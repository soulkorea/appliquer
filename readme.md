# Appliquer

> **Better decisions, not more applications.**

An AI decision engine that helps Product Managers identify the right opportunities, prepare strategically, and invest their time where it matters most.

---

# Vision

Appliquer aims to become the most trusted AI Career Copilot for Product Managers.

Its purpose is not to maximize the number of job applications.

Its purpose is to maximize the quality of career decisions.

The long-term vision is an AI system that supports every stage of the job search:

- Evaluate opportunities
- Research companies
- Tailor resumes
- Prepare for interviews
- Capture lessons learned
- Continuously improve career strategy

---

# Guiding Principles

Appliquer follows six core principles.

### Evidence over opinion

Recommendations should always be supported by evidence from the user's experience and the job description.

### Action over information

Every interaction should end with a clear recommended next step.

### Clarity over cleverness

Outputs should be concise, structured, and easy to understand.

### Honesty over optimism

Appliquer should never exaggerate a user's fit for a role or hide uncertainty.

### Respect the user's time

The product exists to reduce wasted effort and improve decision quality.

### AI supports judgment

Appliquer helps users make better decisions.

It never replaces the user's own judgment.

---

## Why "Appliquer"?

The name **Appliquer** is inspired by the French verb *appliquer*, meaning **"to apply."**

The name reflects two ideas that define the product:

- **Applying for opportunities** — helping users identify and pursue the roles that best align with their experience, goals, and strengths.
- **Applying thoughtful judgment** — making deliberate, evidence-based career decisions rather than reacting to every opportunity.

Appliquer is built on the belief that the best career outcomes come not from submitting more applications, but from making better decisions about **where to invest your time and energy**.

Its mission is to help professionals pursue fewer opportunities with greater confidence, preparation, and intention.

--

# Current MVP

Version 0.1 focuses on one capability:

## Opportunity Evaluation

Inputs

- Resume
- Product Manager job description

Outputs

- Apply / Maybe / Pass recommendation
- Evidence supporting the recommendation
- Strengths
- Potential gaps
- Estimated preparation effort
- Recommended next action

---

# Product Architecture

Appliquer is intentionally platform-independent.

The product is built around a portable reasoning engine called the **Brain**.

The Brain contains the product's reasoning, principles, evaluation framework, and communication style.

Different implementations (ChatGPT, Claude, web application, API, etc.) simply provide different interfaces to the same Brain.

```
                +---------------------+
                |   Appliquer Brain   |
                +---------------------+
                          |
        -----------------------------------------
        |            |            |             |
    ChatGPT      Claude       Web App        API
```

This architecture allows Appliquer to evolve independently of any individual AI platform.

---

# Repository Structure

```
brain/
    constitution.md
    decision_engine.md
    evaluation_rubric.md
    communication_style.md

knowledge/
    resume.md
    star_stories.md
    companies/

product/
    prd.md
    roadmap.md
    decision_log.md

validation/
    test_cases.md
    feedback.md

platform/
    chatgpt/
    future/
```

---

# Roadmap

### Phase 1

Build the Appliquer Brain.

- Constitution
- Founding Principles
- Decision Engine
- Evaluation Rubric

### Phase 2

Implement the Brain inside ChatGPT.

### Phase 3

Validate against real Product Manager job opportunities.

### Phase 4

Expand into a platform-independent multi-agent career copilot.

---

# Status

**Current Version**

Project: v0.1

Brain: v0.1

Status: 🚧 Early Development

---

## Founding Philosophy

Appliquer is being built like a product, not a prompt.

The long-term goal is to create a portable AI reasoning engine that can move across platforms while maintaining a consistent product philosophy, decision framework, and user experience.

Every feature should answer one question:

> **Does this help the user make a better career decision?**