# AI Leadership Dev Skill

Operating system for executives building AI applications. 4 phases: Vision → Implementation → Refinement → Launch.

**Core Principle:** Lock the AI vision before locking the implementation. Lock the architecture before locking the code.

---

## The 4 Phases

### Phase 0: Vision, Architecture & Strategy (Planning)

**Duration:** 3-5 days  
**HITL Gate:** Executive alignment before Phase 1  
**Cost of deferring:** 5-30x more expensive if moved to Phase 2

**How AI and humans communicate in this phase:**

This phase uses **multi-optional questions** as the primary communication pattern.

Instead of: "What do you want to build?"  
Ask: "Are you building: (A) internal automation, (B) customer-facing product, or (C) decision support tool?"

Instead of: "What model should we use?"  
Ask: "Which appeals most: (A) fine-tuned smaller model, (B) LLM with RAG, or (C) hybrid approach? Here's the tradeoff..."

**Human decides which option. AI presents options with tradeoffs.**

---

**What happens:**

1. **Vision** — What will the AI actually do? (1-2 sentences, not hype)
   - Example: "AI assistant handles 60% of support tickets, escalates 40% to humans"
   - AI asks: "Should the AI: (A) draft response for human approval, (B) send response and human reviews after, or (C) handle certain categories fully?"
   - Human chooses A, B, or C

2. **Goal** — What business outcome? (measurable, not vanity)
   - Example: "Reduce avg support response time from 4 hours to 2 hours"
   - AI asks: "Is the success metric: (A) response time, (B) ticket resolution rate, or (C) customer satisfaction score?"
   - Human chooses primary + secondary metrics

3. **AI Architecture** — What model? What data? What decisions?
   - Example: "LLM + internal knowledge base + escalation logic"
   - AI asks: "For your use case, which approach: (A) use off-the-shelf LLM, (B) fine-tune on your data, or (C) hybrid with domain-specific model?"
   - AI explains cost/quality/speed tradeoffs for each
   - Human chooses based on constraints

4. **Data Strategy** — What data does the AI need? How current? How clean?
   - AI asks: "For training data, do you have: (A) historical data ready to use, (B) data that needs cleaning, or (C) minimal data but can label as we go?"
   - Lock data pipelines
   - Define quality thresholds
   - Document data lineage

5. **Human-AI Boundary** — What does AI decide? What do humans decide?
   - AI presents common patterns:
     - Option A: AI generates, human approves (safe, slow)
     - Option B: AI executes, human reviews after (fast, risky)
     - Option C: AI handles routine, human handles edge cases (balanced)
   - Example boundary: AI generates response, human approves before sending
   - Example boundary: AI escalates to human for review
   - Human explicitly chooses the boundary

6. **Success Metrics** — How do we know it works? (not vanity metrics)
   - AI asks: "Which matters most: (A) accuracy/quality, (B) speed/latency, or (C) cost efficiency? You can't optimize all three equally."
   - Not: "200 transactions processed"
   - Yes: "Reduce response time 50%, maintain 95% accuracy"

7. **Risk & Compliance** — What could go wrong? What's required?
   - AI asks: "Your biggest risk is: (A) hallucination/wrong answers, (B) data privacy, or (C) cost runaway?"
   - Hallucination risk? How do we mitigate?
   - GDPR/compliance requirements?
   - Audit trail needed?
   - Cost limits?

8. **Constraints** — Speed, cost, latency, availability?
   - Response time SLA?
   - Monthly cost budget?
   - Uptime requirements?

---

**⚠️ HITL Stoppers - Phase 0 Has Multiple Human Decision Gates**

This phase is NOT linear. It has explicit stoppers where humans must decide before proceeding.

**Stopper 1: Vision Clarity**
- If humans disagree on what the AI should do → STOP
- Go back to multi-optional questions until clarity achieved
- Do NOT proceed to architecture until vision is locked

**Stopper 2: Architecture Viability**
- If the proposed architecture can't support the vision → STOP
- Go back and choose different architecture option
- Do NOT proceed to data strategy until architecture is solid

**Stopper 3: Risk Acceptance**
- If risks are unacceptable → STOP
- Either change the vision to reduce risk, or increase budget for risk mitigation
- Do NOT proceed if C-suite hasn't explicitly accepted risks

**Stopper 4: Budget/Timeline Mismatch**
- If timeline is too short for the vision → STOP
- Either reduce scope, extend timeline, or increase budget
- Do NOT proceed if resources don't match requirements

**Why stoppers matter:**
- Stopping in Phase 0 costs $0 (just more conversation)
- Stopping in Phase 1 costs thousands (rework)
- Stopping in Phase 2 costs tens of thousands (rebuild)
- There's no cost to saying "this won't work" in Phase 0

**If any stopper is triggered, reset the conversation and re-ask multi-optional questions.**

---

**9. Generate Requirements Document**

Before approval gate, generate formal requirements document. This is the bridge from Phase 0 planning to Phase 1 building.

**Requirements Document must include:**

```markdown
# AI Project Requirements Document

## Project: [Name]
**Date:** [Date]  
**Status:** Ready for Phase 1 Build

---

## Vision & Goals

**Vision Statement:** [1-2 sentences what AI does]

**Success Metrics:**
- Primary metric: [specific, measurable]
- Secondary metric: [specific, measurable]
- Approval threshold: [specific numbers]

---

## AI Architecture Locked

**Model/Approach:** [LLM / Fine-tune / RAG / Hybrid / Other]

**Data Requirements:**
- Input data: [what the AI needs]
- Training data: [size, quality, source]
- Data refresh frequency: [daily / weekly / real-time]

**Performance Requirements:**
- Latency SLA: [<2 second response required?]
- Accuracy requirement: [95% on what metric?]
- Cost budget: [$X per month maximum]

---

## Human-AI Boundary (CRITICAL)

**What AI Does:**
- [ ] Generates X
- [ ] Escalates Y
- [ ] Decides Z

**What Humans Do:**
- [ ] Approves AI output
- [ ] Reviews edge cases
- [ ] Makes final decision

**Escalation Triggers:**
- [ ] Confidence < 80%
- [ ] Category unknown
- [ ] Edge case detected

---

## Compliance & Risk

**Risks Identified:**
1. [Risk]: Hallucination on X topic
   - Mitigation: Human review before output
   - Acceptance: C-Suite approved

2. [Risk]: Data privacy exposure
   - Mitigation: Anonymize input
   - Acceptance: Legal approved

**Compliance Requirements:**
- [ ] GDPR audit trail required
- [ ] Explainability required
- [ ] Data retention policy: [X days]

---

## Constraints Locked

- Timeline: [By date]
- Budget: [$X total / $Y monthly]
- Team: [Who owns what]
- Availability: [SLA requirement]

---

## Phase 1 Inputs for Engineering

**Architecture Diagram:** [Attached]

**Data Pipeline:** [Specified]

**Success Definition:** [Metrics locked]

**Budget Allocated:** [$X]

**Go/No-Go:** ✅ APPROVED by:
- [ ] C-Suite
- [ ] Product Owner
- [ ] Engineering Lead
- [ ] Legal/Compliance
```

**Requirements Document is LOCKED before Phase 1 starts.**

If anything in the document is unclear or contested → stopper triggered → reset Phase 0.

---

9. **Deliverables**
   - Vision doc (1 page: what AI does, why it matters)
   - Architecture diagram (model, data, integrations)
   - **Requirements Document** (signed off, locked, no changes)
   - Success metrics (measurable outcomes)
   - Risk assessment
   - Compliance checklist
   - Project plan (phases, timeline, budget)

**You decide:**
- Is the vision clear and realistic? (multi-optional clarification if not)
- Does the architecture support the vision? (architecture stopper if not)
- Are risks acceptable? (risk stopper if not)
- Does the requirements document accurately reflect all decisions?
- Ready to build?

**HITL Gate Checklist (No proceeding without all boxes):**
- [ ] Vision approved by C-suite (not disputed)
- [ ] Architecture chosen and justified
- [ ] Human-AI boundary explicitly defined
- [ ] Success metrics locked (numbers, not feelings)
- [ ] Risk assessment completed and accepted
- [ ] Requirements Document generated and signed
- [ ] Compliance requirements documented
- [ ] Project plan approved
- [ ] Budget approved
- [ ] All stoppers cleared (no unresolved issues)

---

### Phase 1: Core Implementation (Building)

**Duration:** 2-6 weeks  
**HITL Gate:** MVP validation before Phase 2 (Human decision required)

**⚠️ HITL Stopper Rules for Phase 1:**

- NO architecture changes (locked in Phase 0)
- NO scope additions (new features = next version)
- NO human-AI boundary changes (locked in Phase 0)
- If any of these need to change → STOP → Go back to Phase 0 for new Requirements Document

**If metrics don't match expectations:**
- Option A: Model isn't trained well enough (continue Phase 1, retrain)
- Option B: Vision was wrong (STOP, return to Phase 0)
- Human decides which via multi-optional question

**What happens:**

1. **Setup** — Data pipelines, AI infrastructure, integrations
   - Use architecture from Phase 0 (no architecture changes here)
   - Set up data pipelines
   - Set up monitoring infrastructure
   - Integrate with existing systems
   - Human approval required before proceeding to Build

2. **Build MVP** — Core AI capability only
   - Use architecture from Phase 0 exclusively
   - Test with real data (not synthetic)
   - Test with real users early (1-5 users, not 1000)
   - No architecture decisions—they're locked
   - Daily metrics check: Is it on track?

3. **Monitor Early** — Watch for issues before launch
   - Is the model performing as expected?
   - Are data quality issues appearing?
   - Are there edge cases we missed?
   - Is latency acceptable?
   - **Decision point (every 3 days):** On track or needs pivot?

4. **Iterate on Model** — Improve, don't redesign
   - Better training data? Retrain model
   - Wrong data features? Add features
   - Poor performance on edge cases? Document for Phase 2
   - Model hallucinating? Document patterns for Phase 2
   - **Critical:** No changes to human-AI boundary or architecture

5. **Deliverables**
   - Working AI system (MVP scope from Phase 0 requirements)
   - Real user feedback
   - Model performance baselines
   - Data quality observations
   - Updated Requirements Document with actual vs. planned metrics
   - Ready for Phase 2

**You decide (Human gate):**
- Is the MVP working as envisioned in Phase 0 requirements?
- Are results meeting success metrics (within acceptable margin)?
- Are risks manageable or worse than expected?
- Ready to refine?

**If metrics don't match:**
- Decision: (A) Retrain model (continue Phase 1), (B) Vision was wrong (STOP Phase 1, reset Phase 0), or (C) Reduce scope (accept lower performance)?
- Human chooses via multi-optional question

**HITL Gate Checklist (NO proceeding without all):**
- [ ] Core AI features implemented (exact MVP scope from requirements)
- [ ] Testing with real users completed (1-5 users feedback gathered)
- [ ] Model performance baseline documented (vs. Phase 0 targets)
- [ ] Data quality verified (meets Phase 0 spec)
- [ ] Integration working with existing systems
- [ ] No major errors in production logs
- [ ] Metrics vs. targets: On track or acceptable variance?
- [ ] If metrics off: Resolvable in Phase 2? Or requires Phase 0 reset?
- [ ] Human explicitly approves moving to Phase 2

---

### Phase 2: Refinement & Polish (Improving)

**Duration:** 1-2 weeks  
**HITL Gate:** Production readiness before Phase 3 (Critical human decision)

**⚠️ HITL Stopper: Phase 2 is Refinement Only**

- NO new features (locked in Phase 0 requirements)
- NO architecture changes (locked in Phase 0)
- NO scope additions
- If any needed → STOP → Go back to Phase 0 for Phase 2.0 (next major version)

**What happens:**

1. **Model Optimization** — Make the AI better
   - Reduce hallucination (safer responses)
   - Improve accuracy on edge cases
   - Optimize latency (faster responses)
   - Reduce costs (cheaper inference)
   - Decision point: If optimization can't meet Phase 0 targets → STOP, flag for Phase 4

2. **User Experience** — Make it feel right
   - Clear AI confidence levels
   - Good escalation UX
   - Clear feedback loops
   - Brand/tone alignment

3. **Comprehensive Testing** (This is the main gate)
   - Edge cases (what breaks the model?)
   - Adversarial inputs (malicious prompts?)
   - Data drift (does performance degrade over time?)
   - Compliance verification (GDPR, audit trail, data retention?) ← LEGAL SIGN-OFF REQUIRED
   - Performance under load (100 concurrent users?)
   - Failure modes (what happens when AI is wrong?)

4. **Documentation** — For operations teams
   - How to monitor AI health
   - How to escalate when model fails
   - How to retrain when drift occurs
   - Audit trail procedures

5. **Deliverables**
   - Production-ready AI system
   - All compliance verified ✅
   - All tests passing ✅
   - Operational procedures documented
   - Legal sign-off obtained
   - Ready for launch

**You decide (Human gate - this is critical):**
- Is it safe to launch? (or are there unresolved risks?)
- Are we compliant? (or do we need legal review?)
- Do metrics meet Phase 0 targets? (or acceptable variance?)
- Ready to go live? (or need another Phase 2 iteration?)

**If issues found:**
- Minor fix: Continue Phase 2 (iterate)
- Major issue: STOP Phase 2 → Back to Phase 0 → Plan Phase 2.0

**HITL Gate Checklist (STRICT - all must be YES):**
- [ ] Model optimized and meets Phase 0 success metrics
- [ ] Edge cases tested (document all known issues)
- [ ] Compliance verified: GDPR ✅ Audit trail ✅ Data retention ✅
- [ ] Legal has reviewed and approved for launch
- [ ] Performance tested under real load (latency, accuracy verified)
- [ ] Operational procedures documented and tested
- [ ] Escalation procedures documented and tested
- [ ] Monitoring dashboard tested and active
- [ ] No critical blockers found during testing
- [ ] Human explicitly approves moving to Phase 3

---

### Phase 3: Deployment & Monitoring (Launching)

**Duration:** 3-7 days  
**HITL Gate:** Go-live approval (Human decision, no AI bypass)
**Post-Launch Gate:** Week 1 review (Decide: continue, pause, or rollback)

**⚠️ HITL Stopper: Final Launch Approval is Human-Only**

No AI can approve going live. Only humans.

**What happens:**

1. **Pre-Flight Check** (Human verifies everything)
   - Final stakeholder review (C-suite approval required)
   - Compliance sign-off (Legal approval required)
   - Performance baselines documented
   - Rollback plan ready (can we revert if issues?)
   - Monitoring dashboard active and tested
   - Alert rules configured (what triggers escalation?)
   - Escalation procedures ready (who do we call?)

2. **Launch Decision Gate** (Human decides)
   - **Question:** Are all pre-flight items complete?
   - **If NO:** Don't launch. Wait until all items done.
   - **If YES:** Proceed to deployment
   - **Record:** Who approved launch and when

3. **Deploy**
   - Deploy to production
   - Verify all features work
   - Activate monitoring (watch everything)
   - Activate error tracking
   - Activate feedback collection

4. **Monitor** (First 7 days, intensive)
   - Watch error logs (any unexpected errors?)
   - Gather user feedback (are people satisfied?)
   - Monitor model accuracy (is it performing as expected?)
   - Monitor latency (is it fast enough?)
   - Monitor costs (are we within budget?)
   - Monitor edge cases (is anything breaking?)
   - Log any issues for next version

5. **Week 1 Post-Launch Decision Gate** (Human decides next steps)
   - **Option A:** Continue — AI is working well, proceed to normal monitoring
   - **Option B:** Pause — Found issues, need to fix, pause rollout
   - **Option C:** Rollback — Critical issue found, revert to Phase 2, investigate
   - Human chooses via multi-optional question based on data

6. **Long-term Monitoring** (Ongoing, automatic alerts)
   - Model drift (is accuracy degrading over time?)
   - Data drift (are inputs changing in unexpected ways?)
   - Usage patterns (who's using it, how?)
   - Feedback (what's working, what's not?)
   - Costs (is it within budget?)
   - **Automatic escalation:** If drift detected > threshold, alert human

7. **Deliverables**
   - Live AI system
   - Monitoring active (all metrics)
   - Team trained on operations
   - Escalation procedures active
   - Feedback loop active
   - Success metrics tracked
   - Post-launch decision documented

**You decide (Human gate - launch is GO/NO-GO only):**

**Pre-Launch:**
- Is everything ready? (all pre-flight items done?)
- Are we confident? (or do we need more testing?)
- Go live? (YES or NO)

**Post-Launch (Week 1):**
- Is it working? (Continue, Pause, or Rollback?)
- What did we learn?
- What's next?

**HITL Gate Checklist (Pre-Launch - STRICT):**
- [ ] Pre-flight checklist 100% complete
- [ ] C-Suite approval obtained (recorded)
- [ ] Legal/Compliance approval obtained (recorded)
- [ ] Performance baselines documented (Phase 0 targets vs. actual)
- [ ] Rollback procedure tested and ready
- [ ] Monitoring dashboard active and tested
- [ ] Alert rules configured
- [ ] Escalation procedures documented
- [ ] Team trained on operations
- [ ] Launch approval: YES or NO (Human signature required)

**Post-Launch Decision (Week 1 - Human chooses):**
- [ ] Continue (working well, proceed)
- [ ] Pause (issues found, need fixes, no new traffic)
- [ ] Rollback (critical issue, revert to Phase 2)
- Decision recorded with rationale

---

## Version Management for AI

### Versioning Scheme: x.y.z

- **x = Major version** — Phase completion (x.0 at Phase 3 launch)
- **y = Model version** — Model retrain (1.1, 1.2, 1.3 = retrained model)
- **z = Patch** — Bug fix or data quality fix

**Example Timeline:**

```
Phase 0: Planning (complete)
Phase 1: 
  1.0.0 (MVP launched)
  1.1.0 (Model retrained with better data)
  1.2.0 (Model optimized for speed)
  1.3.0 (Model accuracy improved)
Phase 2:
  2.0.0 (Phase 2 complete, production ready)
Phase 3: [Launch to production]
  3.0.0 (Live, production monitoring)
  3.1.0 (Model retrained based on live feedback)
  3.2.0 (Model optimized for new use case)
Next major: 4.0.0 (Major feature or architecture change)
```

---

## Planning Your AI Project

### Before Phase 0 Starts

Answer these strategic questions:

1. **Why AI?** — What problem does AI solve that other tech doesn't?
2. **Vision** — What will the AI do? (1-2 sentences)
3. **Success** — How will we measure success? (metrics, not feelings)
4. **Constraints** — Budget? Timeline? Risk tolerance?
5. **Stakeholders** — Who needs to approve? Who needs to understand?

### During Each Phase

1. **Start of phase** — Read phase description above
2. **During phase** — Work through the phase
3. **End of phase** — HITL gate review (approve to proceed)

### Governance

Maintain a `GOVERNANCE.md` file:

```markdown
# Project: AI Support Assistant

## Governance

### Decision Makers
- C-Suite: Approves vision, risk, budget
- Product: Owns success metrics
- Engineering: Owns architecture
- Legal: Owns compliance

### Review Gates
- Phase 0→1: C-Suite approval
- Phase 1→2: Product + Engineering approval
- Phase 2→3: Legal + Security approval
- Pre-Launch: All stakeholders

### Metrics Tracking
- Model accuracy: Target 95%, current 93%
- Response time: Target <2s, current 1.8s
- Cost: Target $5k/month, current $4.2k/month

### Risk Monitoring
- Hallucination rate: <1%
- Escalation rate: 35% (target 40%)
- User satisfaction: 85% (target 90%)
```

---

## HITL Gates Explained

**HITL = Human-In-The-Loop**

At critical moments, humans (leaders) decide the direction. This prevents expensive mistakes.

### Gate Checkpoints

**Phase 0 → Phase 1 Gate:**
- Is the vision realistic?
- Is the architecture sound?
- Are risks acceptable?
- Ready to build?

**Phase 1 → Phase 2 Gate:**
- Is the MVP working?
- Are metrics on track?
- What did we learn?
- Ready to refine?

**Phase 2 → Phase 3 Gate:**
- Is it safe to launch?
- Are we compliant?
- Are metrics locked?
- Ready to go live?

**Post-Launch Gate (Week 2):**
- How is the AI performing?
- What's the user feedback?
- What should we improve?
- Continue or iterate?

---

## Common Questions

**Q: Our vendor said we should skip Phase 0 and start building.**  
A: Don't. Vendors profit from ambiguous requirements. Phase 0 prevents vendor lock-in and bad decisions. 5 hours of planning saves 40 hours of rework.

**Q: Can we change the AI model in Phase 1?**  
A: You can retrain, optimize, improve. You can't change the architecture (that's locked). Architecture changes = new version.

**Q: What if the AI doesn't work in Phase 1?**  
A: That's why Phase 0 exists. If the MVP fails, Phase 0 decisions were wrong. Go back to Phase 0, not forward to Phase 1.1.

**Q: How long does this take?**  
A: Typical AI project: Phase 0 (5 days) + Phase 1 (4 weeks) + Phase 2 (2 weeks) + Phase 3 (1 week) = ~8 weeks. High-uncertainty projects take longer in Phase 0.

**Q: What if we're in a race and need to move fast?**  
A: Speed comes from clarity, not rushing. Phase 0 gives you clarity. Rushing Phase 0 leads to 5-30x rework. Don't skip gates.

**Q: What about iterative development / agile?**  
A: Phases aren't waterfall—they're strategic gates. Phase 1 is iterative (1.0, 1.1, 1.2). Phase 2 is iterative. But you don't iterate on *architecture*—that's locked in Phase 0.

---

## The Philosophy

This operating system exists because AI projects have unique demands:

- **AI requires architecture clarity** — You can't iterate on whether to use LLMs or fine-tune after you've built
- **Data quality is foundational** — Bad data in Phase 0 means bad model in Phase 1
- **Human-AI boundaries matter** — Ambiguous on this = endless rework
- **Risk is real** — Hallucination, drift, compliance—these need Phase 0 planning
- **Monitoring is not optional** — You must monitor what you deploy

By separating vision (Phase 0), building (Phase 1), refinement (Phase 2), and launch (Phase 3), AI projects get:

- ✅ **Clarity** — Everyone understands the AI strategy
- ✅ **Quality** — Testing happens throughout, not at the end
- ✅ **Speed** — Clear scope prevents delays
- ✅ **Safety** — AI behavior is architected and monitored
- ✅ **Learning** — Each phase documents what we learned

---

## Getting Started

1. Read this document
2. Work through Phase 0 for your AI project
3. Get stakeholder alignment and approval
4. Move to Phase 1 (building)
5. Follow gates through to launch
6. Track version (x.y.z) as you progress
7. Monitor continuously after launch

---

## Part of AI Leadership Program

This methodology is part of the **AI Leadership Program**—an operating system for executives navigating Strategic Vertigo (overwhelm from AI noise).

The program includes:
- **4-Station Model:** Intelligence → Audit → CORE → Strategy
- **This skill:** AI Leadership Dev (how to build with AI)
- **Positioning framework:** For AI companies articulating value
- **Decision framework:** For evaluating AI vendors and tools

**Learn more:** [Clarity Beyond AI | AI Leadership](https://www.linkedin.com/in/hanrabinovitz/)

---

**License:** MIT  
**Author:** Han Rabinovitz | [Clarity Beyond AI](https://www.linkedin.com/in/hanrabinovitz/)  
**Program:** AI Leadership Program (Strategic Vertigo navigation for executives)
