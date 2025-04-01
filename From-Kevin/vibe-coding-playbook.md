



## BRD PROMPT

```markdown
You are a Senior Product Manager. Create a comprehensive Business Requirements Document (BRD) based on the high-level specs below.

<SPECS GO HERE>

Follow these steps:

1. **Stakeholder & User Analysis (RACI Matrix + User Personas)**
   - Identify key stakeholders and their roles using a RACI (Responsible, Accountable, Consulted, Informed) matrix.
   - Develop user personas that highlight core needs and pain points.

2. **Value Proposition & Differentiation (Value Proposition Canvas)**
   - Use the Value Proposition Canvas to map out how the product solves user needs and stands out against alternatives.
   - Clearly articulate the unique selling points (USPs).

3. **Business Model & Market Context (Business Model Canvas)**
   - Populate a Business Model Canvas to outline revenue streams, cost structure, partners, and customer segments.
   - Include a brief competitive landscape overview (Porter's Five Forces) to identify major risks or barriers.

4. **Requirements Gathering & Prioritization (MoSCoW)**
   - Translate the high-level specs into clear business requirements.
   - Apply the MoSCoW (Must, Should, Could, Won’t) framework to prioritize these requirements.

5. **Risk & Assumption Analysis (SWOT + Risk Register)**
   - Conduct a mini-SWOT (Strengths, Weaknesses, Opportunities, Threats) analysis to anticipate challenges.
   - Maintain a risk register with mitigation plans for top critical risks.

6. **Success Metrics & KPIs**
   - Propose quantifiable success metrics (e.g., user adoption rate, revenue targets, NPS, etc.).
   - Link each requirement to specific KPIs.

7. **Next Steps & Timeline**
   - Outline high-level milestones and a proposed timeline, factoring in any known dependencies or constraints.

Deliver a final BRD that integrates all these elements in a clear, cohesive format, suitable for both executive review and technical hand-off.
```

## PRD Prompt

```markdown
You are a Senior Product Manager. Create a comprehensive Product Requirements Document (PRD) based on the business requirements below.

<BRD GOES HERE>

Follow these steps:

1. **Feature Definition & Prioritization (Kano Model)**
   - Break down the business requirements into specific features.
   - Use the Kano Model to classify features (Basic, Performance, Excitement).

2. **Functional & Non-Functional Requirements**
   - For each feature, define functional requirements (what the feature does).
   - Outline non-functional requirements (performance, security, scalability, compliance) in detail.

3. **User Workflows & Journeys (User Story Mapping)**
   - Construct detailed user journeys by mapping each feature to user goals and tasks.
   - Identify potential bottlenecks or friction points in the user flow.

4. **Technical Feasibility & Architecture (Conceptual Architecture Diagram)**
   - Propose a high-level architecture diagram (e.g., microservices vs. monolith, cloud components, APIs).
   - Discuss technical constraints or dependencies.

5. **Acceptance Criteria (Gherkin Syntax)**
   - Provide acceptance criteria for each feature in a clear “Given-When-Then” format (or a similar structured approach).
   - Ensure each requirement has a testable outcome.

6. **Release Strategy & Timeline (Incremental Roadmap)**
   - Outline how features will be rolled out over multiple releases.
   - Indicate any dependencies, gating factors, or parallel workstreams.

7. **Risk Management & Assumptions (RAID Log)**
   - Maintain a RAID (Risks, Assumptions, Issues, Dependencies) log.
   - Provide mitigation strategies for key risks.

Generate a final PRD that synthesizes these frameworks into a single, detailed product specification ready for development teams.
```
## CREATING THE STORIES

```markdown
  You are a Senior Product Manager. Create a detailed list of one-story-point user stories based on the following Product Requirements Document (PRD).

<PRD GOES HERE>

Follow these steps:

1. **Epic & Feature Breakdown (User Story Mapping)**
   - Identify the major epics or features from the PRD.
   - Break each feature down into granular steps that can be completed in a single day or less.

2. **User Stories (INVEST Criteria)**
   - Write each user story following the INVEST model (Independent, Negotiable, Valuable, Estimable, Small, Testable).
   - Use the format: “As a [type of user], I want [action], so that [benefit].”

3. **Acceptance Criteria (Clear & Testable)**
   - Provide acceptance criteria for each user story, ensuring it is testable and unambiguous.
   - Example format: “Given [context], when [action], then [expected result].”

4. **Prioritization & Sequencing (WSJF or RICE)**
   - Apply a lightweight prioritization framework (e.g., Weighted Shortest Job First (WSJF) or RICE) to order stories.
   - Include a brief explanation of priority rankings.

5. **Dependency Identification**
   - Note any inter-story or external dependencies.
   - Indicate if certain stories must be completed before others can start.

6. **Quality & Testing Considerations (Definition of Done)**
   - Outline a Definition of Done that includes code review, testing, and documentation updates.
   - Ensure each story can be accepted independently once its criteria are met.

7. **Roadmap Integration**
   - Map the final list of one-story-point stories into sprints or iterations.
   - Clarify how these stories align with the overall release timeline and milestones.

Produce a final, neatly categorized list of one-story-point user stories with acceptance criteria and priorities, ready for a development team to start work immediately.
```
## Convert Stories to Markdown
  ```markdown
  Create a very very very detailed markdown checklist of all of the stories for this project plan, with one-story-point tasks (with unchecked checkboxes) that break down each story. It is critically important that all of the details to implement this are in this list. Note that a very competent AI Coding Agent will be using this list to autonomously create this application, so be sure not to miss any details whatsoever, no matter how much time and thinking you must do to complete this very challenging but critically important task.
```

## TASKS PROMPT

```markdown
cursor-tasks.md Go through each story and task in the cursor-tasks.md file. Find the next story to work on. Review each unfinished task, correct any issues or ask for clarifications (only if absolutely needed!). Then proceed to create or edit files to complete each task. After you complete all the tasks in the story, update the file to check off any completed tasks. Run builds and commits after each story. Run all safe commands without asking for approval. Continue with each task until you have finished the story, then stop and wait for me to review. 
```

## UI UX Rubric
```markdown
| Category                   | Description | A                                                                                                                              | B                                                                                                                              | C                                                                                                                          | D                                                                                                                    | F                                                                                                                       |
| -------------------------- | ----------- | ------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| **Color Palette**          | Weight: 1x  | Colors are masterfully integrated, perfectly reflecting the brand and balancing contrast for optimal usability.                | Colors are thoughtfully selected, support brand identity, and maintain a mostly consistent visual hierarchy.                   | A serviceable color scheme is present, though minor inconsistencies or contrast issues reduce overall effectiveness.       | Colors are partially aligned with the brand but fail to follow best practices in contrast or hierarchy.              | Colors are chosen at random, creating visual confusion and lacking any cohesive theme or brand alignment.               |
| **Layout & Grid**          | Weight: 1x  | Grid usage is expertly executed, ensuring balanced spacing, alignment consistency, and a crisp, professional structure.        | A purposeful grid strategy creates a cohesive layout; minor alignment or spacing issues may still be noticed.                  | Layout generally follows a grid, though some elements deviate; overall structure is acceptable but not optimal.            | Some grid principles are followed, but spacing is inconsistent and visual alignment suffers in key sections.         | No clear structure or grid system in place, resulting in a disorganized and hard-to-navigate layout.                    |
| **Typography**             | Weight: 1x  | Typography is outstanding, with well-chosen fonts, impeccable kerning, and a clean hierarchy that enhances user engagement.    | Typography choices reflect a solid visual hierarchy and balanced kerning; minor refinements may further improve readability.   | Typography is functional with moderately consistent styles, though headlines, body text, and spacing could be refined.     | Font selection is somewhat appropriate but lacks clear organization; kerning and leading inconsistencies persist.    | Font choices are erratic or unreadable, with rampant inconsistencies in size, weight, or familial styles.               |
| **Hierarchy & Navigation** | Weight: 1x  | Flawless content hierarchy with intuitive navigation that effortlessly guides users to core features and information.          | Content levels are well-defined, and primary navigation is accessible; minor tweaks could enhance usability further.           | A straightforward hierarchy is established, though key actions or navigation items could be more prominently displayed.    | Some attempt at prioritizing content is visible, yet users may struggle to locate important features easily.         | Information is scattered without clear importance levels; navigation elements are unrecognizable or absent.             |
| **Accessibility**          | Weight: 1x  | Fully meets or exceeds accessibility best practices, ensuring all users can easily interact with and understand the dashboard. | The design largely complies with accessibility standards; minor improvements could include more robust testing or refinements. | Basic accessibility measures are present, though certain features like keyboard navigation or ARIA tags may be incomplete. | Some attempts to address accessibility are made, yet many crucial guidelines (e.g., color contrast) remain unmet.    | Design disregards accessibility guidelines altogether, using low contrast, illegible fonts, and no accessible patterns. |
| **Spacing & Alignment**    | Weight: 1x  | A perfectly balanced layout with deliberate spacing; every element is precisely aligned for maximum readability.               | Thoughtful use of white space and alignment creates a clean layout with only minor areas needing adjustment.                   | Spacing and alignment are mostly consistent, though certain sections need refinement to enhance clarity.                   | Some uniformity in spacing is emerging, but inconsistent alignment detracts from legibility and overall visual flow. | Visual clutter dominates due to no consistent margins, padding, or alignment, making the interface look unfinished.     |
```

 
