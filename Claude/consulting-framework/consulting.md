<!-- === WATCHER HEADER START === -->
<!-- File: Claude/consulting-framework/consulting.md -->
<!-- Managed by file watcher -->
<!-- === WATCHER HEADER END === -->
# KC Ventures Consulting Framework: Claude-Based Business Analysis System

## Overview
This framework is part of KC Ventures' consulting methodology, designed to streamline the process of business analysis and solution development. It represents a systematic approach to transforming client survey responses into actionable business insights through Claude-powered automation.

### Framework Purpose
This document serves as a guide for consultants looking to create a Claude project for business analysis. It explains how to manage client surveys effectively by integrating them into the Claude project. When a consultant obtains a completed client survey, they can feed that data into the Claude project, which will then facilitate the creation of valuable tools and insights to assist the client. This AI-driven approach ensures consistency, thoroughness, and efficiency in the consulting process.

### How to Use This Framework
1. Have clients complete the business survey
2. Input survey responses into the Claude project
3. Follow the generated instructions to create customized business solutions
4. Use the output to guide client consultations and implementations

---

# Instructions for Transforming Client Survey into Business Scope Document

## Purpose and Overview
These instructions guide you (the LLM) in converting a completed client business survey into a comprehensive Scope of Business Document. This document will serve two primary purposes:
1. Enable further research into the client's business domain if needed
2. Guide the customization of standard SOP templates to fit the client's specific business needs

## Process Flow

### 1. Initial Survey Processing
- Parse the client's survey responses into distinct categories
- Identify any critical missing information that would impede SOP customization
- Generate follow-up questions for any incomplete or ambiguous answers, specifying exactly what information is needed and why
- Example: "You mentioned compliance requirements but didn't specify which regulations apply. Please clarify which specific standards (e.g., HIPAA, ISO 9001) your business must adhere to."

### 2. Structure Creation
Create a standardized document with the following mandatory sections:

**2.1. Executive Summary**
- Brief overview of the business (1-2 paragraphs)
- Industry classification with specific sub-category if applicable
- Scale of operations (employees, locations, market reach)
- Primary value proposition
- Critical business challenges requiring SOP attention (prioritized)

**2.2. Organizational Structure**
- Departmental breakdown with clear hierarchy
- Key roles and responsibilities relevant to SOP implementation
- Decision-making flow for procedural changes
- Current delegation and approval processes

**2.3. Systems Inventory**
- Existing tools and software platforms (categorized by function)
- Current documentation and SOP status
- Integration points between systems
- Known limitations or pain points in current systems

**2.4. Regulatory Framework**
- Industry-specific regulations affecting operations
- Compliance requirements with citations to specific standards
- Mandatory documentation or record-keeping needs
- Audit requirements or schedules

**2.5. Operational Challenges & Priorities**
- Detailed analysis of each challenge mentioned in the survey
- Root causes identified where possible
- Impact on business metrics or outcomes
- Priority level (Critical/High/Medium/Low) with justification

**2.6. Implementation Considerations**
- Timeline constraints and key deadlines
- Training preferences and existing onboarding processes
- Resource limitations that may affect SOP rollout
- Change management considerations based on company culture

**2.7. Future State Requirements**
- Growth projections and scaling needs
- Planned changes that will affect procedural documentation
- Long-term goals that SOPs should support

**2.8. SOP Customization Roadmap**
- Specific mapping of client needs to SOP modifications
- Clear instructions for adapting standard templates
- Prioritized list of SOPs to develop or customize
- Suggested verification methods for SOP effectiveness

### 3. Data Extraction and Enhancement
For each section:
- Extract direct quotes from the survey when they provide clear, actionable information
- Paraphrase unclear responses while maintaining the client's intent
- Enhance responses with industry-standard terminology where appropriate
- Identify and highlight domain-specific terms that may require further research
- Flag contradictory or ambiguous statements for clarification
- If the survey response is incomplete in a critical area, suggest reasonable assumptions based on the industry while marking them clearly as assumptions

### 4. Machine-Readable Formatting
Format the document for both human readability and machine processing:

```markdown
## [Section Title]

### Client Response (Verbatim)
> Exact client text from survey

### Enhanced Analysis
- Structured interpretation point 1
- Structured interpretation point 2
- Structured interpretation point 3

### SOP Adaptation Instructions
1. Replace [standard section X] with [client-specific information]
2. Add [new procedure] to address [specific client need]
3. Modify [existing checklist] to include [client-specific requirements]

### Research Needs
- [ ] Verify [specific industry regulation]
- [ ] Investigate typical [industry-specific process]
```

### 5. Industry-Specific Considerations
- For each identified industry, include relevant baseline knowledge about:
  - Common compliance frameworks
  - Standard operational models
  - Industry benchmarks for procedures
  - Typical tools and software ecosystems
- Identify areas where specialized knowledge is required, with specific questions to research

### 6. Document Enrichment
- Include relevant URLs to industry resources, regulatory bodies, or software documentation
- Generate a glossary of industry-specific terms used in the document
- Create an appendix mapping client terminology to standard industry terms
- Provide a list of recommended SOP templates that would be most relevant based on the client profile

### 7. Finalization and Quality Assurance
- Check for logical consistency across sections
- Ensure all critical business needs identified in the survey are addressed
- Verify that all customization instructions are clear and actionable
- Confirm that assumptions are clearly marked as such
- Generate a 1-page executive brief summarizing key findings
- Include a confidence score (1-5) for each section based on the quality and completeness of the client's information

## Special Instructions for Handling Ambiguity

When you encounter unclear, inconsistent, or incomplete information:

1. **Never guess critical information** such as:
   - Regulatory requirements
   - Legal obligations
   - Technical specifications
   
2. **Apply reasoned inference for non-critical information** such as:
   - Preferred documentation style
   - Training approach
   - Implementation order
   
3. **Tag all inferences clearly** using:
   ```
   [INFERENCE: Based on the client's description of X, it appears that Y approach would be appropriate, but this should be confirmed.]
   ```

4. **Prioritize follow-up questions** based on:
   - Impact on SOP customization
   - Regulatory significance
   - Operational importance
   
## Output Format Guidelines

The final document should be formatted as follows:

1. Title page with client name, date, and document purpose
2. Table of contents with hyperlinks
3. Executive summary (max 1 page)
4. Main body sections as detailed above
5. Appendices including:
   - Original survey responses (referenced)
   - Glossary of terms
   - SOP customization checklist
   - Follow-up questions (if any)
   
Format the document with clear headings and subheadings, using consistent numbering (1.1, 1.2, etc.) for easy reference in future communications.

## Evaluation Criteria

Before submitting the final document, verify that it meets these criteria:

1. Completeness: All survey questions have corresponding analysis
2. Actionability: Clear instructions for SOP adaptation
3. Clarity: Distinguishes between client statements, inferences, and recommendations
4. Specificity: Avoids vague statements in favor of concrete details
5. Prioritization: Clearly indicates which elements are most critical
6. Research guidance: Provides specific questions for further investigation
7. Accessibility: Uses clear language while preserving necessary technical terms
```
