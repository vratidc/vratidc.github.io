---
title: Unity + Vuforia AR
permalink: /unity-ar
layout: single
hidetitle: "true"
sitemap: false
noindex: true
search: false
description: "Live-demo reference for building marker-based AR with Unity and Vuforia — unlisted, not for general browsing."
---

<div class="ar-hero">
  <h1>Unity + Vuforia: Building Marker-Based AR</h1>
  <p>A walkthrough of how a Unity application recognises a hand-drawn marker and overlays 3D content on it in real time — the underlying concepts explained in the technology tree below, then the full build pipeline, with the reasoning behind each step. Built as a live reference for walking an audience through a practical AR demonstration.</p>
  <nav class="ar-jumpnav">
    <a href="#tree">Technology Tree</a>
    <a href="#flow">Build Flow</a>
    <a href="#why-these-tools">Why These Tools</a>
  </nav>
</div>

<h2 class="ar-section-title" id="tree">The AR Technology Tree</h2>
<p class="ar-tree-intro">AR branches into three independent choices — SDK, tracking approach, and game engine — each with real alternatives.</p>

<div class="ar-tree-wrap">

  <div class="ar-tree-canvas" id="ar-tree-canvas">
    <svg class="ar-tree-lines" id="ar-tree-lines"></svg>

    <div class="ar-tree-level ar-tree-level--root">
      <button type="button" class="ar-node ar-node-root" data-id="root">AR</button>
    </div>

    <div class="ar-tree-level ar-tree-level--branches">

      <div class="ar-tree-branch-col">
        <button type="button" class="ar-node ar-node-branch" data-id="sdk" data-parent="root">SDK</button>
        <div class="ar-tree-leaf-group">
          <button type="button" class="ar-node ar-node-leaf" data-id="arkit" data-parent="sdk">ARKit</button>
          <button type="button" class="ar-node ar-node-leaf" data-id="arcore" data-parent="sdk">ARCore</button>
          <button type="button" class="ar-node ar-node-leaf" data-id="vuforia" data-parent="sdk">Vuforia</button>
        </div>
      </div>

      <div class="ar-tree-branch-col">
        <button type="button" class="ar-node ar-node-branch" data-id="tracking" data-parent="root">Tracking</button>
        <div class="ar-tree-leaf-group">
          <button type="button" class="ar-node ar-node-leaf" data-id="markerless" data-parent="tracking">Markerless</button>
          <button type="button" class="ar-node ar-node-leaf" data-id="marker" data-parent="tracking">Marker-based</button>
        </div>
      </div>

      <div class="ar-tree-branch-col">
        <button type="button" class="ar-node ar-node-branch" data-id="engine" data-parent="root">Game Engine</button>
        <div class="ar-tree-leaf-group">
          <button type="button" class="ar-node ar-node-leaf" data-id="unreal" data-parent="engine">Unreal Engine</button>
          <button type="button" class="ar-node ar-node-leaf" data-id="unity" data-parent="engine">Unity</button>
        </div>
      </div>

    </div>

    <div class="ar-tree-level ar-tree-level--used">
      <button type="button" class="ar-node ar-node-used" data-id="used-vuforia" data-parent="vuforia">Vuforia</button>
      <button type="button" class="ar-node ar-node-used" data-id="used-marker" data-parent="marker">Marker-based</button>
      <button type="button" class="ar-node ar-node-used" data-id="used-unity" data-parent="unity">Unity</button>
    </div>

    <p class="ar-tree-caption">This tutorial uses these.</p>
  </div>

  <aside class="ar-detail-panel">
    <p class="ar-detail-hint">Click any node to see what it is</p>
    <div class="ar-detail-panel-content" id="ar-detail-panel"></div>
  </aside>

</div>

<h2 class="ar-section-title" id="flow">The Full Build Flow</h2>

<div class="ar-flow">

  <details class="ar-term" name="build-flow" open>
    <summary>1. Creating a Unity Project</summary>
    <div class="ar-term-body">

      <div class="ar-step">
        <div class="ar-step-body">
          <h3>Create the Unity Project</h3>
          <p>In Unity Hub, click <strong>New Project</strong>, pick the <strong>Universal 3D</strong> template, name it, and click <strong>Create</strong> — a clean starting point with the camera, lighting, and render pipeline already in place.</p>
          <p class="ar-why"><strong>Note:</strong> this page's menu paths assume <strong>Unity 6</strong>. If you're on an older LTS version, the main difference is step 7 — look for <strong>File → Build Settings</strong> instead of <strong>File → Build Profiles</strong>.</p>
        </div>
      </div>

    </div>
  </details>

  <details class="ar-term" name="build-flow">
    <summary>2. Prepare a Marker</summary>
    <div class="ar-term-body">

      <div class="ar-step">
        <div class="ar-step-body">
          <h3>2.1 Design the Marker</h3>
          <p>This is a hand-drawn marker, not a digital graphic — sketch or draw it on paper. Three things matter: <strong>dimensions</strong> (plan roughly how large it'll be drawn, since that affects how close the camera needs to be to track it reliably), <strong>detail</strong> (rich, asymmetric linework — avoid plain shapes, symmetry, or large flat areas of a single colour), and <strong>material</strong> (use a matte finish, not glossy).</p>
          <p class="ar-why"><strong>Why:</strong> detail and asymmetry are what Vuforia's feature-point tracking actually extracts and matches against. A glossy surface adds a second problem on top of that — it catches glare and reflections under camera light, which breaks tracking even if the artwork itself is good.</p>
        </div>
      </div>

      <div class="ar-step">
        <div class="ar-step-body">
          <h3>2.2 Photograph the Marker</h3>
          <p>Take a clear photo of the finished drawing. Don't edit the colours or apply any filter — just crop it to the drawing's edges — then transfer the image to your laptop.</p>
          <p class="ar-why"><strong>Why:</strong> Vuforia extracts features from this exact image. Colour edits or filters change what gets analysed versus what the camera will actually see live, which can quietly hurt tracking.</p>
        </div>
      </div>

    </div>
  </details>

  <details class="ar-term" name="build-flow">
    <summary>3. Setting Up Unity for AR</summary>
    <div class="ar-term-body">

      <div class="ar-step">
        <div class="ar-step-body">
          <h3>Import Vuforia Engine</h3>
          <p>On the <a href="https://assetstore.unity.com/packages/templates/packs/vuforia-engine-163598" target="_blank" rel="noopener">Vuforia Engine Asset Store page</a>, click <strong>Add to My Assets</strong> (sign in if asked). Back in Unity, open <strong>Window → Package Manager</strong>, switch the dropdown at the top to <strong>Packages: My Assets</strong>, select <strong>Vuforia Engine AR</strong>, click <strong>Download</strong>, then <strong>Import</strong>, and confirm with <strong>Import</strong> in the dialog that appears.</p>
        </div>
      </div>

    </div>
  </details>

  <details class="ar-term" name="build-flow">
    <summary>4. Vuforia to Unity</summary>
    <div class="ar-term-body">

      <div class="ar-step">
        <div class="ar-step-body">
          <h3>4.1 Create a Vuforia Developer Account</h3>
          <p>Go to the <a href="https://developer.vuforia.com/" target="_blank" rel="noopener">Vuforia Developer Portal</a> and register for a free account. This account is what every license key and target database you create is tied to.</p>
        </div>
      </div>

      <div class="ar-step">
        <div class="ar-step-body">
          <h3>4.2 Generate a Vuforia License Key</h3>
          <p>In the portal, go to <strong>Develop → License Manager → Get Basic</strong> (free tier), give the license a name, and create it. Click into the license you just created and copy the key shown there.</p>
          <p class="ar-why"><strong>Why:</strong> Vuforia won't initialise in Unity without a license key tied to your account — it's what authorises the app to use Vuforia's recognition and tracking features.</p>
        </div>
      </div>

      <div class="ar-step">
        <div class="ar-step-body">
          <h3>4.3 Create a Target Database</h3>
          <p>In the Developer Portal, go to <strong>Develop → Target Manager</strong>, click <strong>Add Database</strong>, give it a name, choose <strong>Device</strong> as the database type (not Cloud), and click <strong>Create</strong>.</p>
        </div>
      </div>

      <div class="ar-step">
        <div class="ar-step-body">
          <h3>4.4 Upload the Marker Image</h3>
          <p>Click into your new database, then click <strong>Add Target</strong>. Set Type to <strong>Single Image</strong>, choose your cropped photo as the file, enter a Width (in scene units — Vuforia's scene units are metres, so scale the marker's real-world width accordingly) and a Name, then click <strong>Add</strong>.</p>
        </div>
      </div>

      <div class="ar-step">
        <div class="ar-step-body">
          <h3>4.5 Check the Star Rating</h3>
          <p>Back on the database page, the star rating (0–5) appears next to your uploaded target's thumbnail. <strong>Only proceed at 4 or 5 stars.</strong> Below that, go back and redesign the marker with more contrast and detail.</p>
          <p class="ar-why"><strong>Why:</strong> this rating is a direct preview of how reliably the marker will track live — catching a weak marker here is far better than discovering it isn't tracking in front of an audience.</p>
        </div>
      </div>

      <div class="ar-step">
        <div class="ar-step-body">
          <h3>4.6 Download the Database</h3>
          <p>Tick the checkbox next to your target, click <strong>Download Database (All)</strong>, choose <strong>Unity Editor</strong> as the format, then <strong>Download</strong> and save the <code>.unitypackage</code> file. While you're here, keep the license key you generated earlier copied and ready.</p>
        </div>
      </div>

    </div>
  </details>

  <details class="ar-term" name="build-flow">
    <summary>5. Developing for AR</summary>
    <div class="ar-term-body">

      <div class="ar-step">
        <div class="ar-step-body">
          <h3>5.1 Add the License Key to Unity</h3>
          <p>Back in Unity, open <strong>Window → Vuforia Configuration</strong>. In the Inspector panel that opens, paste your key into the <strong>App License Key</strong> field. It saves automatically — there's no separate save button.</p>
        </div>
      </div>

      <div class="ar-step">
        <div class="ar-step-body">
          <h3>5.2 Replace the Main Camera with an AR Camera</h3>
          <p>In the Hierarchy panel, select <strong>Main Camera</strong> and delete it. Then go to <strong>GameObject → Vuforia Engine → AR Camera</strong> to add the replacement. This camera streams the live device feed into the scene and feeds it through Vuforia's tracking.</p>
          <p class="ar-why"><strong>Why:</strong> a normal Unity camera only renders the 3D scene — it has no idea what the physical camera is seeing. The AR Camera is what bridges the two: real camera feed in, tracked marker positions out.</p>
        </div>
      </div>

      <div class="ar-step">
        <div class="ar-step-body">
          <h3>5.3 Import the Target Database into Unity</h3>
          <p>Double-click the <code>.unitypackage</code> you downloaded in the previous phase (or go to <strong>Assets → Import Package → Custom Package</strong> and select it), then click <strong>Import</strong> in the dialog — this brings your specific marker's tracking data into the project.</p>
        </div>
      </div>

      <div class="ar-step">
        <div class="ar-step-body">
          <h3>5.4 Add an Image Target</h3>
          <p>Go to <strong>GameObject → Vuforia Engine → Image Target</strong>. Select it in the Hierarchy, then in its Inspector (the Image Target Behaviour component), set the <strong>Database</strong> dropdown to the database you just imported and the <strong>Image Target</strong> dropdown to your specific marker.</p>
          <p class="ar-why"><strong>Why:</strong> this is the link between "an image Vuforia can recognise" and "a point in the Unity scene" — it's the anchor everything else attaches to.</p>
        </div>
      </div>

      <div class="ar-step">
        <div class="ar-step-body">
          <h3>5.5 Add Your 3D Content</h3>
          <p>Import your 3D model into Unity, then drag it from the Project window into the Hierarchy, dropping it directly onto the <strong>ImageTarget</strong> object so it becomes a child of it.</p>
          <p class="ar-why"><strong>Why:</strong> Unity's parent-child transform system means the content's position updates automatically whenever the Image Target's tracked position updates — no manual code needed to make it "follow" the marker.</p>
        </div>
      </div>

      <div class="ar-step">
        <div class="ar-step-body">
          <h3>5.6 Scale and Position the Model</h3>
          <p>Select the model and use its Inspector's <strong>Transform → Scale</strong> fields (or press <strong>R</strong> for the Scale tool in the Scene view) so the content reads clearly against the marker — not so small it's hard to see, not so large it overwhelms the frame or clips oddly. Keep proportions close to how the object would actually look at that size.</p>
        </div>
      </div>

      <div class="ar-step">
        <div class="ar-step-body">
          <h3>5.7 Check the Webcam Configuration</h3>
          <p>In <strong>Window → Vuforia Configuration</strong>, open the <strong>Webcam</strong> section — make sure <strong>Disable Vuforia Play Mode</strong> is unchecked and <strong>Camera Device</strong> points at your laptop's webcam.</p>
          <p class="ar-why"><strong>Why:</strong> without this, Play mode won't show a camera feed at all, no matter how correctly everything else is set up.</p>
        </div>
      </div>

      <div class="ar-step">
        <div class="ar-step-body">
          <h3>5.8 Test with the Webcam</h3>
          <p>Click the <strong>Play</strong> button at the top of the Unity Editor, allow camera access if prompted, and hold the hand-drawn marker up to your laptop's webcam. Confirm the model appears, stays anchored, and tracks correctly as you move the marker.</p>
        </div>
      </div>

      <div class="ar-checkpoint">
        <strong>Checkpoint —</strong> this is already a complete, working AR demo running in the Editor. Advanced polish and building to a device are optional from here.
      </div>

    </div>
  </details>

  <details class="ar-term" name="build-flow">
    <summary>6. Advanced (Optional)</summary>
    <div class="ar-term-body">

      <div class="ar-step">
        <div class="ar-step-body">
          <h3>Play Sound on Target Found</h3>
          <p>On the Image Target's Vuforia event handler, hook up an <strong>OnTargetFound</strong> event to play an Audio Source — for example, a short sound the moment the marker is recognised.</p>
        </div>
      </div>

      <div class="ar-step">
        <div class="ar-step-body">
          <h3>Spatial Text UI</h3>
          <p>Add world-space text (a <strong>3D Text</strong> or world-space Canvas <strong>Text</strong> object) as a child of the model or Image Target — labels, callouts, or captions that sit in the scene itself rather than on the screen.</p>
        </div>
      </div>

      <div class="ar-step">
        <div class="ar-step-body">
          <h3>Sound Button (Screen UI)</h3>
          <p>Add a screen-space UI button that plays or mutes audio on click, using the button's <strong>On Click ()</strong> list in the Inspector.</p>
        </div>
      </div>

      <div class="ar-step">
        <div class="ar-step-body">
          <h3>Toggle Particle Effects (VFX)</h3>
          <p>Add a Particle System as a child of the model, then use a UI button or event to toggle its visibility or trigger it on demand.</p>
        </div>
      </div>

      <div class="ar-step">
        <div class="ar-step-body">
          <h3>Import and Integrate a Rigged Animated Asset</h3>
          <p>Import a rigged, animated model, create an Animator Controller for it, wire up the animation clip(s), and confirm it plays correctly once parented under the Image Target.</p>
        </div>
      </div>

      <div class="ar-step">
        <div class="ar-step-body">
          <h3>Basic Scripting</h3>
          <p>Write a short C# script and attach it to a GameObject for simple behaviour — for example, a constant rotation, or a colour change triggered on some event.</p>
        </div>
      </div>

    </div>
  </details>

  <details class="ar-term" name="build-flow">
    <summary>7. Building the APK</summary>
    <div class="ar-term-body">

      <div class="ar-step">
        <div class="ar-step-body">
          <h3>7.1 Install the Platform's Build Support Module</h3>
          <p>In Unity Hub, under your Unity install, click the gear icon → <strong>Add Modules</strong> and install <strong>Android Build Support</strong> (which bundles the Android SDK/NDK/OpenJDK) — or <strong>iOS Build Support</strong> if targeting iPhone/iPad.</p>
          <p class="ar-why"><strong>Why:</strong> this is a one-time install separate from Unity itself. Skipping it is the most common reason "Android" or "iOS" doesn't even appear as an option in the next step.</p>
        </div>
      </div>

      <div class="ar-step">
        <div class="ar-step-body">
          <h3>7.2 Open Build Profiles and Switch Platform</h3>
          <p>Go to <strong>File → Build Profiles</strong> (this replaced the old "Build Settings" window in Unity 6), select <strong>Android</strong> (or iOS) in the Platform list, and click <strong>Switch Platform</strong>.</p>
        </div>
      </div>

      <div class="ar-step">
        <div class="ar-step-body">
          <h3>7.3 Configure Player Settings</h3>
          <p>In the Build Profiles window, click <strong>Player Settings</strong>. For Android, under <strong>Other Settings</strong>: set the Package Name, set <strong>Minimum API Level</strong> to at least <strong>API 24 (Android 7.0)</strong> — check Vuforia's current minimum, since it can require higher — and set <strong>Scripting Backend</strong> to <strong>IL2CPP</strong> with <strong>Target Architectures</strong> including <strong>ARM64</strong>. Under <strong>Icon</strong>, set the app icon; under <strong>Resolution and Presentation</strong>, set the Default Orientation.</p>
          <p class="ar-why"><strong>Why:</strong> the Play Store has required 64-bit (ARM64) support for years, and Unity's Mono scripting backend can't target it — only IL2CPP can. Newer phones (Pixel 7 and later) are 64-bit only and can't run a 32-bit build at all, so skipping this doesn't just risk a Play Store rejection — it can mean the app won't install on current hardware.</p>
        </div>
      </div>

      <div class="ar-step">
        <div class="ar-step-body">
          <h3>7.4 iOS Only: Set the Camera Usage Description</h3>
          <p>Still in Player Settings, under <strong>Other Settings → Configuration</strong>, fill in <strong>Camera Usage Description</strong> with a short sentence explaining why the app needs the camera.</p>
          <p class="ar-why"><strong>Why:</strong> without this string in its Info.plist, iOS terminates the app the moment it requests camera access, and App Store review rejects the build outright — the Vuforia camera feed will never appear on a real iPhone/iPad without it.</p>
        </div>
      </div>

      <div class="ar-step">
        <div class="ar-step-body">
          <h3>7.5 Manage Scenes in the Build</h3>
          <p>In the Build Profiles window's <strong>Scene List</strong>, click <strong>Add Open Scenes</strong> to add your AR scene, then select and remove (uncheck or delete) any unused or demo scenes already listed.</p>
        </div>
      </div>

      <div class="ar-step">
        <div class="ar-step-body">
          <h3>7.6 Build</h3>
          <p>For Android, click <strong>Build</strong> (or <strong>Build And Run</strong>) in the Build Profiles window and choose an output folder — Unity compiles a single <code>.apk</code> by default, or a Play Store-ready <code>.aab</code> if <strong>Build App Bundle</strong> is ticked in Player Settings. For iOS, Unity doesn't produce an installable file directly: it generates an Xcode project, which you then open in Xcode on a Mac to sign and build to a device.</p>
        </div>
      </div>

      <div class="ar-step">
        <div class="ar-step-body">
          <h3>7.7 Install and Test on a Real Device</h3>
          <p>For Android: enable <strong>Developer Options → USB Debugging</strong> on the phone, connect it by USB, and either use <strong>Build And Run</strong> to install directly, or copy the <code>.apk</code> onto the device and install it manually. For iOS: run the generated Xcode project onto a connected iPhone/iPad and trust the developer certificate on the device (<strong>Settings → General → VPN &amp; Device Management</strong>) before it will open. Point the camera at the hand-drawn marker and confirm it tracks the same way it did in the Editor.</p>
          <p class="ar-why"><strong>Why:</strong> a webcam test in the Editor only proves the marker and content work — it doesn't prove the build itself works. Device quirks (permissions, performance, camera resolution) only show up once it's actually installed and running standalone.</p>
        </div>
      </div>

    </div>
  </details>

</div>


<h2 class="ar-section-title" id="why-these-tools">Why Unity + Vuforia (and not something else)</h2>
<div class="ar-why-tools">
  <p>Unity's mobile-first architecture and gentler C# learning curve make it faster to get running reliably on a phone than Unreal — what matters most for a live demo.</p>
  <p>Vuforia is one of the most established marker-tracking SDKs, predating ARKit/ARCore, and works the same way across Android and iOS from one Unity project.</p>
</div>

<script>
(function () {
  var nodeInfo = {
    root: {
      title: "Augmented Reality",
      text: "Overlays computer-generated content — 3D models, video, text, sound — onto a live view of the real world, usually through a phone or headset camera. Unlike Virtual Reality, which replaces what you see entirely, AR adds to it: the real environment stays visible, with digital elements blended in on top.<br><br>Everything below is a different way of answering: how do we figure out <em>where</em> to put that content, and <em>what</em> do we build it with?"
    },
    sdk: {
      title: "SDK",
      text: "A Software Development Kit (SDK) is a ready-made toolbox for building on a specific platform — a bundle of libraries, APIs, sample code, and documentation, so developers don't have to solve the same low-level problems from scratch. An AR SDK handles image recognition, camera access, and real-time tracking, so a developer only has to decide what content to show and where.<br><br><strong>Why it matters:</strong> without one, recognising and tracking an image through a camera feed in real time would mean writing your own computer-vision pipeline — feature detection, matching, pose estimation — before you could even begin placing 3D content."
    },
    tracking: {
      title: "Tracking Approach",
      text: "How the app figures out where in physical space to anchor digital content. The two branches below — marker-based and markerless — solve this in fundamentally different ways."
    },
    engine: {
      title: "Game Engine",
      text: "A game engine is a software framework that provides the core systems a real-time application needs — rendering, physics, audio, input, and scene management — so developers build the experience itself rather than that infrastructure.<br><br>In an AR pipeline, the game engine is where everything comes together: it runs the SDK's tracking data, renders the 3D content, and handles interaction. The SDK only tells you <em>where</em> the marker is — the engine is what actually draws something on top of it and lets you script what happens next."
    },
    marker: {
      title: "Marker-based AR",
      text: "Content appears when the camera recognises a specific pre-registered image or object — in Vuforia's terms, an <strong>Image Target</strong>. Once detected, the engine tracks its position and orientation continuously, even as the camera or the target moves, and uses that position as the anchor for digital content.<br><br>Under the hood, Vuforia converts the marker image to grayscale and extracts <strong>feature points</strong> — sharp, high-contrast corners and edges — then looks for that same pattern in the live camera feed. This is why Target Manager gives every uploaded marker a <strong>star rating from 0 to 5</strong> as soon as you upload it: it's scoring how trackable the image actually is, before Unity is involved at all. Deterministic and easy to follow live — show the marker, content appears, move it, content follows."
    },
    markerless: {
      title: "Markerless AR",
      text: "Content is placed using the device's own sensors — camera, GPS, accelerometer, depth sensing — to understand surfaces and location, with no pre-registered image needed (SLAM, plane detection, location-based anchoring). This is how ARKit/ARCore \"place an object on this table\" experiences work."
    },
    vuforia: {
      title: "Vuforia",
      text: "An AR SDK from PTC that plugs directly into Unity, providing Image Target / Model Target tracking and exposing that data to Unity's scene graph, so a 3D object can simply be \"childed\" under a tracked target and follow it automatically. One of the most established marker-tracking SDKs, predating ARKit and ARCore, and works the same way across Android and iOS.<br><br>Account, license keys, and documentation live on the Vuforia Developer Portal; the Unity integration itself is distributed as a free package on the Unity Asset Store.",
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
    unity: {
      title: "Unity",
      text: "A mobile-first, cross-platform engine using C# — an estimated 60% of AR/VR content is built on it. Gentler learning curve than Unreal and typically better-optimised for entry-level and mid-range mobile hardware."
    },
    unreal: {
      title: "Unreal Engine",
      text: "Epic's C++ engine, known for a higher graphical ceiling and used heavily in high-end VR and cinematic work. Steeper learning curve than Unity and less mobile-optimised, which matters more for a lightweight, reliably-running live demo than raw visual fidelity."
    },
  };

  var canvas = document.getElementById("ar-tree-canvas");
  var svg = document.getElementById("ar-tree-lines");
  var panel = document.getElementById("ar-detail-panel");
  var nodes = Array.prototype.slice.call(canvas.querySelectorAll(".ar-node"));

  function getParentIds(node) {
    var single = node.getAttribute("data-parent");
    return single ? [single] : [];
  }

  function getNode(id) {
    return canvas.querySelector('.ar-node[data-id="' + id + '"]');
  }

  // The fixed path this tutorial actually uses, shown as a permanently
  // highlighted route (not just on click) so it reads at a glance.
  var pinnedIds = ["root", "sdk", "vuforia", "used-vuforia", "tracking", "marker", "used-marker", "engine", "unity", "used-unity"];

  function drawLines() {
    var canvasRect = canvas.getBoundingClientRect();
    svg.setAttribute("width", canvasRect.width);
    svg.setAttribute("height", canvasRect.height);
    svg.innerHTML = "";

    nodes.forEach(function (node) {
      var toId = node.getAttribute("data-id");

      getParentIds(node).forEach(function (parentId) {
        var parent = getNode(parentId);
        if (!parent) return;

        var a = parent.getBoundingClientRect();
        var b = node.getBoundingClientRect();
        var x1 = a.left + a.width / 2 - canvasRect.left;
        var y1 = a.bottom - canvasRect.top;
        var x2 = b.left + b.width / 2 - canvasRect.left;
        var y2 = b.top - canvasRect.top;
        var midY = (y1 + y2) / 2;
        var d = "M " + x1 + " " + y1 + " C " + x1 + " " + midY + ", " + x2 + " " + midY + ", " + x2 + " " + y2;

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
    // The row-4 "used" nodes are copies of their row-3 originals (same
    // info, just pulled into their own row), so they share one entry.
    var info = nodeInfo[id.replace(/^used-/, "")];
    if (!info) return;

    var html = "<h3>" + info.title + "</h3>";
    if (info.tag) html += '<span class="ar-detail-tag">' + info.tag + "</span>";
    html += "<p>" + info.text + "</p>";
    if (info.link) html += '<a href="' + info.link.href + '" target="_blank" rel="noopener">' + info.link.label + " &rarr;</a>";

    // Fade the old content out, swap it, then fade the new content in —
    // a plain innerHTML swap reads as an abrupt jump cut.
    panel.classList.add("is-fading");
    setTimeout(function () {
      panel.innerHTML = html;
      panel.classList.remove("is-fading");
    }, 120);
  }

  var selectedId = null;

  function applySelection(id) {
    var chain = ancestorChain(id);

    nodes.forEach(function (node) {
      node.classList.toggle("is-active", chain.indexOf(node.getAttribute("data-id")) !== -1);
    });

    Array.prototype.slice.call(svg.querySelectorAll(".ar-tree-line")).forEach(function (line) {
      var isActive = chain.indexOf(line.getAttribute("data-from")) !== -1 && chain.indexOf(line.getAttribute("data-to")) !== -1;
      line.classList.toggle("is-active", isActive);
    });
  }

  function selectNode(id) {
    selectedId = id;
    applySelection(id);
    showDetail(id);

    // On narrow screens the detail panel sits below the whole tree, so a
    // tap can change text that's scrolled out of view — bring it on screen.
    if (window.innerWidth <= 900) {
      panel.scrollIntoView({ behavior: "smooth", block: "nearest" });
    }
  }

  nodes.forEach(function (node) {
    node.addEventListener("click", function () {
      selectNode(node.getAttribute("data-id"));
    });
  });

  // Show something from the moment the page loads, rather than an empty
  // panel — the root node is the natural starting point.
  selectedId = "root";
  applySelection("root");
  showDetail("root");

  function handleResize() {
    drawLines();
    // Redrawing rebuilds every line fresh (no is-active classes), so the
    // active path has to be re-applied or a resize silently clears it.
    if (selectedId) applySelection(selectedId);
  }

  if (typeof ResizeObserver !== "undefined") {
    new ResizeObserver(handleResize).observe(canvas);
  } else {
    window.addEventListener("resize", handleResize);
  }
  window.addEventListener("load", handleResize);
  drawLines();
})();

(function () {
  // Animates every "build-flow" accordion open and closed by resizing the
  // <details> element itself with the Web Animations API, instead of
  // relying on CSS max-height — the native open/close toggle is instant
  // (the browser hides closed content in the same frame it removes the
  // `open` attribute), so there's nothing a CSS transition could animate.
  // Clicks are intercepted so this script drives open/close itself,
  // including manually closing the sibling in the same name="" group
  // (the native grouping behaviour is just as instant as a plain toggle).
  var reduceMotion = window.matchMedia && window.matchMedia("(prefers-reduced-motion: reduce)").matches;
  var items = Array.prototype.slice.call(document.querySelectorAll(".ar-term"));
  var controllers = new Map();

  items.forEach(function (details) {
    var summary = details.querySelector(":scope > summary");
    if (!summary) return;

    var currentAnimation = null;

    function clearInlineStyles() {
      details.style.height = "";
      details.style.overflow = "";
    }

    function open() {
      if (details.hasAttribute("open")) return;
      if (reduceMotion) {
        details.setAttribute("open", "");
        return;
      }
      var startHeight = details.offsetHeight;
      details.setAttribute("open", "");
      var endHeight = details.offsetHeight;
      details.style.overflow = "hidden";
      details.style.height = startHeight + "px";
      if (currentAnimation) currentAnimation.cancel();
      currentAnimation = details.animate(
        { height: [startHeight + "px", endHeight + "px"] },
        { duration: 250, easing: "ease" }
      );
      currentAnimation.onfinish = clearInlineStyles;
      currentAnimation.oncancel = clearInlineStyles;
    }

    function close() {
      if (!details.hasAttribute("open")) return;
      if (reduceMotion) {
        details.removeAttribute("open");
        return;
      }
      var startHeight = details.offsetHeight;
      var endHeight = summary.offsetHeight;
      details.style.overflow = "hidden";
      if (currentAnimation) currentAnimation.cancel();
      currentAnimation = details.animate(
        { height: [startHeight + "px", endHeight + "px"] },
        { duration: 200, easing: "ease" }
      );
      currentAnimation.onfinish = function () {
        details.removeAttribute("open");
        clearInlineStyles();
      };
      currentAnimation.oncancel = clearInlineStyles;
    }

    controllers.set(details, { open: open, close: close });

    summary.addEventListener("click", function (e) {
      e.preventDefault();

      if (details.hasAttribute("open")) {
        close();
        return;
      }

      var groupName = details.getAttribute("name");
      if (groupName) {
        items.forEach(function (other) {
          if (other !== details && other.getAttribute("name") === groupName && other.hasAttribute("open")) {
            controllers.get(other).close();
          }
        });
      }
      open();
    });
  });
})();
</script>
