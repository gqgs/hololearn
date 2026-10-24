# hololearn

*A shared holodeck for learning, experimentation, and social interaction.*

<img width="1672" height="941" alt="image" src="https://github.com/user-attachments/assets/484d7333-0634-4bbe-ac01-2fa5a9c31af0" />

**Status:** Concept / Backlog  
**Priority:** Low — revisit after higher-priority projects  
**Initial platform:** Browser (Three.js)  
**First prototype:** Chaos Lab — Nonlinear Dynamics

## 1. Vision

What would education look like 1,000 years from now if classrooms could leverage virtually unrestricted simulation capabilities?

This project explores that question by building a browser-based, multiplayer learning environment where concepts become interactive worlds.

Instead of recreating traditional classrooms with desks, projectors, and blackboards, we envision a **reconfigurable shared simulation space** where students can directly observe, manipulate, and experiment with the subjects they're studying.

Think **VRChat meets a university meets Star Trek's holodeck**, with AI-powered instructors and classmates.

The central idea:

> **A classroom should be able to become the thing being taught.**

Students shouldn't merely watch someone explain a dynamical system. They should be able to enter its phase space, perturb initial conditions, manipulate parameters, and observe its evolution alongside other students.

The goal is to create an environment where people genuinely learn useful subjects while enjoying the social experience of learning together.

## 2. Core Design Principles

### 2.1. Subjects Are Places

Treat subjects as explorable environments rather than collections of videos or documents.

Examples:

- **Nonlinear dynamics:** Explore attractors, bifurcations, phase spaces, and coupled oscillators.
- **Physics:** Visualize electromagnetic fields, orbital mechanics, thermodynamics, and wave propagation.
- **Mathematics:** Manipulate functions, geometric transformations, vector spaces, and mathematical structures.
- **Computer science:** Explore algorithms, data structures, execution models, and distributed systems.
- **History:** Navigate reconstructed historical environments and examine causal relationships.
- **Biology:** Explore cellular processes, evolution, molecular structures, and ecosystems.

Each environment should offer capabilities that conventional teaching materials cannot easily provide.

### 2.2. Interactive Laboratories, Not Virtual Theaters

Three-dimensional environments must provide educational value beyond visual novelty.

Students should be able to:

- Manipulate parameters and observe consequences.
- Visualize normally invisible properties and relationships.
- Freeze, rewind, accelerate, and replay simulations.
- Compare alternative hypotheses and model configurations.
- Explore phenomena at different spatial and temporal scales.
- Collaboratively solve problems.

Avoid using 3D merely to display conventional videos or presentations. When a 2D representation communicates something more effectively, use it.

### 2.3. Navigable Levels of Abstraction

Understanding frequently requires translating between different representations of the same concept.

Environments should support transitions between:

**Physical intuition ↔ Simulation ↔ Visualization ↔ Equations ↔ Formal reasoning**

For example, a pendulum lesson could connect:

1. An interactive physical pendulum.
2. Its differential equations.
3. A phase-space representation.
4. Numerical solutions and trajectories.
5. Stability analysis and bifurcations.

The goal is to make connections between representations directly observable.

### 2.4. Social Learning Is a First-Class Feature

The environment is not only a simulator. It is a shared space for inquiry.

Students should be able to attend lessons together, ask questions, collaborate on experiments, exchange explanations, and develop relationships through recurring interactions.

The experience should be valuable alone but improve meaningfully with other participants.

This includes support for:

- Human students joining shared sessions.
- Clearly identified AI classmates that populate otherwise empty environments.
- AI instructors and teaching assistants.
- Shared experiments, exercises, and discussions.
- Scheduled classes and on-demand learning.

NPCs should maintain consistent identities and constrained knowledge states, including misconceptions and areas of expertise. They should not behave as omniscient assistants disguised as ordinary students.

### 2.5. Simulations Must Be Scientifically Meaningful

Prefer real mathematical models and validated simulation logic over purely decorative animations.

When approximations are necessary, expose their limitations.

Educational correctness takes precedence over visual spectacle.

A simulation should help students understand why a phenomenon occurs, not merely produce an attractive depiction of it.

### 2.6. AI Supports Teaching Without Replacing Ground Truth

Use AI to generate, adapt, and present educational material, facilitate discussions, and animate believable characters.

Take inspiration from effective pedagogical methods used by educators such as Richard Feynman, Gilbert Strang, and Steven Strogatz without impersonating them.

Crucially, separate the instructor's **educational knowledge** from their **presentation and personality**.

Initially, prefer preconstructed and validated lessons over fully improvised AI lectures.

Real-time AI should be introduced selectively, particularly for questions, explanations, and contextual character interactions.

## 3. Proposed Architecture

The platform should separate educational content, simulation logic, presentation, and social interactions.

### Semantic Lesson Representation

Define lessons as structured, reusable content rather than fixed videos.

A lesson may contain:

- Learning objectives and prerequisites.
- Concepts, equations, and explanations.
- Simulation definitions and parameters.
- Timeline events and presentation instructions.
- Interactive demonstrations and exercises.
- Assessment questions and expected outcomes.
- Optional instructor dialogue and character behavior.

This representation could eventually integrate with existing programmatic explainer-video tooling.

### Simulation and Rendering

Use Three.js for browser-based visualization and interaction.

Where practical, implement simulations independently of their rendering so the same models can support different visualizations, experiments, and educational contexts.

### Multiplayer and Shared State

Provide synchronized sessions where participants can see and manipulate the same educational environment.

The shared state should describe simulation parameters, user actions, and lesson events rather than requiring synchronized video streams.

Personal exploration, shared experiments, and synchronized instruction may eventually require distinct time-control policies.

### AI Agent Layer

Support instructors, classmates, and teaching assistants with defined roles, knowledge boundaries, and persistent behavioral characteristics.

Start with scripted behavior and constrained interactions. Introduce more autonomous agents only when their value can be demonstrated.

## 4. Initial MVP — Chaos Lab

Build **one shared interactive environment** for teaching introductory nonlinear dynamics.

The MVP should validate the educational and social experience without attempting to build an entire school.

### Core Features

- [ ] Browser-based Three.js environment accessible without installation.
- [ ] Simple navigation and recognizable participant avatars.
- [ ] Real-time multiplayer with basic text communication.
- [ ] A shared interactive mathematical visualization.
- [ ] One short, structured lesson with an instructor.
- [ ] A small number of clearly identified AI classmates with scripted behavior.
- [ ] An individual or collaborative exercise.
- [ ] A simple assessment of conceptual understanding.
- [ ] A way to enter an available session without requiring a large active community.

### First Lesson: Understanding Chaos

Use the logistic map as the initial educational experiment:

\[
x_{n+1}=rx_n(1-x_n)
\]

Students should be able to:

1. Modify the parameter \(r\).
2. Observe how trajectories change.
3. Compare nearby initial conditions.
4. Explore period-doubling bifurcations.
5. Discover the distinction between deterministic dynamics and long-term predictability.

The instructor should connect the experiment to mathematical explanations and guide students through a short exercise.

**Potential follow-up experiments:**

- Lorenz attractor and sensitive dependence.
- Damped and driven pendula.
- Feigenbaum universality and renormalization.

These are extensions, not prerequisites for the initial MVP.

## 5. Future Directions

Potential additions after validating the initial experience:

- Multiple subjects and explorable learning environments.
- Scheduled courses, cohorts, and recurring classmates.
- Real-time conversational AI instructors.
- Voice communication and expressive NPC animation.
- Persistent individual learning progress and adaptive instruction.
- Multiplayer research laboratories and collaborative problem-solving.
- Procedural generation of lessons from validated educational sources.
- Semantic reconstruction of existing educational lectures.
- Exams, office hours, study groups, and academic progression.
- Virtual campuses connecting different learning environments.
- Support for VR and other immersive interfaces.

The platform should remain browser-first and accessible without specialized hardware.

## 6. Open Questions

### Educational Experience
- How much lesson structure should be predetermined versus generated dynamically?
- How do we measure genuine learning rather than engagement alone?
- What forms of collaboration provide measurable educational benefits?

### Social Design
- How should scheduled classes coexist with on-demand sessions?
- How can we maintain social density with a small user base?
- How should AI classmates participate without displacing human interaction?

### Simulation Architecture
- What is the minimal reusable interface for defining educational simulations?
- How should semantic lesson events control the environment?
- Which simulation state must be authoritative and synchronized?
- How should local experimentation interact with shared lesson time?

### AI and Content
- How should we validate AI-generated educational material?
- What are the costs and limitations of real-time multimodal AI?
- How can NPC knowledge and misconceptions remain internally consistent?
- What licensing and consent requirements apply when adapting existing lectures or teaching styles?

### Platform
- How much can run entirely inside the browser?
- What is the minimum server infrastructure for multiplayer?
- What moderation, privacy, and safety features will be needed for public sessions?

## 7. Success Criteria

The first prototype should answer three questions:

**1. Educational value:** Can a participant demonstrably understand something after interacting with the environment that they did not understand beforehand?

**2. Social value:** Does learning alongside other participants provide a meaningful advantage over using the same simulation alone?

**3. Reusability:** Can the technical architecture support another lesson without rebuilding the entire environment?

Visual quality and world size are secondary to these questions.

## 8. Scope and Prioritization

This is an exploratory, low-priority project.

**Do not begin full implementation until existing higher-priority projects have progressed sufficiently.**

When development begins:

1. Prototype one educational simulation.
2. Validate that interacting with it teaches something useful.
3. Add shared multiplayer interactions.
4. Integrate the minimal instructor and NPC behaviors.
5. Test the complete lesson with actual learners.
6. Expand only if the results justify further investment.

Avoid premature investment in large campuses, complex character systems, sophisticated animation, procedural content generation, or extensive infrastructure.

Reuse existing tools and infrastructure where practical.

---

## Guiding Philosophy

The project is not primarily about reproducing traditional schooling in a virtual world.

It is about exploring **what education becomes when the environment itself can represent, simulate, and transform the concepts being taught.**

A future classroom should be a place where invisible structures become observable, abstract concepts become manipulable, and understanding becomes a shared activity.

**Subjects are places. Learning is exploration. The classroom is a programmable world.**
