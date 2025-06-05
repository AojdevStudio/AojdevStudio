# AI Guardrails Template & Prompting System

## PRD Template for Technical Issues

### Document Information
- **Issue ID:** [ISSUE-ID]
- **Title:** [Brief, descriptive title]
- **Priority:** [Critical/High/Medium/Low]
- **Due Date:** [Based on priority: Critical=1 day, High=2-3 days, Medium=1 week, Low=2-3 weeks]
- **Created:** [Date]
- **Author:** [Name]
- **Status:** [Draft/In Review/Approved]

### Executive Summary
[One paragraph describing the issue, its impact, and the proposed solution approach using AI guardrails]

### Background and Strategic Fit
#### Current State
- [Specific technical issues identified]
- [Impact on codebase/system]
- [Risk factors if not addressed]

#### Desired State
- [Specific, measurable outcomes]
- [Quality improvements expected]
- [Risk mitigation achieved]

### Goals and Success Metrics
#### Goals
1. [Primary technical goal]
2. [Secondary quality goal]
3. [Developer experience goal]

#### Success Metrics
1. **Primary:** [Quantifiable metric - e.g., 100% of X replaced]
2. **Primary:** [Quality metric - e.g., all checks pass]
3. **Secondary:** [Regression metric - e.g., no functionality loss]

### Detailed Requirements
#### 1. [Main Technical Requirement]
##### 1.1 Affected Files
- [List specific files needing changes]
- [Risk level assessment for each]

##### 1.2 Technical Standards
- [Specific guidelines for implementations]
- [Quality requirements]
- [Documentation requirements]

#### 2. [Secondary Technical Requirement]
##### 2.1 [Specific sub-requirement]
##### 2.2 [Implementation guidelines]

### AI Guardrails Implementation Strategy

#### 1. File-Level Constraints
- **One file per AI session rule**
- **Risk-based order:** Start with test files, end with core components
- **Dependency awareness:** Process leaf nodes before dependencies
- **Maximum scope:** Limit to [X] lines of changes per session

#### 2. Change Type Isolation
- **Separate concerns:** Handle different types of fixes in separate sessions
- **Auto-fixable first:** Apply automated fixes before manual changes
- **Validation gates:** Test each type of change independently

#### 3. AI Safety Prompts (See Prompting System Below)
- **Constraint setting prompts**
- **Impact assessment requirements**
- **Scope limitation directives**
- **Validation checkpoints**

#### 4. Incremental Validation Protocol
- **Per-file testing:** Validate each file before proceeding
- **Regression checks:** Run relevant tests after each change
- **Quality gates:** Verify standards compliance at each step
- **Rollback readiness:** Maintain easy revert capability

### Implementation Plan
#### Phase 1: Analysis and Low-Risk Files (Day 1)
- [Specific analysis tasks]
- [Low-risk file identification and fixes]
- [Initial validation]

#### Phase 2: [Medium Risk Changes] (Day 2)
- [Specific implementation tasks]
- [Validation requirements]

#### Phase 3: [High Risk Changes and Final Validation] (Day 3)
- [Core component changes]
- [Final validation and testing]
- [Documentation updates]

### Technical Considerations
- **Compatibility:** [Specific compatibility requirements]
- **Performance:** [Performance impact considerations]
- **Maintainability:** [Long-term maintenance requirements]

### Risks and Mitigation
| Risk | Impact | Likelihood | Mitigation |
|------|--------|------------|------------|
| [Specific technical risk] | [High/Medium/Low] | [High/Medium/Low] | [Specific mitigation strategy] |

### Timeline and Milestones
| Milestone | Description | Completion |
|-----------|-------------|------------|
| [Phase 1 Complete] | [Specific deliverables] | Day 1 |
| [Phase 2 Complete] | [Specific deliverables] | Day 2 |
| [Final Validation] | [Specific deliverables] | Day 3 |

### Acceptance Criteria
- [ ] [Specific, testable criterion]
- [ ] [Quality standard met]
- [ ] [No regression verified]
- [ ] [Documentation complete]

---

## AI Prompting System

### System Prompt Template
```xml
<role>
You are an expert software engineer working on a technical debt resolution project. Your task is to make precise, minimal changes to improve code quality while avoiding large refactoring jobs.
</role>

<constraints>
- You may only modify ONE file at a time
- Maximum 15 lines of changes per response
- Must identify import dependencies before suggesting changes
- Always perform impact assessment first
- Never suggest changes that affect more than 3 related files
</constraints>

<process>
1. Analyze the specific file provided
2. Identify dependencies and imports
3. Assess impact of proposed changes
4. Provide minimal, targeted fixes only
5. Explain validation steps required
</process>

<output_format>
<impact_assessment>
List affected files/components
</impact_assessment>

<proposed_changes>
Minimal code changes with line numbers
</proposed_changes>

<validation_steps>
How to verify the changes work
</validation_steps>

<next_file_recommendation>
Safest next file to process
</next_file_recommendation>
</output_format>
```

### Constraint-Setting Prompts

#### Initial Analysis Prompt
```xml
<task>
Analyze the file `[FILENAME]` for [SPECIFIC ISSUE TYPE].
</task>

<constraints>
- Do NOT provide fixes yet
- Focus only on identifying issues
- List files that import from this module
- Assess complexity and risk level
</constraints>

<required_output>
<issues_found>
List with line numbers
</issues_found>

<risk_assessment>
Low/Medium/High with reasoning
</risk_assessment>

<dependencies>
Files that depend on this module
</dependencies>

<recommended_order>
Suggested fix sequence
</recommended_order>
</required_output>
```

#### Implementation Prompt Template
```xml
<task>
Fix [SPECIFIC ISSUE] in `[FILENAME]` following strict constraints.
</task>

<strict_limits>
- Maximum 15 lines of changes
- Do not modify function signatures used elsewhere
- Preserve existing API contracts
- Show only the minimal changes needed
</strict_limits>

<pre_change_verification>
<dependency_check>
Which other files import from this module: [LIST]
</dependency_check>

<api_impact>
Whether this change affects external APIs: [YES/NO]
</api_impact>

<risk_level>
Risk level of the change: [LOW/MEDIUM/HIGH]
</risk_level>
</pre_change_verification>

<required_output>
<exact_changes>
Line-by-line changes with explanations
</exact_changes>

<reasoning>
Reason for each change
</reasoning>

<testing_steps>
Steps to verify the changes work
</testing_steps>

<scope_check>
If the fix requires more than 15 lines, respond with:
"This fix exceeds the 15-line limit. Recommend breaking into smaller steps: [LIST STEPS]"
</scope_check>
</required_output>
```

#### Validation Prompt Template
```xml
<task>
Review the changes made to `[FILENAME]` and verify safety.
</task>

<validation_checklist>
<compatibility>
Do these changes affect any other files?
</compatibility>

<breaking_changes>
Are there potential breaking changes?
</breaking_changes>

<test_requirements>
What tests should be run to verify this works?
</test_requirements>

<next_file>
What's the next safest file to process?
</next_file>
</validation_checklist>

<response_format>
<compatibility_check>
PASS/FAIL with explanation
</compatibility_check>

<test_requirements>
Specific tests to run
</test_requirements>

<impact_verification>
Steps to check for side effects
</impact_verification>

<next_recommendation>
Safest next file and reason
</next_recommendation>
</response_format>
```

### Chain-of-Thought Prompting for Complex Issues

```xml
<task>
Before making any changes to `[FILENAME]`, work through this analysis systematically.
</task>

<thinking>
<step1>
Current State Analysis:
- Analyze current code structure
- Identify the specific issues
- Map out dependencies
</step1>

<step2>
Dependency Impact Assessment:
- List importing files
- Identify external API usage
- Assess breaking change potential
</step2>

<step3>
Minimal Fix Strategy:
- Identify smallest possible change
- Verify it doesn't break contracts
- Ensure it's within 15-line limit
</step3>

<step4>
Validation Planning:
- Specific test requirements
- Compilation checks needed
- Runtime verification steps
</step4>
</thinking>

<implementation>
Now provide the implementation following the constraints above.
</implementation>
```

### Multi-Shot Examples

#### Example 1: Good Constraint Adherence
```
HUMAN: Fix the any types in dashboard-client.tsx

ASSISTANT: I'll analyze dashboard-client.tsx first to understand its dependencies and scope.

**Impact Assessment:**
- Files importing this module: 3 found (dashboard/page.tsx, layout.tsx, index.ts)
- External API surfaces: DashboardClientProps interface
- Risk level: HIGH (core component)

**Issues Found:**
- Line 23: `data: any` in handleResponse function
- Line 45: `config: any` in setupClient function
- Line 67: `event: any` in event handler

**Recommended Approach:**
Start with the lowest impact change - Line 23 handleResponse function.
This is internal to the function and won't affect external APIs.

**Proposed Change (5 lines):**
```typescript
// Before
function handleResponse(data: any) {
  return data.results;
}

// After  
interface ApiResponse {
  results: unknown[];
  status: string;
}

function handleResponse(data: ApiResponse) {
  return data.results;
}
```

**Validation Steps:**
1. Verify TypeScript compilation
2. Test dashboard loading functionality
3. Check that no external imports break

**Next Safest File:** The test file dashboard-client.test.tsx (if it exists)
```

#### Example 2: Proper Scope Limitation
```
HUMAN: Fix all the import issues and type issues in the entire codebase

ASSISTANT: I cannot fix all issues across the entire codebase in one session. This violates our constraint of processing one file at a time with maximum 15 lines of changes.

**Recommended Approach:**
1. Start with one specific file
2. Choose the lowest-risk file first (typically test files)
3. Process in dependency order (leaf nodes first)

**Question for you:**
Which specific file would you like me to start with? I recommend beginning with test files or utility functions that have fewer dependencies.

**Process we'll follow:**
- File 1: [Lowest risk] → Validate → 
- File 2: [Next safest] → Validate → 
- File 3: [Continue in order] → Final validation
```

### Error Recovery Prompts

```xml
<emergency_brake>
If at any point the AI suggests changes that exceed constraints, use this prompt:

<stop_command>
STOP. You've exceeded the constraint limits.
</stop_command>

<required_response>
<constraint_violated>
Identify which constraint was violated
</constraint_violated>

<corrective_action>
Break this into smaller, compliant steps
</corrective_action>

<safe_first_step>
Recommend only the first small step
</safe_first_step>

<safety_explanation>
Explain why this approach is safer
</safety_explanation>
</required_response>
</emergency_brake>
```

### Validation Chain Prompts

```xml
<post_file_validation>
After each file is processed, use this validation prompt:

<task>
Before proceeding to the next file, verify the current changes.
</task>

<validation_requirements>
<compilation_check>
Confirm these changes compile successfully
</compilation_check>

<error_assessment>
List any new errors introduced
</error_assessment>

<issue_resolution>
Verify the specific issue was resolved
</issue_resolution>

<next_file_planning>
Recommend the next safest file to process
</next_file_planning>

<progress_estimation>
Estimate remaining work (number of files/sessions needed)
</progress_estimation>
</validation_requirements>
</post_file_validation>
```

---

## Usage Guidelines

### When to Use This System
- ✅ Technical debt resolution
- ✅ Large-scale refactoring needs
- ✅ Type safety improvements
- ✅ Dependency updates
- ✅ Code quality initiatives

### When NOT to Use This System
- ❌ New feature development
- ❌ Single-file fixes
- ❌ Emergency bug fixes
- ❌ Prototype/experiment code

### Best Practices
1. **Always start with the PRD template** - ensures proper planning
2. **Use system prompts** - sets consistent constraints
3. **Chain prompts logically** - each builds on previous validation
4. **Maintain constraint discipline** - never allow scope creep
5. **Document exceptions** - if constraints must be violated, document why

### Success Indicators
- Issues completed within timeline estimates
- No unexpected side effects or regressions
- Manageable change review sizes
- Consistent code quality improvements
- Reduced developer cognitive load

---

## Customization Notes

This template can be customized for:
- **Different tech stacks** (adjust file types and tools)
- **Team sizes** (adjust review requirements)
- **Risk tolerance** (adjust constraint limits)
- **Project complexity** (adjust phase durations)

The core principles remain: constraint-driven, incremental, validated, and AI-safe.