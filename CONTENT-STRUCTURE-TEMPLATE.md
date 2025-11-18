# Content Structure Template for Custom Fraud Risk Indicators

This guide explains how to customize the assessment tool with your own indicators, domains, and questions.

---

## Assessment Structure Overview

The tool is organized as follows:

```
1. Introduction Page (optional)
2. Domain 1 → Questions 1-3
3. Domain 2 → Questions 4-6
4. Domain 3 → Questions 7-9
5. Domain 4 → Questions 10-12
6. Domain 5 → Questions 13-15
7. Results Page (auto-generated)
```

Each domain represents a key area of fraud risk management capability.

---

## Current Domains & Questions

### Domain 1: Governance and Accountability
**Focus:** Leadership, policies, roles

**Questions:**
1. Clear roles and responsibilities for fraud risk management
2. Senior leaders receive regular fraud risk reporting
3. Documented fraud risk management policy

### Domain 2: Fraud Risk Assessment
**Focus:** Risk identification and prioritization

**Questions:**
4. Regular structured fraud risk assessments
5. Assessment considers inherent and residual risk
6. Fraud risks integrated into enterprise risk management

### Domain 3: Data and Analytics
**Focus:** Using data to prevent/detect fraud

**Questions:**
7. Key datasets available and linked for analysis
8. Analytics/rules flag high-risk cases before payment
9. Data engineers work with fraud staff to refine models

### Domain 4: Controls and Operations
**Focus:** Prevention and detection mechanisms

**Questions:**
10. Fraud controls documented and mapped to risks
11. Preventive controls embedded in systems
12. Clear procedures for handling suspected fraud

### Domain 5: Monitoring, Oversight, and Learning
**Focus:** Performance tracking and improvement

**Questions:**
13. Track fraud prevention performance indicators
14. Oversight recommendations tracked and implemented
15. Lessons from fraud cases inform design changes

---

## How to Add or Modify Domains

### Step 1: Plan Your Domain Structure

Create a table like this:

| Domain | Focus Area | # Questions | Question Topics |
|--------|-----------|-------------|-----------------|
| Financial Controls | Payment integrity | 3 | Verification, approval, segregation |
| Identity Verification | Know Your Customer | 3 | ID checks, biometrics, databases |
| Third-Party Risk | Vendor/supplier fraud | 3 | Due diligence, monitoring, contracts |

### Step 2: Write Your Questions

For each domain, write 3-5 questions following this template:

```
[Domain]: [Focus Area]
Hint: [Contextual guidance for respondents]

Question X: [Clear statement about a specific capability or practice]
Scale: 1 (Not in place) → 5 (Fully in place)
```

**Example:**

```
Domain: Identity Verification
Hint: Think about how you confirm someone is who they claim to be.

Question 7: The organization uses multiple data sources to verify customer identity before onboarding.
Scale: 1 (Not in place) → 2 (Basic) → 3 (Developing) → 4 (Good) → 5 (Fully in place)
```

### Step 3: Add to HTML

Find this section in the HTML file (around line 300):

```html
<!-- Step 2: Your Domain Name -->
<div class="fp-step" data-step="2" data-domain="Your Domain Name">
  <div class="fp-section-title">Your Domain Name</div>
  <div class="fp-section-hint">
    Your hint text here - helps respondents understand what to consider.
  </div>

  <div class="fp-question">
    <div class="fp-question-text">
      4. Your question text here.
    </div>
    <div class="fp-scale" data-domain-question>
      <label><input type="radio" name="q4" value="1"><span>Not in place</span></label>
      <label><input type="radio" name="q4" value="2"><span>Basic</span></label>
      <label><input type="radio" name="q4" value="3"><span>Developing</span></label>
      <label><input type="radio" name="q4" value="4"><span>Good</span></label>
      <label><input type="radio" name="q4" value="5"><span>Fully in place</span></label>
    </div>
  </div>

  <!-- Repeat for each question in this domain -->

</div>
```

**Important:**
- Each question needs a UNIQUE name (q1, q2, q3, etc.)
- Update the `data-step` number sequentially
- Update the `data-domain` attribute with your domain name
- Keep the same HTML structure and class names

---

## Maturity Level Definitions

The tool classifies scores into four maturity levels:

| Score Range | Level | Meaning |
|-------------|-------|---------|
| 0-29% | **Emerging** | Basic elements present, mostly ad hoc |
| 30-59% | **Developing** | Building blocks in place, uneven coverage |
| 60-79% | **Established** | Regular management practice, systematic |
| 80-100% | **Leading** | Actively managed, data-informed, innovative |

### Customizing Level Descriptions

Find the `getLevelText()` function (around line 800) and modify:

```javascript
function getLevelText(level) {
  switch (level) {
    case "Emerging":
      return "Your custom description for Emerging maturity...";
    case "Developing":
      return "Your custom description for Developing maturity...";
    case "Established":
      return "Your custom description for Established maturity...";
    case "Leading":
      return "Your custom description for Leading maturity...";
    default:
      return "";
  }
}
```

### Customizing Recommendations by Domain

Find the `getRecommendations()` function (around line 820) and modify:

```javascript
function getRecommendations(domain, level) {
  const recommendations = {
    "Your Domain Name": {
      "Emerging": "Do this first step...",
      "Developing": "Next, focus on...",
      "Established": "To advance further...",
      "Leading": "Consider sharing..."
    },
    // Add more domains...
  };
  return recommendations[domain]?.[level] || "";
}
```

---

## Question Writing Best Practices

### ✅ Good Question Examples

**Clear and specific:**
> "Payment approvals require authorization from two independent staff members."

**Observable behavior:**
> "The fraud risk register is reviewed and updated at least quarterly."

**Appropriate scope:**
> "Key fraud controls are documented and accessible to relevant staff."

### ❌ Avoid These

**Too vague:**
> "We care about fraud prevention."

**Multiple concepts in one question:**
> "We have policies, training, and monitoring for fraud."

**Requires specialized knowledge:**
> "Our Bayesian fraud detection algorithms are optimized for Type I errors."

---

## Scoring Considerations

### Number of Questions

- **3 questions per domain:** Fast, high-level snapshot
- **5 questions per domain:** Balanced, recommended
- **7+ questions per domain:** Detailed, but increases completion time

**Current tool:** 15 questions (5 domains × 3 questions) ≈ 10-15 minutes

### Scale Options

**Current 5-point scale:**
1. Not in place
2. Basic
3. Developing
4. Good
5. Fully in place

**Alternative scales you could use:**

**Frequency scale:**
- Never
- Rarely
- Sometimes
- Often
- Always

**Agreement scale:**
- Strongly disagree
- Disagree
- Neutral
- Agree
- Strongly agree

**Capability scale:**
- No capability
- Initial capability
- Developing capability
- Established capability
- Advanced capability

---

## Template: Adding a New Domain

Here's a complete template for adding a new domain:

```html
<!-- Step X: [Your Domain Name] -->
<div class="fp-step" data-step="X" data-domain="[Your Domain Name]">
  <div class="fp-section-title">[Your Domain Name]</div>
  <div class="fp-section-hint">
    [Guidance text: What should respondents think about when answering?]
  </div>

  <!-- Question 1 -->
  <div class="fp-question">
    <div class="fp-question-text">
      X. [Your question text - be specific and actionable]
    </div>
    <div class="fp-scale" data-domain-question>
      <label><input type="radio" name="qX" value="1"><span>Not in place</span></label>
      <label><input type="radio" name="qX" value="2"><span>Basic</span></label>
      <label><input type="radio" name="qX" value="3"><span>Developing</span></label>
      <label><input type="radio" name="qX" value="4"><span>Good</span></label>
      <label><input type="radio" name="qX" value="5"><span>Fully in place</span></label>
    </div>
  </div>

  <!-- Question 2 -->
  <div class="fp-question">
    <div class="fp-question-text">
      X. [Your second question text]
    </div>
    <div class="fp-scale" data-domain-question>
      <label><input type="radio" name="qX" value="1"><span>Not in place</span></label>
      <label><input type="radio" name="qX" value="2"><span>Basic</span></label>
      <label><input type="radio" name="qX" value="3"><span>Developing</span></label>
      <label><input type="radio" name="qX" value="4"><span>Good</span></label>
      <label><input type="radio" name="qX" value="5"><span>Fully in place</span></label>
    </div>
  </div>

  <!-- Question 3 -->
  <div class="fp-question">
    <div class="fp-question-text">
      X. [Your third question text]
    </div>
    <div class="fp-scale" data-domain-question>
      <label><input type="radio" name="qX" value="1"><span>Not in place</span></label>
      <label><input type="radio" name="qX" value="2"><span>Basic</span></label>
      <label><input type="radio" name="qX" value="3"><span>Developing</span></label>
      <label><input type="radio" name="qX" value="4"><span>Good</span></label>
      <label><input type="radio" name="qX" value="5"><span>Fully in place</span></label>
    </div>
  </div>

</div>
```

**Don't forget to:**
1. Update `data-step="X"` with the correct step number
2. Update `data-domain="[Your Domain Name]"` with your actual domain name
3. Update all question numbers and `name="qX"` attributes to be unique
4. Update the JavaScript if you change the number of domains (see below)

---

## Updating JavaScript for Domain Changes

If you **add or remove domains**, update this line in the JavaScript (around line 700):

```javascript
const totalQuestionSteps = 5; // Change this to match your number of domains
```

For example:
- 3 domains → `const totalQuestionSteps = 3;`
- 6 domains → `const totalQuestionSteps = 6;`
- 8 domains → `const totalQuestionSteps = 8;`

---

## Example: Payment Fraud Focus

Here's a complete example for a **payment fraud-focused** assessment:

### Domain 1: Payment Authorization
```
1. All payments above $[threshold] require dual authorization
2. Payment approval limits are defined and enforced by system controls
3. Payment approvers are rotated and cannot approve their own requests
```

### Domain 2: Vendor Verification
```
4. New vendor registrations require documented due diligence
5. Vendor master data changes trigger automated alerts
6. High-risk vendor relationships undergo periodic re-verification
```

### Domain 3: Transaction Monitoring
```
7. Automated rules flag duplicate payments or unusual patterns
8. Alerts are reviewed and resolved within defined timeframes
9. False positive rates are tracked and used to tune detection rules
```

### Domain 4: Data Quality
```
10. Vendor and customer databases are regularly deduplicated
11. Payment data is validated against purchase orders and contracts
12. Master data governance includes fraud risk considerations
```

### Domain 5: Investigation & Response
```
13. Suspected payment fraud cases follow a documented escalation process
14. Investigation outcomes are tracked and inform control improvements
15. Recovery actions are pursued systematically for confirmed fraud
```

---

## Fraud Risk Indicator Examples by Domain Type

### Identity Fraud
- Document verification processes
- Biometric authentication
- Identity data cross-checking
- Synthetic identity detection
- Customer due diligence

### Procurement Fraud
- Supplier due diligence
- Bid rigging prevention
- Conflict of interest management
- Invoice verification
- Contract compliance monitoring

### Benefits/Claims Fraud
- Eligibility verification
- Claims validation rules
- Cross-agency data matching
- Anomaly detection
- Post-payment review

### Payroll Fraud
- Employee master data validation
- Ghost employee detection
- Time and attendance verification
- Bank account validation
- Segregation of duties

### Revenue/Tax Fraud
- Filing validation
- Income verification
- Asset cross-referencing
- Refund screening
- Third-party reporting

---

## Testing Your Custom Assessment

After making changes, test:

1. **Navigation:** Can you move through all sections?
2. **Validation:** Try clicking "Next" without answering - does it block you?
3. **Scoring:** Complete the assessment - do all domains appear in results?
4. **Chart:** Does the visualization show all your domains?
5. **PDF:** Does the PDF include all your custom content?
6. **Mobile:** Does it work on a phone?

---

## Quick Reference: Key Variables to Update

| What to Change | Where in File | Example |
|----------------|---------------|---------|
| Number of domains | Line ~700 | `const totalQuestionSteps = 5;` |
| Domain names | Each `<div class="fp-step">` | `data-domain="Your Domain"` |
| Questions | Each `<div class="fp-question-text">` | Question text |
| Question IDs | Each `name="qX"` | q1, q2, q3... |
| Level descriptions | Function `getLevelText()` | Custom text |
| Recommendations | Function `getRecommendations()` | Domain-specific advice |
| Colors | CSS `:root` variables | `--pia-teal: #00404a;` |
| Title | `<h1 class="fp-title">` | Tool name |

---

## Need Help?

Common issues:

**Problem:** Results page shows wrong domain names
- **Fix:** Make sure `data-domain` attributes match exactly in HTML and JavaScript

**Problem:** Some questions don't count toward score
- **Fix:** Verify each question has unique `name="qX"` and is inside a step with `data-step` attribute

**Problem:** Progress bar doesn't reach 100%
- **Fix:** Check that `totalQuestionSteps` matches the number of question sections

---

## Resources & References

**Fraud risk frameworks you might reference:**
- COSO Fraud Risk Management Guide
- ACFE (Association of Certified Fraud Examiners) resources
- ISO 37001 Anti-Bribery Management Systems
- UK National Audit Office Fraud Risk Management Standards
- GAO Fraud Risk Framework (US Government Accountability Office)

**Assessment design principles:**
- Keep questions focused (one concept per question)
- Use clear, plain language
- Make questions observable/verifiable
- Balance comprehensiveness with completion time
- Provide context hints for each domain
- Ensure maturity levels are meaningful and actionable

---

Good luck customizing your fraud risk assessment tool! Remember: the best assessment is one that's actually completed - so prioritize clarity and brevity.
