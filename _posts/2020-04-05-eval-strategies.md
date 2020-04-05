---
title:  "Evaluation Strategies for HCI Toolkit Research"
isnotes: "yes"
isdate: 1
permalink: notes/toolkit_evaluation_notes
excerpt: A paper by Steven Houben et al. that presents an interesting compilation of potential evaluation methods for HCI projects.
---

> Ledo, D., Houben, S., Vermeulen, J., Marquardt, N., Oehlberg, L., & Greenberg, S. (2018, April). **Evaluation strategies for HCI toolkit research**. In *Proceedings of the 2018 CHI Conference on Human Factors in Computing Systems* (pp. 1-17).

Find the paper on the [ACM DL](https://dl.acm.org/doi/abs/10.1145/3173574.3173610) or [here](https://stevenhouben.be/pubs/EvaluationCHI2018.pdf).

# Introduction

Toolkit research is important, but there's no clear definition of what it means to 'evaluate' toolkits.

The authors survey a range of toolkit research papers to describe and discuss the various evaluation methods that have been employed in the past.

> "... how toolkit researchers collectively derive **what** evaluation methods are useful, **when** they are appropriate and **how** they are performed."

# Background

## What is a Toolkit?

Toolkits are a way to encapsulate interface design concepts for programmers (Greenberg, 2007).

More generally, toolkits are frameworks for thinking about software or hardware design and research.

The authors define toolkits as *"generative platforms designed to create new interactive artifacts, provide easy access to complex algorithms, enable fast prototyping of software and hardware interfaces, and/or enable creative exploration of design spaces."*

The [Microinteraction Toolkit](https://info-design-lab.github.io/microinteractions/) from Venkat sir's module on Interface Design is one relatable example. 

## Why do HCI Researchers Build Toolkits?

Five major goals:

1. Reducing Authoring Time and Complexity
2. Creating Paths of Least Resistance
3. Empowering New Audiences
4. Integrating with Current Practices and Infrastructures
5. Enabling Replication and Creative Exploration

## The issues with Toolkit Evaluation

The lack of a clear definition for what Toolkit evaluation means has led to difficulties in publishing toolkit-related work, due to the general perception and expectations associated with HCI project evaluation.

Toolkits are more open-ended than systems that solve a particular problem. Toolkits can be used across a range of contexts, but this makes it harder to thoroughly explore/evaluate the large space of potential applications.

> To read: Dan R. Olsen, Jr.. 2007. Evaluating user interface systems research.

# This Review

## Dataset

Keyword search resulting in 58 papers from major ACM venues (CHI, UIST, DIS, Ubicomp, TEI, MobileHCI).

10 additional 'exemplary' papers published elsewhere.

The claim is that this is a representative sample of toolkit research.

## Analysis

The authors used a range of techniques. They began by open-coding a subset of the sample, after which focused coding was performed on the evaluation methods for the whole sample. Iterative coding led to the generation of categories and eventually **4 overarching evaluation strategies**:

1. Demonstration
2. Usage
3. Technical Evaluation
4. Heuristic Evaluation

# Evaluation Strategies

I've tried to make this section less toolkit-specific to help with seeing how these categories might apply to a lot of other work. However, the insights do come solely from a toolkit-based review, and the intent is not to generalise the findings.

## 1. Demonstration

Popular example: Douglas Engelbart and the Mouse.

- Precisely and effectively communicating new ideas or concepts.
- Show what something might support, and also how users might work with it.
- Discuss the transferability of an idea to neighbouring problem spaces.

How do users explore the *Threshold*, *Ceiling*, and *Design Space* associated with an idea/toolkit.

### 1.1 Novel Examples

> What is important is that these examples detail how the features, design principles, and building blocks enable new applications.

### 1.2 Replicated Examples

> These examples demonstrate how toolkits reduce complexity, effort and development time for recreating applications. Further, replication can demonstrate how the toolkit generalizes across a variety of examples

### 1.3 Case Studies

>  ... they convincingly demonstrate the toolkit’s application within complex scenarios as opposed to small example applications.

### 1.4 Exploration of a Design Space

> ... systematic way of trying to map out possible design boundaries. Although exploring the full design space is often impossible, examples demonstrate the breadth of designs enabled by the toolkit.

### 1.5 'How To' Scenarios

> ... can demonstrate a step-by-step breakdown of how a user creates a specific application

### Challenges while evaluating by demonstration

- Demos do a good job of showing 'what' can be done, but are often less convincing in their arguments about 'who' would use such a thing and 'why'
- It is difficult to demonstrate external validity without showing that others can use the system in the manner that the authors do
- One may demonstrate future applications today, and therefore, a target group of users may not exist at the moment
- The systems and setups associated with toolkits may be difficult to recreate by a more general user base

### Opportunities

- Provide Rationale for Toolkit Design and Examples
- Express first-hand experience
- Challenges identified in prior work can be used as motivations for demos
- Formative Studies: Interviews about the context in which a toolkit might be deployed
- Discuss Boundaries and Underlying Assumptions: To avoid sounding like an out-and-out sales pitch

## 2. Usage

Usage clarifies the question of 'Who can use the toolkit', and represents the idea of more conventional user evaluations.

Most Usage-based evaluations are informed by user studies, and can clarify whether a toolkit is:

1. Conceptually Clear
2. Easy to Use
3. Valuable to the Audience

'Usability' is often evaluated in HCI projects, and so Toolkit research also attempts to do so.

'Utility' is also important, and concerns the audiences' interest or outcomes.

A more abstract metric is 'Use', where researchers are interested in the question of how a toolkit is being used more than usability/utility.

### 2.1 Five Ways to Conduct Usage Studies:

### 2.1.1 Usability Study

> When toolkits claim that they facilitate a process, authors may choose to carry out a usability study. This can help identify issues with the toolkit, using measures of participants’ performance (e.g. time, accuracy), and further qualitative feedback

### 2.1.2 A/B Comparisons

> One way to suggest improvement over existing work is to compare the new toolkit to a baseline. Baselines include not having a toolkit, or working with a different toolkit.

### 2.1.3 Walkthrough Demonstrations

> A walkthrough demonstration consists of showing the toolkit to a potential user and gathering their overall impressions.

### 2.1.4 Observation

> Direct observation helps inform how users approached the toolkit to solve problems ranging from closed tasks requiring a specific solution to a given problem, to open tasks where participants formulate the problem and use the toolkit to create their own solution.

### 2.1.5 Take-Home Studies

> Some external validity can be acquired by conducting experiments outside lab settings. While it is difficult to deploy a toolkit before it has gained broader acceptance, researchers can provide their toolkit to “early adopter” participants. Participants receive the toolkit (and all necessary components and documentation) to create any applications of their liking within a given timeframe (e.g. a week)

### 2.2 Two Ways to Elicit User Feedback

### 2.2.1 Questionnaires

In the case of toolkit research, Likert Scale measures are predominantly used.

> Likert scales provide a non-parametric value pertaining to a question. The questions can later be analyzed either through non-parametric tests or by examining the median values.

### 2.2.2 Interviews

> ... ask participants about their experiences or challenges performing their tasks, which provided the authors with insight in terms of processes, successes and shortcomings of the toolkit.

### Challenges

- Usability may distract from conceptual idea, more exploratory opportunities
- Usability on 'prototypes' is problematic because of the inherent low-fidelity of prototypes in comparison to commercial products
- Controlled experiments are limited in scope, only some tasks are considered
- Real-world usage is still suspect, even in the case of take-home studies
- Usage always tests with novice users
- Students are often stand-ins for real users

### Opportunities

- Bringing Utility into the picture
- Selecting Tasks and Measures Carefully
>... we argue that rigour is only of value if truly representative tasks and appropriate measures are used
- Recognising the Consequences of Audience Choice

## 3. Technical Performance

Evaluating Technical Performance answers the question of 'how well' a toolkit works. This is often complementary to Demos or Usage Evaluations.

> The goal of studying technical performance is to benchmark, quantify or analyze the toolkit or its components to verify or validate the performance. (...) These measures show whether it meets basic usage standards (threshold), or if there are improvements over the state-of-the-art. Technical benchmarks can push the boundaries of the toolkit to show when it no longer works as expected.

### 3.1 Benchmarking Against Thresholds
> For certain types of applications, systems and algorithms, there are known, tested or desirable thresholds that serve as baseline to verify that a system meets a commonly accepted standard of use (e.g. accuracy, latency).

### 3.2 Benchmarking Against State-of-the-Art
> Benchmarking often looks for improvements over existing state-of-the-art solutions. This comparison approach is often similar to algorithm contributions in HCI, where a toolkit’s capabilities are compared against well-known baselines, or the best algorithm for that purpose.

### Challenges

- Technical Evaluations don't work very well in isolation from other techniques.
- The importance of certain benchmarks may be unclear
- Due to the fast-moving nature of HCI research, it may be difficult to re-implement technical baselines
- Baselines themselves may not exist in some cases

### Opportunities

- **Contextualize and State Technical Limitations:** HCI goals and commercial goals are often not the same
- **Risky Hypothesis Testing:** Actively stress-test the toolkit's abilities and claims
- **Open Source and Open Access**: Facilitate comparison and replication by providing access to methods, code and data
- **Discuss Implicit Baselines:** To clarify the importance of certain benchmarks to unfamiliar audiences

## 4. Heuristics

> Heuristics in HCI are typically associated with Nielsen et al.’s discount method to informally assess inter-face usability

This method does not require human participants, but still brings up some aspects of utility.

> "create a vocabulary for experts to make early judgements when designing, and to articulate decisions later." - Cognitive Dimensions of Notation

Heuristics can and should be omitted when appropriate, as some may be more important than others, while others may not even be relevant.

### 4.1 Checklists

> The checklist approach consists of selecting a heuristic evaluation approach and going through individual heuristics one at a time. In doing so, authors can reflect on whether the toolkit satisfies the heuristic or not, and the ex-tent of meeting it.

### 4.2 Discussion

Use Heuristics as reflection points in the discussion section of a Toolkit paper, in order to better understand the limitations of a toolkit, and identify issues that are still to be addressed.

### 4.3 Basing Usage Studies on Heuristics

> Heuristics can help determine what is useful to evaluate.

### Challenges

- The danger of falling into self-fulfilling prophecies, or excluding heuristics that don't support a narrative
- Heuristics may not always be relevant
- Authors often have implicit bias, and they are the ones who usually conduct a heuristic evaluation
- External heuristic evaluation is difficult for toolkits given their inherent complexity

### Opportunities

- **Using Heuristics as Design Guidelines:** Can inform design as well as help evaluate, by helping authors be more mindful of best practices
- **Using Heuristics to inform techniques from Prior Types:** Using the language of heuristics to better understand how other demos or usage studies stem from certain heuristics.
- **Transparency:** Authors should be more clear about which heuristics are being used and which are being omitted, to "increase transparency and possibly expose gaps in their evaluation".

# Discussion

> Rather than considering some methods as better than others, we believe that it is more important to use methods that best match the claims of the toolkit paper, and what that evaluation method might yield.

> While demonstrations are often not considered a formal evaluation, they show evidence through “research by design” and are highly effective in communicating the principles, concepts and under-lying ideas of the toolkit.

> Despite Greenberg and Buxton’s warning that usability studies can be ‘harmful’ if not applied to the right problem, many papers in our sample performed usability studies to evaluate complex toolkits. Such studies may employ artificial tasks, small sample sizes, and non-representative user groups to evaluate a small subset of paths offered by the toolkit. While still yielding results, these are limited to the specific task, and rarely generalize to the entire toolkit capabilities, development paths, broader audience that would use the toolkit, and the context around toolkit learning and use.

**It is important to not conflate Successful Evaluation with the Success of a Toolkit**

# Limitations

- Not a complete overview of toolkit research - only considered relatively recent research work, and also only looked at the contributions contained within single papers
- The authors are familiar with the design of toolkits, and some amount of bias may have crept in

