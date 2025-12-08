---
marp: true
theme: default
paginate: true
style: |
  section {
    background-color: #1e1e2e;
    color: #cdd6f4;
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
    padding: 60px;
  }
  h1 {
    color: #cba6f7;
    font-size: 60px;
    margin-bottom: 30px;
    border-bottom: 3px solid #6c71c4;
  }
  h2 {
    color: #b4befe;
    font-size: 48px;
    margin-top: 40px;
    margin-bottom: 20px;
  }
  h3 {
    color: #89b4fa;
    font-size: 36px;
  }
  p {
    font-size: 28px;
    line-height: 1.6;
    color: #cdd6f4;
  }
  ul, ol {
    font-size: 28px;
    line-height: 1.8;
  }
  li {
    color: #cdd6f4;
    margin-bottom: 10px;
  }
  strong {
    color: #f5c2e7;
    font-weight: 700;
  }
  pre {
    background-color: #11111b;
    border: 2px solid #6c71c4;
    border-radius: 8px;
    padding: 20px;
    margin: 20px 0;
  }
  code {
    background-color: #11111b;
    color: #cba6f7;
    font-family: 'Fira Code', 'Monaco', 'Courier New', monospace;
    font-size: 24px;
  }
  :not(pre) > code {
    background-color: #313244;
    color: #f5c2e7;
    padding: 2px 8px;
    border-radius: 4px;
  }
  blockquote {
    border-left: 5px solid #6c71c4;
    padding-left: 20px;
    color: #a6adc8;
    font-style: italic;
    background-color: #181825;
    padding: 20px;
    border-radius: 4px;
  }
  table {
    border-collapse: collapse;
    width: 100%;
    margin: 20px 0;
  }
  th {
    background-color: #6c71c4;
    color: #ffffff;
    padding: 12px;
    font-weight: 700;
    font-size: 28px;
  }
  td {
    background-color: #313244;
    border: 1px solid #6c71c4;
    padding: 12px;
    color: #cdd6f4;
    font-size: 26px;
  }
  tr:nth-child(even) td {
    background-color: #45475a;
  }
  a {
    color: #a6adc8;
    text-decoration: none;
  }
  a:hover {
    color: #cba6f7;
    text-decoration: underline;
  }
  hr {
    border: none;
    border-top: 2px solid #6c71c4;
    margin: 40px 0;
  }
  section::after {
    color: #6c71c4;
    font-weight: 700;
  }
  .author-info {
    font-size: 0.9em;
    line-height: 1.6;
  }
  .contact-info {
    font-size: 0.8em;
  }
  .footer {
    position: absolute;
    bottom: 20px;
    right: 20px;
    font-size: 0.7em;
    color: #a0aec0;
  }
  .two-columns {
    display: flex;
  }
  .two-columns > div {
    flex: 1;
    padding: 0 20px;
  }
---

<!--
  Presentation: AI-Enhanced Deliberate Practice in Medical Research
  Context: Medical Research and Education
  Date: December 2025
  Presenter: Dr. MTD Lakshan
-->

<!-- _paginate: false -->

# AI-Enhanced Deliberate Practice in Medical Research

**Transforming Medical Research Through Intelligent Feedback Systems**

Presented by **Dr. MTD Lakshan**

---

## About the Presenter

![bg right:40% width:400px](assets/linkedin-qr-code.jpg)

<div class="author-info">

**Dr. MTD LAKSHAN**
MBBS MS DOHNS FEB ORL HNS FRCS Ed ORL HNS

- Board Certified Consultant in ENT and Head and Neck Surgery
- Senior Lecturer in Medical Education, University of Kelaniya
- Director, Nawaloka Hospitals PLC
- Head, Nawaloka Research and Education Foundation
- Founder, Infinite Learner AI

</div>

---

## Agenda

1. **Understanding Deliberate Practice**
2. **Core Principles and Components**
3. **AI's Role in Each Component**
4. **Practical Applications in Medical Research**
5. **Implementation Framework**
6. **Challenges and Solutions**
7. **Future Directions**

---

# Understanding Deliberate Practice

---

## What is Deliberate Practice?

> **Deliberate Practice** is purposeful, systematic practice that focuses on improving specific aspects of performance through immediate feedback and constant refinement.

**Key Characteristics:**
- **Goal-directed** - Clear, specific objectives
- **Focused attention** - Concentrated effort on skill development
- **Immediate feedback** - Rapid assessment and correction
- **Repeated refinement** - Iterative improvement cycles

---

## Origins: Ericsson's Framework

**Anders Ericsson's Research (1993):**
- Expert performance requires ~10,000 hours of **deliberate practice**
- Not just repetition - requires structured, goal-oriented effort
- Feedback is critical for improvement
- Expertise develops through conscious refinement

**Traditional Limitations:**
- Requires expert mentors (scarce resource)
- Delayed feedback cycles
- Limited scalability
- High cognitive load on mentors

---

# Core Components of Deliberate Practice

---

## The Four Essential Components

<div class="two-columns">
<div>

### 1. Task Breakdown
- Decompose complex skills into manageable parts
- Identify specific competencies
- Create learning modules

### 2. Outcome Definition
- Establish clear success criteria
- Define measurable objectives
- Set performance benchmarks

</div>
<div>

### 3. Feedback Loops
- Provide timely performance assessment
- Identify gaps and errors
- Guide corrective actions

### 4. Iterative Refinement
- Practice with corrections
- Progressive difficulty scaling
- Mastery before advancement

</div>
</div>

---

# AI's Transformative Role

---

## How AI Enhances Each Component

| Component | Traditional Approach | AI-Enhanced Approach |
|-----------|---------------------|---------------------|
| **Task Breakdown** | Manual expert analysis | Automated skill decomposition with pattern recognition |
| **Outcome Definition** | Fixed, generic standards | Adaptive, personalized objectives |
| **Feedback** | Delayed mentor review | Instantaneous, multimodal feedback |
| **Iteration** | Linear progression | Dynamic, personalized learning paths |

---

# Component 1: AI-Powered Task Breakdown

---

## Task Breakdown in Medical Research

**Traditional Challenge:**
Research is complex, multidisciplinary, and difficult to decompose without expertise.

**AI Solution: Intelligent Task Decomposition**

**Example: Systematic Review Protocol Development**

Traditional breakdown:
1. Formulate research question
2. Design search strategy
3. Define inclusion/exclusion criteria
4. Extract and synthesize data

---

## AI-Enhanced Breakdown

**AI analyzes thousands of published systematic reviews to identify:**

1. **PICO Framework Application**
   - Population identification patterns
   - Intervention categorization
   - Comparison group selection
   - Outcome measure standardization

2. **Search Strategy Optimization**
   - Database-specific syntax variations
   - Boolean operator placement
   - MeSH term hierarchy utilization
   - Search sensitivity/specificity balance

---

## Granular Subtask Identification

**AI identifies micro-skills within each major task:**

For "Data Extraction":
- Identify study characteristics (design, sample size, duration)
- Extract outcome measures (continuous vs. categorical)
- Assess risk of bias (tool-specific criteria)
- Standardize data formats for meta-analysis

**Benefit:** Reduces cognitive overwhelm, provides clear learning pathways

---

# Component 2: AI-Defined Outcomes

---

## Outcome Definition: The AI Advantage

**Traditional Problem:**
Generic outcomes don't account for individual researcher's background, experience level, or research context.

**AI Solution: Adaptive, Personalized Objectives**

---

## Example: Literature Review Quality Assessment

**Traditional Outcome:**
"Complete a comprehensive literature review"

**AI-Enhanced Personalized Outcomes:**

For a **junior researcher** (Year 1):
- Identify and retrieve **15 relevant papers** using systematic search (by Week 2)
- Summarize key findings using structured templates (by Week 3)
- Identify methodological gaps in **3 papers** (by Week 4)

For a **senior researcher** (Year 4+):
- Conduct meta-analysis of **30+ RCTs** with heterogeneity assessment (by Month 1)
- Publish systematic review in Q1 journal (by Month 6)

---

## Dynamic Benchmarking

**AI continuously adjusts targets based on:**
- Performance velocity (learning rate)
- Error patterns (common mistakes)
- Domain complexity (topic difficulty)
- Time constraints (project deadlines)

> "AI transforms static goals into living targets that evolve with your progress"

---

# Component 3: AI-Powered Feedback

---

## The Feedback Revolution

**Traditional Feedback Limitations:**
- **Delayed:** Mentor reviews take days/weeks
- **Generic:** Same feedback for different learners
- **Inconsistent:** Varies by mentor expertise
- **Limited:** Mentor bandwidth constraints

**AI Feedback Characteristics:**
- **Instantaneous:** Real-time assessment
- **Personalized:** Adapted to individual needs
- **Consistent:** Standardized quality
- **Scalable:** Unlimited capacity

---

## Multimodal Feedback Mechanisms

<div class="two-columns">
<div>

### 1. Real-Time Text Analysis
- Grammar and clarity checks
- Argumentation structure
- Citation accuracy
- Evidence strength assessment

### 2. Conceptual Coherence
- Logical flow evaluation
- Gap identification
- Redundancy detection
- Synthesis quality

</div>
<div>

### 3. Methodological Rigor
- Statistical test appropriateness
- Sample size justification
- Bias assessment accuracy
- Ethical consideration coverage

### 4. Comparative Benchmarking
- Performance vs. peers
- Alignment with best practices
- Publication readiness score

</div>
</div>

---

## Example: AI Feedback on Research Manuscript

**Scenario:** Resident submits introduction section for case series

**AI Feedback (Immediate):**

✅ **Strengths:**
- Clear problem statement (paragraph 1)
- Appropriate literature cited (15 references)

⚠️ **Areas for Improvement:**
- **Gap in literature:** Missing discussion of recent meta-analysis (Smith et al., 2024)
- **Argumentation:** Transition from problem to research aim is abrupt (paragraph 3 → 4)
- **Clarity:** Sentence complexity score: 82 (target: <75 for medical journals)

📊 **Suggested Action:**
Add bridging paragraph discussing limitations of prior studies before stating research aim

---

## Feedback Timing and Granularity

**AI provides feedback at multiple stages:**

| Stage | Feedback Type | Example |
|-------|---------------|---------|
| **Drafting** | Real-time suggestions | "Consider rephrasing for clarity" |
| **Section Completion** | Structural analysis | "Introduction lacks clear hypothesis statement" |
| **Full Manuscript** | Holistic assessment | "Results section exceeds 30% of total word count (target: 20-25%)" |
| **Pre-Submission** | Readiness scoring | "Manuscript readiness: 78/100. Address reviewer concerns on methodology." |

---

# Component 4: AI-Guided Iteration

---

## Iterative Refinement: The AI Learning Loop

**Traditional Iteration:**
Linear progression → Practice → Wait for feedback → Revise → Submit again

**AI-Enhanced Iteration:**
Continuous micro-cycles of practice, feedback, and refinement in real-time

---

## Adaptive Learning Paths

**AI monitors performance and dynamically adjusts:**

**Example: Critical Appraisal Skill Development**

**Cycle 1:** Appraise 3 RCTs (provided templates)
- AI detects: Difficulty identifying allocation concealment
- **Adaptive Response:** Provides 5 additional examples with guided practice on this specific skill

**Cycle 2:** Appraise 5 cohort studies (reduced scaffolding)
- AI detects: Improved bias assessment, but struggles with confounding analysis
- **Adaptive Response:** Introduces interactive case studies on confounding

**Cycle 3:** Mixed study designs (independent work)
- AI detects: Mastery achieved
- **Adaptive Response:** Introduces meta-analysis training

---

## Progressive Difficulty Scaling

**AI automatically adjusts task complexity based on mastery:**

| Mastery Level | Task Complexity | AI Support |
|---------------|-----------------|------------|
| **Novice** | Simplified scenarios, guided templates | High scaffolding, step-by-step prompts |
| **Advanced Beginner** | Realistic cases, partial guidance | Moderate scaffolding, hints available |
| **Competent** | Complex, ambiguous cases | Minimal scaffolding, self-assessment |
| **Expert** | Novel, undefined problems | No scaffolding, peer comparison |

---

## Spaced Repetition and Retention

**AI applies cognitive science principles:**

- **Spaced Repetition Algorithm:** Re-introduces challenging concepts at optimal intervals
- **Interleaving:** Mixes different research skills to enhance retention
- **Retrieval Practice:** Prompts active recall before providing answers

**Example:**
If a researcher struggles with "risk of bias assessment" in Week 2, AI reintroduces this skill in Week 4, Week 7, and Week 12 with progressively harder cases.

---

# Practical Applications in Medical Research

---

## Application 1: Manuscript Writing

**Task:** Writing the Methods section of an RCT manuscript

**AI-Enhanced Deliberate Practice:**

1. **Breakdown:**
   - Study design description
   - Participant eligibility and recruitment
   - Randomization and blinding procedures
   - Intervention description (using TIDieR checklist)
   - Outcome measures and data collection
   - Statistical analysis plan

---

## Manuscript Writing (continued)

2. **Outcome Definition:**
   - Methods section completeness score: 90/100 (based on CONSORT checklist)
   - Clarity score: >75 (readability)
   - Reproducibility score: >80 (sufficient detail for replication)

3. **Feedback:**
   - Real-time CONSORT compliance checking
   - Clarity suggestions for complex statistical procedures
   - Identification of missing methodological details

4. **Iteration:**
   - Revise based on AI feedback
   - Compare with exemplar methods sections from high-impact journals
   - Submit for human mentor review only after AI-verified quality threshold

---

## Application 2: Statistical Analysis Skills

**Task:** Performing and interpreting regression analysis for observational study

**AI-Enhanced Deliberate Practice:**

1. **Breakdown:**
   - Data exploration and assumption checking
   - Model selection (which regression type?)
   - Covariate selection and justification
   - Model diagnostics (residual analysis)
   - Interpretation of coefficients and confidence intervals
   - Reporting results following STROBE guidelines

---

## Statistical Analysis (continued)

2. **Outcome Definition:**
   - Correctly identify appropriate regression model (100% accuracy on 10 practice datasets)
   - Interpret coefficients with clinical context (scored by AI evaluation of written interpretations)
   - Detect model violations (sensitivity >85%)

3. **Feedback:**
   - **Immediate:** "Your model assumes linear relationship, but scatter plot suggests non-linearity. Consider polynomial terms or splines."
   - **Diagnostic:** AI flags when p-hacking behaviors detected (e.g., excessive model iterations)

4. **Iteration:**
   - Practice on progressively complex datasets
   - AI introduces confounding scenarios, effect modification, missing data

---

## Application 3: Critical Appraisal and Evidence Synthesis

**Task:** Conducting systematic review and meta-analysis

**AI-Enhanced Deliberate Practice:**

1. **Breakdown:**
   - Formulating answerable PICO question
   - Developing comprehensive search strategy
   - Screening titles/abstracts efficiently
   - Full-text review and data extraction
   - Risk of bias assessment
   - Meta-analysis (forest plots, heterogeneity assessment)
   - GRADE evidence quality rating

---

## Critical Appraisal (continued)

2. **Outcome Definition:**
   - Search strategy retrieves ≥95% of relevant studies (validated against gold standard)
   - Inter-rater reliability with AI: Cohen's kappa >0.80 on risk of bias
   - Meta-analysis technically correct (no statistical errors)

3. **Feedback:**
   - **Search Strategy:** "Your search missed 3 relevant RCTs. Consider adding MeSH term: 'Drug Therapy, Combination'"
   - **Risk of Bias:** "You rated 'allocation concealment' as low risk, but the study states 'sealed envelopes' without specifying opaqueness. This should be unclear risk."
   - **Meta-Analysis:** "I² = 78% indicates high heterogeneity. Have you explored subgroup analyses or meta-regression?"

---

## Critical Appraisal (continued)

4. **Iteration:**
   - Start with pre-screened studies (learn extraction)
   - Progress to full systematic review workflow
   - AI introduces "planted" errors in studies to test vigilance
   - Final test: Independent systematic review on novel topic, AI evaluates quality against published reviews

---

## Application 4: Grant Writing Skills

**Task:** Writing a competitive research grant proposal

**AI-Enhanced Deliberate Practice:**

1. **Breakdown:**
   - Specific Aims page (hypothesis, objectives)
   - Significance section (problem importance, innovation)
   - Approach (study design, methods, analysis plan)
   - Preliminary data presentation
   - Budget justification

---

## Grant Writing (continued)

2. **Outcome Definition:**
   - Aims page: Clear hypothesis, achievable within timeframe (scored 0-10)
   - Significance: Compelling case for funding (novelty score, impact score)
   - Approach: Rigorous, feasible (scored on AREA criteria)
   - Overall fundability score: >7/10 (based on NIH reviewer guidelines)

3. **Feedback:**
   - **Specific Aims:** "Your hypothesis is not testable as stated. Rephrase to specify measurable outcome."
   - **Significance:** "You cite 8 papers, all >5 years old. Reviewers expect recent literature (last 2-3 years)."
   - **Approach:** "Your sample size calculation uses 80% power. Most reviewers expect 90% for primary outcome."

---

## Grant Writing (continued)

4. **Iteration:**
   - Write multiple drafts with AI feedback
   - Compare with funded grants (AI provides comparative analysis)
   - Simulate peer review (AI generates mock reviewer critiques)
   - Practice responses to reviewer concerns
   - Final polish: Human mentor review after AI quality threshold met

---

# Implementation Framework

---

## How to Integrate AI into Your Research Training

**Step-by-Step Implementation:**

### Phase 1: Assessment (Weeks 1-2)
- Identify specific research competencies to develop
- Establish baseline skill level (self-assessment + AI diagnostic test)
- Set SMART goals with AI assistance

### Phase 2: Structured Practice (Weeks 3-12)
- Daily/weekly practice sessions with AI feedback
- Focus on one competency cluster at a time
- Track progress metrics

---

## Implementation Framework (continued)

### Phase 3: Progressive Complexity (Weeks 13-24)
- Reduce AI scaffolding gradually
- Introduce authentic research projects
- Blend AI feedback with human mentorship

### Phase 4: Mastery and Independence (Weeks 25+)
- Minimal AI support (use for quality checks only)
- Lead independent research projects
- Mentor others using AI-enhanced frameworks

---

## Recommended AI Tools for Medical Researchers

| Research Task | AI Tool Category | Examples |
|---------------|------------------|----------|
| **Literature Review** | Search & Synthesis | Elicit, Consensus, Scite |
| **Writing Assistance** | Grammar & Clarity | Claude, GPT-4, Grammarly (Medical) |
| **Statistical Analysis** | Guidance & Checking | Statistical AI tutors, R/Python AI assistants |
| **Manuscript Preparation** | Compliance Checking | CONSORT-AI, PRISMA-AI checkers |
| **Grant Writing** | Reviewer Simulation | Grant review AI tools |
| **Critical Appraisal** | Bias Detection | Cochrane RoB-AI, systematic review AI |

---

## Integration with Traditional Mentorship

**AI does NOT replace human mentors. It augments mentorship:**

<div class="two-columns">
<div>

### AI Handles:
- Repetitive feedback on basics
- 24/7 availability for practice
- Immediate error detection
- Scalable support for multiple learners
- Objective performance tracking

</div>
<div>

### Human Mentors Focus On:
- Strategic research direction
- Nuanced judgment calls
- Career guidance and networking
- Ethical dilemmas
- Emotional support and motivation
- Domain-specific expertise

</div>
</div>

> **Optimal Model:** AI for frequent micro-feedback + Human mentors for periodic macro-guidance

---

# Challenges and Solutions

---

## Challenge 1: AI Accuracy and Reliability

**Problem:**
AI can make errors, especially in nuanced medical contexts (e.g., clinical judgment, ethical considerations)

**Solutions:**
- **Validation:** Use AI trained on verified medical datasets
- **Human-in-the-loop:** Critical decisions reviewed by experts
- **Transparency:** AI explains reasoning, user assesses credibility
- **Continuous learning:** AI updated with latest evidence

---

## Challenge 2: Over-reliance on AI

**Problem:**
Learners may become dependent on AI, hindering independent critical thinking

**Solutions:**
- **Fading scaffolding:** Gradually reduce AI support as competence grows
- **Metacognitive prompts:** AI asks "Why did you choose this approach?" before giving answers
- **Independent assessment:** Periodic evaluation without AI assistance
- **Reflective practice:** Encourage self-assessment before consulting AI

---

## Challenge 3: Lack of Contextual Understanding

**Problem:**
AI may miss institution-specific norms, cultural contexts, or local resource constraints

**Solutions:**
- **Customization:** Adapt AI tools to local contexts (e.g., resource-limited settings)
- **Hybrid feedback:** Combine AI's general principles with local mentor's contextual knowledge
- **User input:** Allow researchers to provide context to AI for tailored feedback

---

## Challenge 4: Access and Equity

**Problem:**
Advanced AI tools may be expensive or unavailable in low-resource settings

**Solutions:**
- **Open-source tools:** Promote development of free, accessible AI for medical research
- **Institutional licenses:** Universities/hospitals negotiate bulk access
- **Offline capabilities:** AI tools that work without constant internet
- **Global collaborations:** Share AI infrastructure across institutions

---

## Challenge 5: Data Privacy and Ethics

**Problem:**
Sharing research data with AI systems raises confidentiality concerns

**Solutions:**
- **De-identification:** Remove patient identifiers before AI processing
- **Local processing:** Use on-premise AI (not cloud-based) for sensitive data
- **Compliance:** Ensure AI tools meet HIPAA, GDPR, institutional IRB standards
- **Transparency:** Clearly communicate data use policies to participants

---

# Future Directions

---

## The Future of AI in Medical Research Training

**Emerging Trends:**

1. **Multimodal AI Tutors**
   - Voice interaction for hands-free guidance during lab work
   - Visual analysis of histology slides, imaging, surgical videos
   - Real-time coaching during patient interviews (communication skills)

2. **Collaborative AI**
   - AI facilitates team-based research (coordinates tasks, synthesizes inputs)
   - Virtual research assistants for PIs managing multiple projects

---

## Future Directions (continued)

3. **Predictive Analytics**
   - AI predicts research project success likelihood (before you invest months)
   - Identifies high-impact research questions based on trend analysis
   - Suggests optimal collaborations based on complementary expertise

4. **Personalized Research Career Pathways**
   - AI analyzes your publication trajectory, suggests next career steps
   - Recommends training gaps to fill for competitive grant applications
   - Connects you with mentors and collaborators aligned with your goals

---

## Vision: The AI-Augmented Medical Researcher

**By 2030, we envision:**

- **Every medical researcher** has access to personalized AI coaching
- **Research training time** reduced by 30-40% through efficient deliberate practice
- **Research quality** improved through consistent, immediate feedback
- **Equity in access** to expert-level guidance, regardless of geography or resources
- **Mentorship bottleneck** eliminated, freeing human mentors for high-value guidance

> "AI empowers every doctor to become a competent researcher, accelerating medical discovery for humanity."

---

# Conclusion

---

## Key Takeaways

1. **Deliberate Practice Works** - Structured, goal-directed practice with feedback leads to expertise
2. **AI Supercharges Each Component:**
   - Task breakdown → Intelligent decomposition
   - Outcome definition → Adaptive, personalized goals
   - Feedback loops → Instantaneous, multimodal assessment
   - Iterative refinement → Dynamic learning paths

3. **Medical Research is Ideal for AI Enhancement** - Complex, multifaceted skills benefit from scalable, consistent feedback

---

## Practical Next Steps

**For Individual Researchers:**
1. Identify one research skill to develop (e.g., manuscript writing)
2. Select appropriate AI tool (e.g., Claude for writing feedback)
3. Commit to 30 days of daily practice with AI feedback
4. Track progress and adjust goals

**For Research Programs/Institutions:**
1. Pilot AI-enhanced training modules in one research course
2. Evaluate effectiveness (time to competency, learner satisfaction)
3. Scale successful interventions across programs
4. Train faculty on AI integration best practices

---

## The Paradigm Shift

**From:**
- Limited mentor availability → Bottlenecked learning
- Delayed feedback → Slow skill development
- Generic training → One-size-fits-all approach

**To:**
- **Unlimited AI coaching** → Accelerated learning
- **Immediate feedback** → Rapid skill refinement
- **Personalized pathways** → Optimized for individual needs

> "AI-enhanced deliberate practice democratizes excellence in medical research."

---

## Thank You

### Questions & Discussion

<div class="author-info">

**Dr. MTD LAKSHAN**
MBBS MS DOHNS FEB ORL HNS FRCS Ed ORL HNS

</div>

<div class="contact-info">

**Get in touch:**
- Email: [lakshan@health.lk](mailto:lakshan@health.lk)
- LinkedIn: [mtd-lakshan](https://www.linkedin.com/in/mtd-lakshan-78738213)
- Website: [health.lk](https://www.health.lk)
- Infinite Learner AI: [ilai.academy](https://ilai.academy/)

</div>

---

<!-- _paginate: false -->

# Additional Resources

---

## Recommended Reading

**Deliberate Practice:**
- Ericsson, K. A., Krampe, R. T., & Tesch-Römer, C. (1993). *The role of deliberate practice in the acquisition of expert performance.* Psychological Review, 100(3), 363.

**AI in Medical Education:**
- Masters, K. (2019). *Artificial intelligence in medical education.* Medical Teacher, 41(9), 976-980.
- Chan, K. S., & Zary, N. (2019). *Applications and challenges of implementing artificial intelligence in medical education.* JMIR Medical Education, 5(1), e13930.

**Medical Research Training:**
- Burgoyne, L. N., O'Flynn, S., & Boylan, G. B. (2010). *Undergraduate medical research.* Academic Medicine, 85(1), 150-156.

---

## Online Learning Platforms

**AI Tools for Researchers:**
- **Elicit.org** - AI research assistant for literature reviews
- **Consensus.app** - Evidence-based answers from research papers
- **Scite.ai** - Smart citations showing how papers are cited
- **Claude.ai / ChatGPT** - General AI assistants for writing and analysis

**Research Training Resources:**
- **Infinite Learner AI** ([ilai.academy](https://ilai.academy/)) - AI-enhanced medical education
- **Cochrane Training** - Systematic review methodology
- **EQUATOR Network** - Reporting guidelines for health research

---

## Contact for Collaborations

**Interested in implementing AI-enhanced deliberate practice in your institution?**

**Dr. MTD Lakshan** is available for:
- Workshop facilitation
- Curriculum development consultation
- Research collaborations on AI in medical education
- Institutional AI integration planning

📧 **Email:** lakshan@health.lk
🌐 **Website:** [health.lk](https://www.health.lk)
🎓 **Infinite Learner AI:** [ilai.academy](https://ilai.academy/)

---

<!-- _paginate: false -->

# Thank You

**Let's transform medical research training together.**
