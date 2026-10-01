---
title: Unity + Vuforia AR
permalink: /unity-ar
layout: single
hidetitle: "true"
---

<div class="ar-hero">
  <h1>Unity + Vuforia: Building Marker-Based AR</h1>
  <p>A walkthrough of how a Unity application recognises a printed image and overlays 3D content on it in real time — the core concepts, then the full build pipeline, with the reasoning behind each step. Built as a live reference for walking an audience through a practical AR demonstration.</p>
  <nav class="ar-jumpnav">
    <a href="#tree">Technology Tree</a>
    <a href="#concepts">Core Concepts</a>
    <a href="#flow">Build Flow</a>
    <a href="#why-these-tools">Why These Tools</a>
  </nav>
</div>

<h2 class="ar-section-title" id="tree">The AR Technology Tree</h2>
<p class="ar-tree-intro">Every node below is a real alternative at that layer of the stack. Click any node to trace its path from "Augmented Reality" and read what it is on the right. Nodes highlighted in green are the ones this build actually uses — they converge into the final stack at the bottom.</p>

<div class="ar-tree-wrap">

  <div class="ar-tree-canvas" id="ar-tree-canvas">
    <svg class="ar-tree-lines" id="ar-tree-lines"></svg>

    <div class="ar-tree-col ar-tree-root-col">
      <button type="button" class="ar-node ar-node-root" data-id="root">Augmented Reality</button>

      <div class="ar-tree-row">

        <div class="ar-tree-col">
          <button type="button" class="ar-node ar-node-branch" data-id="sdk" data-parent="root">SDK</button>
          <div class="ar-tree-row">
            <button type="button" class="ar-node ar-node-leaf is-path" data-id="vuforia" data-parent="sdk">Vuforia</button>
            <button type="button" class="ar-node ar-node-leaf" data-id="arcore" data-parent="sdk">ARCore</button>
            <button type="button" class="ar-node ar-node-leaf" data-id="arkit" data-parent="sdk">ARKit</button>
            <button type="button" class="ar-node ar-node-leaf" data-id="webar" data-parent="sdk">8th Wall</button>
          </div>
        </div>

        <div class="ar-tree-col">
          <button type="button" class="ar-node ar-node-branch" data-id="engine" data-parent="root">Game Engine</button>
          <div class="ar-tree-row">
            <button type="button" class="ar-node ar-node-leaf is-path" data-id="unity" data-parent="engine">Unity</button>
            <button type="button" class="ar-node ar-node-leaf" data-id="unreal" data-parent="engine">Unreal Engine</button>
            <button type="button" class="ar-node ar-node-leaf" data-id="native" data-parent="engine">Native SDK only</button>
          </div>
        </div>

        <div class="ar-tree-col">
          <button type="button" class="ar-node ar-node-branch" data-id="tracking" data-parent="root">Tracking Approach</button>
          <div class="ar-tree-row">

            <div class="ar-tree-col">
              <button type="button" class="ar-node ar-node-leaf is-path" data-id="marker" data-parent="tracking">Marker-based</button>
              <div class="ar-tree-row ar-tree-row--detail">
                <button type="button" class="ar-node ar-node-detail is-path" data-id="img-target" data-parent="marker">Image Targets</button>
                <button type="button" class="ar-node ar-node-detail" data-id="model-target" data-parent="marker">Model Targets</button>
                <button type="button" class="ar-node ar-node-detail" data-id="vumark" data-parent="marker">VuMarks</button>
              </div>
            </div>

            <div class="ar-tree-col">
              <button type="button" class="ar-node ar-node-leaf" data-id="markerless" data-parent="tracking">Markerless</button>
              <div class="ar-tree-row ar-tree-row--detail">
                <button type="button" class="ar-node ar-node-detail" data-id="slam" data-parent="markerless">SLAM / VIO</button>
                <button type="button" class="ar-node ar-node-detail" data-id="plane" data-parent="markerless">Plane Detection</button>
                <button type="button" class="ar-node ar-node-detail" data-id="location" data-parent="markerless">Location-based</button>
              </div>
            </div>

          </div>
        </div>

      </div>

      <div class="ar-tree-converge-row">
        <button type="button" class="ar-node ar-node-converge" data-id="stack" data-parents="img-target,vuforia,unity">Marker-based + Image Target + Vuforia + Unity</button>
      </div>

    </div>
  </div>

  <aside class="ar-detail-panel" id="ar-detail-panel">
    <p class="ar-detail-placeholder">Click any node to see what it is.</p>
  </aside>

</div>

<h2 class="ar-section-title" id="concepts">Core Concepts</h2>

<div class="ar-glossary">

  <details class="ar-term" open>
    <summary>What is Augmented Reality (AR)?</summary>
    <div class="ar-term-body">
      <p>Augmented Reality overlays computer-generated content — 3D models, video, text, sound — onto a live view of the real world, usually through a phone or headset camera. Unlike Virtual Reality, which replaces what you see entirely, AR adds to it: the real environment stays visible, with digital elements blended in on top and anchored so they appear to belong in the scene.</p>
      <p>There are two broad approaches, and the distinction matters for what you're about to demonstrate:</p>
      <ul>
        <li><strong>Marker-based AR</strong> — content appears when the camera recognises a specific pre-registered image or object (a "marker"). This is what Vuforia's Image Targets do, and what today's demo is built on.</li>
        <li><strong>Markerless AR</strong> — content is placed using the device's own sensors (camera, GPS, accelerometer, depth sensing) to understand surfaces and location, without needing a pre-registered image. This is how ARKit/ARCore "place an object on this table" experiences work.</li>
      </ul>
      <p><strong>Why marker-based, for this demo:</strong> it's deterministic and easy for an audience to follow — show the printed image, the content appears, move the image, the content follows. There's a clear, visible cause and effect, which is harder to narrate live with markerless/surface-detection AR.</p>
    </div>
  </details>

  <details class="ar-term">
    <summary>What is a Marker / Image Target?</summary>
    <div class="ar-term-body">
      <p>A marker is a real-world image or object that an AR application is trained to recognise. In Vuforia, this is called an <strong>Image Target</strong>. Once the camera detects the target in the physical world, the engine tracks its position and orientation continuously — even as the camera or the target moves — and uses that position as the "anchor" for digital content.</p>
      <p>Under the hood, Vuforia converts the marker image to grayscale and extracts <strong>feature points</strong> — sharp, high-contrast corners and edges — then stores them as a searchable set of coordinates. At runtime, it looks for that same pattern of feature points in the live camera feed. The more distinct, asymmetric detail an image has, the more reliable the match.</p>
      <p>This is why Vuforia's Target Manager gives every uploaded marker a <strong>star rating from 1 to 5</strong> before you ever open Unity — it's scoring how trackable the image actually is.</p>
      <p><strong>Why this matters live:</strong> if your printed marker isn't tracking well on stage, it's almost always a feature-point problem — too plain, too symmetric, too low-contrast, or too small/blurry when printed. Worth checking the star rating beforehand, not debugging it live.</p>
    </div>
  </details>

  <details class="ar-term">
    <summary>What is an SDK?</summary>
    <div class="ar-term-body">
      <p>A Software Development Kit (SDK) is a ready-made toolbox for building on a specific platform — a bundle of libraries, APIs, sample code, and documentation, so developers don't have to solve the same low-level problems from scratch. Vuforia is an SDK for computer-vision-based AR: it handles image recognition, camera access, and real-time tracking, so a developer only has to decide what content to show and where.</p>
      <p><strong>Why it matters:</strong> without an SDK like Vuforia, recognising and tracking an image through a camera feed in real time would mean writing your own computer-vision pipeline — feature detection, matching, pose estimation — before you could even begin placing 3D content. The SDK is what turns a multi-week computer-vision research problem into a feature you can set up inside Unity in an afternoon.</p>
    </div>
  </details>

  <details class="ar-term">
    <summary>What is a Game Engine?</summary>
    <div class="ar-term-body">
      <p>A game engine is a software framework that provides the core systems a real-time application needs — rendering, physics, audio, input, and scene management — so developers build the experience itself rather than that underlying infrastructure. <strong>Unity</strong> is one of the most widely used engines for this, supporting 2D, 3D, AR, and VR projects across many platforms from a single codebase.</p>
      <p>In an AR pipeline, the game engine is where everything comes together: it runs the SDK's tracking data, renders the 3D content, and handles how the user interacts with it. Vuforia alone only tells you <em>where</em> the marker is — Unity is what actually draws the 3D object on top of it and lets you script what happens next.</p>
    </div>
  </details>

  <details class="ar-term">
    <summary>What is Vuforia, specifically?</summary>
    <div class="ar-term-body">
      <p>Vuforia Engine is an augmented reality SDK that plugs directly into Unity. It provides the computer-vision pipeline — detecting and tracking Image Targets, Model Targets, and other marker types through the device camera — and exposes that tracking data to Unity's scene graph, so a 3D object can simply be "childed" under a tracked target and will follow it automatically, with no manual position-tracking code required.</p>
      <p>Developed by PTC. Account, license keys, and documentation live on the <a href="https://developer.vuforia.com/" target="_blank" rel="noopener">Vuforia Developer Portal</a>; the Unity integration itself is distributed as a free package on the <a href="https://assetstore.unity.com/packages/templates/packs/vuforia-engine-163598" target="_blank" rel="noopener">Unity Asset Store</a>.</p>
    </div>
  </details>

</div>

<h2 class="ar-section-title" id="flow">The Full Build Flow</h2>

<div class="ar-flow">

  <div class="ar-step">
    <div class="ar-step-num">1</div>
    <div class="ar-step-body">
      <h3>Create a Vuforia Developer Account</h3>
      <p>Go to the <a href="https://developer.vuforia.com/" target="_blank" rel="noopener">Vuforia Developer Portal</a> and register for a free account. This account is what every license key and target database you create is tied to.</p>
    </div>
  </div>

  <div class="ar-step">
    <div class="ar-step-num">2</div>
    <div class="ar-step-body">
      <h3>Generate a Vuforia License Key</h3>
      <p>In the portal, go to <strong>Develop → License Manager → Get Basic</strong> (free tier), give the license a name, and create it. Click into the license you just created and copy the key shown there.</p>
      <p class="ar-why"><strong>Why:</strong> Vuforia won't initialise in Unity without a license key tied to your account — it's what authorises the app to use Vuforia's recognition and tracking features.</p>
    </div>
  </div>

  <div class="ar-step">
    <div class="ar-step-num">3</div>
    <div class="ar-step-body">
      <h3>Create the Unity Project</h3>
      <p>In Unity Hub, click <strong>New Project</strong>, pick the <strong>Universal 3D</strong> template, name it, and click <strong>Create</strong> — a clean starting point with the camera, lighting, and render pipeline already in place.</p>
    </div>
  </div>

  <div class="ar-step">
    <div class="ar-step-num">4</div>
    <div class="ar-step-body">
      <h3>Import Vuforia Engine</h3>
      <p>On the <a href="https://assetstore.unity.com/packages/templates/packs/vuforia-engine-163598" target="_blank" rel="noopener">Vuforia Engine Asset Store page</a>, click <strong>Add to My Assets</strong> (sign in if asked). Back in Unity, open <strong>Window → Package Manager</strong>, switch the dropdown at the top to <strong>Packages: My Assets</strong>, select <strong>Vuforia Engine AR</strong>, click <strong>Download</strong>, then <strong>Import</strong>, and confirm with <strong>Import</strong> in the dialog that appears.</p>
    </div>
  </div>

  <div class="ar-step">
    <div class="ar-step-num">5</div>
    <div class="ar-step-body">
      <h3>Add the License Key to Unity</h3>
      <p>In Unity, open <strong>Window → Vuforia Configuration</strong>. In the Inspector panel that opens, paste your key from step 2 into the <strong>App License Key</strong> field. It saves automatically — there's no separate save button.</p>
    </div>
  </div>

  <div class="ar-step">
    <div class="ar-step-num">6</div>
    <div class="ar-step-body">
      <h3>Replace the Main Camera with an AR Camera</h3>
      <p>In the Hierarchy panel, select <strong>Main Camera</strong> and delete it. Then go to <strong>GameObject → Vuforia Engine → AR Camera</strong> to add the replacement. This camera streams the live device feed into the scene and feeds it through Vuforia's tracking.</p>
      <p class="ar-why"><strong>Why:</strong> a normal Unity camera only renders the 3D scene — it has no idea what the physical camera is seeing. The AR Camera is what bridges the two: real camera feed in, tracked marker positions out.</p>
    </div>
  </div>

  <div class="ar-step">
    <div class="ar-step-num">7</div>
    <div class="ar-step-body">
      <h3>Design the Marker</h3>
      <p>With Unity now AR-ready, switch to designing the marker itself: sketch or draw something with rich, asymmetric detail. Avoid plain shapes, symmetry, or large flat areas of a single colour.</p>
      <p class="ar-why"><strong>Why:</strong> this connects directly to the feature-point tracking covered above — detail, contrast, and asymmetry are literally what Vuforia extracts and matches against. A plain or symmetric drawing will track poorly no matter how well everything else is set up.</p>
    </div>
  </div>

  <div class="ar-step">
    <div class="ar-step-num">8</div>
    <div class="ar-step-body">
      <h3>Photograph the Marker</h3>
      <p>Take a clear photo of the finished drawing. Don't edit the colours or apply any filter — just crop it to the drawing's edges — then transfer the image to your laptop.</p>
      <p class="ar-why"><strong>Why:</strong> Vuforia extracts features from this exact image. Colour edits or filters change what gets analysed versus what the camera will actually see live, which can quietly hurt tracking.</p>
    </div>
  </div>

  <div class="ar-step">
    <div class="ar-step-num">9</div>
    <div class="ar-step-body">
      <h3>Create a Target Database</h3>
      <p>In the Developer Portal, go to <strong>Develop → Target Manager</strong>, click <strong>Add Database</strong>, give it a name, choose <strong>Device</strong> as the database type (not Cloud), and click <strong>Create</strong>.</p>
    </div>
  </div>

  <div class="ar-step">
    <div class="ar-step-num">10</div>
    <div class="ar-step-body">
      <h3>Upload the Marker Image</h3>
      <p>Click into your new database, then click <strong>Add Target</strong>. Set Type to <strong>Single Image</strong>, choose your cropped photo as the file, enter a Width (in scene units) and a Name, then click <strong>Add</strong>.</p>
    </div>
  </div>

  <div class="ar-step">
    <div class="ar-step-num">11</div>
    <div class="ar-step-body">
      <h3>Check the Star Rating</h3>
      <p>Back on the database page, the star rating (1–5) appears next to your uploaded target's thumbnail. <strong>Only proceed at 4 or 5 stars.</strong> Below that, go back to step 7 and redesign the marker with more contrast and detail.</p>
      <p class="ar-why"><strong>Why:</strong> this rating is a direct preview of how reliably the marker will track live — catching a weak marker here is far better than discovering it isn't tracking in front of an audience.</p>
    </div>
  </div>

  <div class="ar-step">
    <div class="ar-step-num">12</div>
    <div class="ar-step-body">
      <h3>Download the Database</h3>
      <p>Tick the checkbox next to your target, click <strong>Download Database (All)</strong>, choose <strong>Unity Editor</strong> as the format, then <strong>Download</strong> and save the <code>.unitypackage</code> file.</p>
    </div>
  </div>

  <div class="ar-step">
    <div class="ar-step-num">13</div>
    <div class="ar-step-body">
      <h3>Import the Target Database into Unity</h3>
      <p>Back in the Unity project from step 6, double-click the downloaded <code>.unitypackage</code> (or go to <strong>Assets → Import Package → Custom Package</strong> and select it), then click <strong>Import</strong> in the dialog — this brings your specific marker's tracking data in.</p>
    </div>
  </div>

  <div class="ar-step">
    <div class="ar-step-num">14</div>
    <div class="ar-step-body">
      <h3>Add an Image Target</h3>
      <p>Go to <strong>GameObject → Vuforia Engine → Image Target</strong>. Select it in the Hierarchy, then in its Inspector (the Image Target Behaviour component), set the <strong>Database</strong> dropdown to the database you just imported and the <strong>Image Target</strong> dropdown to your specific marker.</p>
      <p class="ar-why"><strong>Why:</strong> this is the link between "an image Vuforia can recognise" and "a point in the Unity scene" — it's the anchor everything else attaches to.</p>
    </div>
  </div>

  <div class="ar-step">
    <div class="ar-step-num">15</div>
    <div class="ar-step-body">
      <h3>Add Your 3D Content</h3>
      <p>Drag your own 3D model — or the one provided — from the Project window into the Hierarchy, dropping it directly onto the <strong>ImageTarget</strong> object so it becomes a child of it.</p>
      <p class="ar-why"><strong>Why:</strong> Unity's parent-child transform system means the content's position updates automatically whenever the Image Target's tracked position updates — no manual code needed to make it "follow" the marker.</p>
    </div>
  </div>

  <div class="ar-step">
    <div class="ar-step-num">16</div>
    <div class="ar-step-body">
      <h3>Scale and Position the Model</h3>
      <p>Select the model and use its Inspector's <strong>Transform → Scale</strong> fields (or press <strong>R</strong> for the Scale tool in the Scene view) so the content reads clearly against the marker — not so small it's hard to see, not so large it overwhelms the frame or clips oddly. Keep proportions close to how the object would actually look at that size.</p>
    </div>
  </div>

  <div class="ar-step">
    <div class="ar-step-num">17</div>
    <div class="ar-step-body">
      <h3>Test with the Webcam</h3>
      <p>Click the <strong>Play</strong> button at the top of the Unity Editor, allow camera access if prompted, and hold the printed marker up to your laptop's webcam. Confirm the model appears, stays anchored, and tracks correctly as you move the marker.</p>
    </div>
  </div>

  <div class="ar-checkpoint">
    <strong>Checkpoint —</strong> this is already a complete, working AR demo. Everything below is optional polish (UI, effects, animation, scripting) before the final build.
  </div>

  <div class="ar-step">
    <div class="ar-step-num">18</div>
    <div class="ar-step-body">
      <h3>Build the UI</h3>
      <p>Go to <strong>GameObject → UI → Canvas</strong> (this also auto-creates an EventSystem), then add buttons, labels, or on-screen instructions as children via <strong>GameObject → UI → Button / Text</strong>, etc.</p>
    </div>
  </div>

  <div class="ar-step">
    <div class="ar-step-num">19</div>
    <div class="ar-step-body">
      <h3>Add Particle Effects</h3>
      <p>Go to <strong>GameObject → Effects → Particle System</strong> for visual flourishes — sparks, glow, dust, and similar — as additional children of the Image Target or model.</p>
    </div>
  </div>

  <div class="ar-step">
    <div class="ar-step-num">20</div>
    <div class="ar-step-body">
      <h3>Set Up Animation</h3>
      <p>Drag a rigged, animated model (FBX) into the Project window. Select it, open the <strong>Rig</strong> tab in the Inspector, set Animation Type to <strong>Humanoid</strong> or <strong>Generic</strong>, and click <strong>Apply</strong>. Right-click in the Project window → <strong>Create → Animator Controller</strong>, then open <strong>Window → Animation → Animator</strong> to drag in clips and connect transitions between them. Finally, select your model's <strong>Animator</strong> component and assign this controller to its <strong>Controller</strong> field.</p>
    </div>
  </div>

  <div class="ar-step">
    <div class="ar-step-num">21</div>
    <div class="ar-step-body">
      <h3>Add Unity Events</h3>
      <p>On a UI Button's Inspector, scroll to the <strong>On Click ()</strong> list, click <strong>+</strong>, drag in the target GameObject, then pick a function from the dropdown — for example, a particle system's <strong>SetActive</strong> to toggle visibility, or a custom script's public method to trigger an animation.</p>
    </div>
  </div>

  <div class="ar-step">
    <div class="ar-step-num">22</div>
    <div class="ar-step-body">
      <h3>Write a Script</h3>
      <p>In the Project window, right-click → <strong>Create → C# Script</strong>, name it, and double-click to open it in your code editor. After writing the logic — for example, a "billboard" script that makes a text label continuously face the camera, or a script that keeps the AR model rotating — drag the script onto the target GameObject in the Hierarchy (or use <strong>Add Component</strong> in its Inspector) to attach it.</p>
    </div>
  </div>

  <div class="ar-step">
    <div class="ar-step-num">23</div>
    <div class="ar-step-body">
      <h3>Open Build Settings</h3>
      <p>Go to <strong>File → Build Settings</strong>, select <strong>Android</strong> (or iOS) in the Platform list, and click <strong>Switch Platform</strong>.</p>
    </div>
  </div>

  <div class="ar-step">
    <div class="ar-step-num">24</div>
    <div class="ar-step-body">
      <h3>Configure Player Settings</h3>
      <p>In the same Build Settings window, click <strong>Player Settings</strong>. Under <strong>Other Settings</strong>, set the Package Name and Minimum API Level; under <strong>Icon</strong>, set the app icon; under <strong>Resolution and Presentation</strong>, set the Default Orientation.</p>
    </div>
  </div>

  <div class="ar-step">
    <div class="ar-step-num">25</div>
    <div class="ar-step-body">
      <h3>Manage Scenes in the Build</h3>
      <p>In the Build Settings window's <strong>Scenes In Build</strong> list, click <strong>Add Open Scenes</strong> to add your AR scene, then select and remove (uncheck or delete) any unused or demo scenes already listed.</p>
    </div>
  </div>

  <div class="ar-step">
    <div class="ar-step-num">26</div>
    <div class="ar-step-body">
      <h3>Build</h3>
      <p>Click <strong>Build</strong> (or <strong>Build And Run</strong>) in the Build Settings window, choose an output folder, and Unity will compile the final APK (or IPA).</p>
    </div>
  </div>

</div>

<h2 class="ar-section-title" id="why-these-tools">Why Unity + Vuforia (and not something else)</h2>
<div class="ar-why-tools">
  <p>Unity is the dominant engine for AR/VR work — an estimated 60% of AR/VR content is built on it — largely because of its mobile-first architecture, built-in AR Foundation/ARCore/ARKit support, and a much gentler learning curve (C#) than Unreal's C++ toolchain. For a live demo meant to run reliably on a phone in front of an audience, that mobile optimisation and setup speed matters more than Unreal's graphical ceiling.</p>
  <p>Vuforia remains one of the most established marker-tracking SDKs for exactly this use case: it's been doing image-target recognition since well before ARKit/ARCore existed, and it works consistently across both Android and iOS from one Unity project — useful when you don't know in advance which device the audience will be watching it on.</p>
</div>

<script>
(function () {
  var nodeInfo = {
    root: {
      title: "Augmented Reality",
      text: "Overlays computer-generated content onto a live view of the real world. Everything in this tree is a different way of answering: how do we figure out <em>where</em> to put that content, and <em>what</em> do we build it with?"
    },
    tracking: {
      title: "Tracking Approach",
      text: "How the app figures out where in physical space to anchor digital content. The two branches below — marker-based and markerless — solve this in fundamentally different ways."
    },
    marker: {
      title: "Marker-based AR",
      text: "Content appears when the camera recognises a specific pre-registered image or object. Deterministic and easy to follow live: show the marker, content appears, move it, content follows. This is what today's demo uses.",
      tag: "Used in today's demo"
    },
    "img-target": {
      title: "Image Targets",
      text: "A flat image Vuforia has extracted feature points from and can recognise in the live camera feed. The marker type used in today's demo."
    },
    "model-target": {
      title: "Model Targets",
      text: "Lets Vuforia recognise the 3D shape of a real object — like a physical product — using a 3D model of that object as the reference, instead of a flat image."
    },
    vumark: {
      title: "VuMarks",
      text: "Vuforia's own customisable, scannable marker format — part barcode, part QR code — that can be styled to match a brand while still encoding trackable data."
    },
    markerless: {
      title: "Markerless AR",
      text: "Content is placed using the device's own sensors — camera, GPS, accelerometer, depth sensing — to understand surfaces and location, with no pre-registered image needed. This is how ARKit/ARCore \"place an object on this table\" experiences work."
    },
    slam: {
      title: "SLAM / Visual-Inertial Odometry",
      text: "Simultaneous Localization and Mapping: combines camera and IMU (motion sensor) data to work out the device's position and the shape of the room in real time, with no marker required."
    },
    plane: {
      title: "Plane Detection",
      text: "Clusters of tracked feature points are used to identify flat surfaces — floors, tables, walls — so virtual objects can be placed on them realistically."
    },
    location: {
      title: "Location-based AR",
      text: "Uses GPS, compass, and other positioning sensors to anchor content to real-world coordinates rather than visual features — common in location-based AR games and wayfinding apps."
    },
    sdk: {
      title: "SDK",
      text: "The toolbox that actually does the recognition and tracking — camera access, computer vision, pose estimation — so the engine only has to decide what to render and where."
    },
    vuforia: {
      title: "Vuforia",
      text: "An AR SDK from PTC that plugs directly into Unity, providing Image Target / Model Target tracking. One of the most established marker-tracking SDKs, predating ARKit and ARCore, and works the same way across Android and iOS.",
      tag: "Used in today's demo",
      link: { href: "https://developer.vuforia.com/", label: "Vuforia Developer Portal" }
    },
    arcore: {
      title: "ARCore",
      text: "Google's AR SDK for Android. Detects feature points in the environment and clusters them into planes (floors, tables, walls), using visual-inertial SLAM for six-degrees-of-freedom tracking, plus Cloud Anchors for shared multi-device AR."
    },
    arkit: {
      title: "ARKit",
      text: "Apple's AR framework for iOS. Combines visual-inertial odometry with scene understanding; on LiDAR-equipped devices it uses depth data automatically for more precise tracking, occlusion, and better recognition of low-texture surfaces like plain walls."
    },
    webar: {
      title: "8th Wall",
      text: "A browser-based WebAR SDK — experiences run instantly from a URL, no app install required — built on a JavaScript/WebGL SLAM engine optimised for real-time AR directly inside a mobile browser."
    },
    engine: {
      title: "Game Engine",
      text: "Where everything comes together: it runs the SDK's tracking data, renders the 3D content, and handles interaction. The SDK only tells you where the marker is — the engine is what actually draws something on top of it."
    },
    unity: {
      title: "Unity",
      text: "A mobile-first, cross-platform engine using C# — an estimated 60% of AR/VR content is built on it. Gentler learning curve than Unreal and typically better-optimised for entry-level and mid-range mobile hardware, which is why it's used in today's demo.",
      tag: "Used in today's demo"
    },
    unreal: {
      title: "Unreal Engine",
      text: "Epic's C++ engine, known for a higher graphical ceiling and used heavily in high-end VR and cinematic work. Steeper learning curve than Unity and less mobile-optimised, which matters more for a lightweight, reliably-running live demo than raw visual fidelity."
    },
    native: {
      title: "Native SDK only",
      text: "Building directly against ARKit/ARCore's native APIs (Swift/Kotlin) with no game engine in between. Maximum control and performance, but rendering, UI, and tooling all have to be built from scratch."
    },
    stack: {
      title: "The Stack Used in This Build",
      text: "Four choices, each from a different branch above, combined into one working pipeline: Marker-based tracking, using an Image Target as the specific marker type, recognised by the Vuforia SDK, rendered and scripted inside Unity. Every other node in this tree is a real alternative at that layer — this is simply the path this particular build takes."
    }
  };

  var canvas = document.getElementById("ar-tree-canvas");
  var svg = document.getElementById("ar-tree-lines");
  var panel = document.getElementById("ar-detail-panel");
  var nodes = Array.prototype.slice.call(canvas.querySelectorAll(".ar-node"));

  // A node normally has one parent (data-parent). The convergence node has
  // several (data-parents, comma-separated) since it pulls together one
  // chosen leaf from each separate branch of the tree.
  function getParentIds(node) {
    var multi = node.getAttribute("data-parents");
    if (multi) return multi.split(",");
    var single = node.getAttribute("data-parent");
    return single ? [single] : [];
  }

  function getNode(id) {
    return canvas.querySelector('.ar-node[data-id="' + id + '"]');
  }

  // The fixed path this build actually uses, shown as a permanently
  // highlighted route (not just on click) so it reads at a glance.
  var pinnedIds = ["root", "tracking", "marker", "img-target", "sdk", "vuforia", "engine", "unity", "stack"];

  function drawLines() {
    var canvasRect = canvas.getBoundingClientRect();
    svg.setAttribute("width", canvasRect.width);
    svg.setAttribute("height", canvasRect.height);
    svg.innerHTML = "";

    nodes.forEach(function (node) {
      var toId = node.getAttribute("data-id");
      var isConverge = !!node.getAttribute("data-parents");

      getParentIds(node).forEach(function (parentId) {
        var parent = getNode(parentId);
        if (!parent) return;

        var a = parent.getBoundingClientRect();
        var b = node.getBoundingClientRect();
        var x1 = a.left + a.width / 2 - canvasRect.left;
        var y1 = a.bottom - canvasRect.top;
        var x2 = b.left + b.width / 2 - canvasRect.left;
        var y2 = b.top - canvasRect.top;

        var d;
        if (isConverge) {
          // Convergence lines route straight down, then cross horizontally
          // only inside the empty gutter just above the final box — never
          // diagonally through the middle of unrelated branches.
          var gutterY = y2 - 22;
          d = "M " + x1 + " " + y1 + " L " + x1 + " " + gutterY + " L " + x2 + " " + gutterY + " L " + x2 + " " + y2;
        } else {
          var midY = (y1 + y2) / 2;
          d = "M " + x1 + " " + y1 + " C " + x1 + " " + midY + ", " + x2 + " " + midY + ", " + x2 + " " + y2;
        }

        var path = document.createElementNS("http://www.w3.org/2000/svg", "path");
        path.setAttribute("d", d);
        var isPinned = pinnedIds.indexOf(parentId) !== -1 && pinnedIds.indexOf(toId) !== -1;
        path.setAttribute("class", "ar-tree-line" + (isPinned ? " is-pinned" : ""));
        path.setAttribute("data-from", parentId);
        path.setAttribute("data-to", toId);
        svg.appendChild(path);
      });
    });
  }

  function ancestorChain(id) {
    var visited = {};
    var queue = [id];
    while (queue.length) {
      var current = queue.shift();
      if (visited[current]) continue;
      visited[current] = true;
      var node = getNode(current);
      if (!node) continue;
      getParentIds(node).forEach(function (parentId) {
        queue.push(parentId);
      });
    }
    return Object.keys(visited);
  }

  function showDetail(id) {
    var info = nodeInfo[id];
    if (!info) return;

    var html = "<h3>" + info.title + "</h3>";
    if (info.tag) html += '<span class="ar-detail-tag">' + info.tag + "</span>";
    html += "<p>" + info.text + "</p>";
    if (info.link) html += '<a href="' + info.link.href + '" target="_blank" rel="noopener">' + info.link.label + " &rarr;</a>";
    panel.innerHTML = html;
  }

  function selectNode(id) {
    var chain = ancestorChain(id);

    nodes.forEach(function (node) {
      node.classList.toggle("is-active", chain.indexOf(node.getAttribute("data-id")) !== -1);
    });

    Array.prototype.slice.call(svg.querySelectorAll(".ar-tree-line")).forEach(function (line) {
      var isActive = chain.indexOf(line.getAttribute("data-from")) !== -1 && chain.indexOf(line.getAttribute("data-to")) !== -1;
      line.classList.toggle("is-active", isActive);
    });

    showDetail(id);
  }

  nodes.forEach(function (node) {
    node.addEventListener("click", function () {
      selectNode(node.getAttribute("data-id"));
    });
  });

  window.addEventListener("resize", drawLines);
  window.addEventListener("load", drawLines);
  drawLines();
})();
</script>
