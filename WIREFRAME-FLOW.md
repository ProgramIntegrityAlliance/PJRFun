# Wireframe & User Flow Documentation

This document provides a visual representation of the user journey through the Fraud Prevention Capability Assessment tool.

---

## 📱 Screen Flow Overview

```
┌─────────────────┐
│  Introduction   │
│     Screen      │
└────────┬────────┘
         │
         ↓
┌─────────────────┐
│   Domain 1      │
│ (3 Questions)   │
└────────┬────────┘
         │
         ↓
┌─────────────────┐
│   Domain 2      │
│ (3 Questions)   │
└────────┬────────┘
         │
         ↓
┌─────────────────┐
│   Domain 3      │
│ (3 Questions)   │
└────────┬────────┘
         │
         ↓
┌─────────────────┐
│   Domain 4      │
│ (3 Questions)   │
└────────┬────────┘
         │
         ↓
┌─────────────────┐
│   Domain 5      │
│ (3 Questions)   │
└────────┬────────┘
         │
         ↓
┌─────────────────┐
│     Results     │
│      Page       │
└─────────────────┘
```

**Total Steps:** 7 (1 intro + 5 domains + 1 results)
**Total Questions:** 15
**Estimated Time:** 10-15 minutes

---

## 🖥️ Screen 1: Introduction

### Layout

```
┌──────────────────────────────────────────────────────────┐
│ Fraud Prevention Capability Assessment                   │
│ ─────────────────────────────────────────────────────    │
│ Use this quick self-assessment to get a snapshot...      │
│                                                           │
│ Introduction                                              │
│ [Progress Bar: ░░░░░░░░░░░░░░░░░░░░] 0%                 │
├──────────────────────────────────────────────────────────┤
│                                                           │
│ Welcome to the Fraud Prevention Capability Assessment    │
│                                                           │
│ This assessment will help you evaluate your               │
│ organization's fraud prevention maturity across five      │
│ critical domains:                                         │
│                                                           │
│ • Governance and Accountability: Leadership, policies...  │
│ • Fraud Risk Assessment: How you identify risks...       │
│ • Data and Analytics: Using data to prevent fraud...     │
│ • Controls and Operations: Prevention mechanisms...      │
│ • Monitoring and Learning: Performance tracking...       │
│                                                           │
│ The assessment takes approximately 10-15 minutes.        │
│                                                           │
│ Your responses are saved automatically in your browser.  │
│                                                           │
├──────────────────────────────────────────────────────────┤
│                                                           │
│ [Previous]                      [Start Assessment ➜]     │
│                                                           │
└──────────────────────────────────────────────────────────┘
```

### Elements

- **Header:** Title + subtitle + progress indicator
- **Content:** Welcome text, domain overview, estimated time
- **Navigation:** Previous button (disabled), "Start Assessment" button

### Interactions

- **Next Button:** Advances to Domain 1
- **Previous Button:** Disabled on this screen

---

## 🖥️ Screens 2-6: Question Domains

### Layout (Example: Domain 1)

```
┌──────────────────────────────────────────────────────────┐
│ Fraud Prevention Capability Assessment                   │
│ ─────────────────────────────────────────────────────────│
│ Use this quick self-assessment to get a snapshot...      │
│                                                           │
│ Section 1 of 5                                            │
│ [Progress Bar: ███████░░░░░░░░░░░░░] 20%                │
├──────────────────────────────────────────────────────────┤
│                                                           │
│ Governance and accountability                            │
│ Consider policies, roles, and leadership expectations... │
│                                                           │
│ ┌────────────────────────────────────────────────────┐  │
│ │ 1. Clear roles and responsibilities for fraud risk  │  │
│ │    management are defined and communicated.         │  │
│ │                                                      │  │
│ │ ○ Not in place  ○ Basic  ○ Developing               │  │
│ │ ○ Good  ○ Fully in place                            │  │
│ └────────────────────────────────────────────────────┘  │
│                                                           │
│ ┌────────────────────────────────────────────────────┐  │
│ │ 2. Senior leaders receive regular reporting on      │  │
│ │    fraud risks and prevention activity.             │  │
│ │                                                      │  │
│ │ ○ Not in place  ○ Basic  ○ Developing               │  │
│ │ ○ Good  ○ Fully in place                            │  │
│ └────────────────────────────────────────────────────┘  │
│                                                           │
│ ┌────────────────────────────────────────────────────┐  │
│ │ 3. There is a documented fraud risk management      │  │
│ │    policy covering prevention, detection, response. │  │
│ │                                                      │  │
│ │ ○ Not in place  ○ Basic  ○ Developing               │  │
│ │ ○ Good  ○ Fully in place                            │  │
│ └────────────────────────────────────────────────────┘  │
│                                                           │
├──────────────────────────────────────────────────────────┤
│ [← Previous]                               [Next ➜]      │
└──────────────────────────────────────────────────────────┘
```

### Elements

- **Domain Title:** "Governance and accountability"
- **Hint Text:** Contextual guidance for the domain
- **Questions:** 3 questions with 5-point radio scale each
- **Progress Indicator:** "Section X of 5" + progress bar
- **Navigation:** Previous and Next buttons

### Interactions

- **Radio Selection:** Click to select maturity level
- **Auto-save:** Each selection is saved to localStorage
- **Hover Effects:** Question boxes highlight on hover
- **Validation:** Cannot proceed without answering all questions
- **Next Button:**
  - On sections 1-4: Goes to next domain
  - On section 5: Shows "View Results" text
- **Previous Button:** Returns to previous section

### Validation Alert

If user clicks Next without answering all questions:

```
┌──────────────────────────────────────────────────────────┐
│ ⚠ Please answer all questions in this section before     │
│   continuing.                                             │
└──────────────────────────────────────────────────────────┘
```

---

## 🖥️ Screen 7: Results Page

### Layout

```
┌──────────────────────────────────────────────────────────┐
│ Fraud Prevention Capability Assessment                   │
│ ─────────────────────────────────────────────────────────│
│ Use this quick self-assessment to get a snapshot...      │
│                                                           │
│ Results                                                   │
│ [Progress Bar: ████████████████████] 100%               │
├──────────────────────────────────────────────────────────┤
│                                                           │
│ Your results                                             │
│ These scores are indicative, not an audit. Use them to  │
│ start a focused discussion...                            │
│                                                           │
│ Overall capability: 67/100 [Established]                 │
│                                                           │
│ ┌────────────────────────────────────────────────────┐  │
│ │ Domain Scores Overview                              │  │
│ │                                                      │  │
│ │     ▮▮▮▮▮▮▮▮▮▮▮▮▮▮ Governance (70%)                │  │
│ │     ▮▮▮▮▮▮▮▮▮▮ Fraud Risk Assessment (50%)          │  │
│ │     ▮▮▮▮▮▮▮▮▮▮▮▮▮▮▮▮▮ Data & Analytics (85%)       │  │
│ │     ▮▮▮▮▮▮▮▮▮▮▮▮ Controls (60%)                     │  │
│ │     ▮▮▮▮▮▮▮▮▮▮▮▮▮▮▮ Monitoring (75%)               │  │
│ │                                                      │  │
│ └────────────────────────────────────────────────────┘  │
│                                                           │
│ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐        │
│ │ Governance  │ │  Risk       │ │  Data &     │        │
│ │ Score: 70   │ │  Assessment │ │  Analytics  │        │
│ │ Established │ │  Score: 50  │ │  Score: 85  │        │
│ │             │ │  Developing │ │  Leading    │        │
│ │ Description │ │             │ │             │        │
│ │ & Next step │ │ Description │ │ Description │        │
│ └─────────────┘ └─────────────┘ └─────────────┘        │
│                                                           │
│ ┌─────────────┐ ┌─────────────┐                         │
│ │ Controls    │ │ Monitoring  │                         │
│ │ Score: 60   │ │ Score: 75   │                         │
│ │ Established │ │ Established │                         │
│ │             │ │             │                         │
│ │ Description │ │ Description │                         │
│ │ & Next step │ │ & Next step │                         │
│ └─────────────┘ └─────────────┘                         │
│                                                           │
│ [Download PDF Report] [Start New Assessment]            │
│                                                           │
├──────────────────────────────────────────────────────────┤
│ [← Back to answers]                                      │
│ You can also print this page (Ctrl+P) or save from      │
│ your browser.                                            │
└──────────────────────────────────────────────────────────┘
```

### Elements

- **Overall Score Badge:** Score + maturity level
- **Chart:** Bar chart showing all domain scores
- **Domain Cards (5):** Individual cards with:
  - Domain name
  - Score (0-100)
  - Maturity level (with color badge)
  - Description of level
  - Specific next step recommendation
- **Action Buttons:**
  - Download PDF Report
  - Start New Assessment
- **Back Navigation:** Return to last question section
- **Helper Text:** Instruction for printing/saving

### Interactions

- **Download PDF:** Generates and downloads PDF report
- **Start New Assessment:** Confirms, then clears all data and returns to intro
- **Back Button:** Returns to Section 5 (last question page)
- **Print:** Browser's native print functionality (Ctrl+P)

---

## 🎨 Visual Design Elements

### Color Scheme

```
Primary (Teal):    ████ #00404a (headings, buttons)
Light Teal:        ████ #0f9c91 (hover states, accents)
Orange:            ████ #e84e0f (CTAs, warnings)
Background:        ████ #f5f7f8 (page background)
Text Main:         ████ #222222 (body text)
Text Muted:        ████ #555555 (hints, secondary text)
Border:            ████ #dde2e6 (dividers, cards)
```

### Maturity Level Colors

```
Emerging:    ████ Orange/Red tones (#c65305)
Developing:  ████ Yellow/Amber tones (#856404)
Established: ████ Green tones (#1b6d2f)
Leading:     ████ Blue tones (#0b5394)
```

### Typography

```
Title:          1.4rem, Bold
Section Title:  1.05rem, Bold
Body Text:      0.95rem, Regular
Hint Text:      0.88rem, Regular
Small Text:     0.8rem, Regular
```

### Spacing & Layout

```
Max Width:      900px (centered)
Padding:        24px
Card Radius:    8-10px
Button Radius:  999px (pill shape)
Question Gap:   10px
Section Gap:    15-20px
```

---

## 📱 Mobile Responsive Behavior

### Breakpoint: < 600px

**Changes:**
- Radio buttons stack vertically
- Cards become full-width
- Font sizes slightly reduced
- Padding reduced (16px instead of 24px)
- Buttons become full-width
- Chart maintains aspect ratio

### Mobile Layout Example

```
┌──────────────────────┐
│ Title                │
│ ─────────────────    │
│ Subtitle             │
│                      │
│ Section 1 of 5       │
│ [Progress ████░░] 20%│
├──────────────────────┤
│                      │
│ Domain Title         │
│ Hint text...         │
│                      │
│ ┌──────────────────┐ │
│ │ Question 1       │ │
│ │                  │ │
│ │ ○ Not in place   │ │
│ │ ○ Basic          │ │
│ │ ○ Developing     │ │
│ │ ○ Good           │ │
│ │ ○ Fully in place │ │
│ └──────────────────┘ │
│                      │
│ [More questions...]  │
│                      │
├──────────────────────┤
│ [← Previous]         │
│ [Next ➜]            │
└──────────────────────┘
```

---

## 🔄 User Interaction States

### Question Card States

**Default:**
```
┌────────────────────────────────┐
│ Question text                  │
│ ○ Not  ○ Basic  ○ Developing   │
└────────────────────────────────┘
```

**Hover:**
```
┌════════════════════════════════┐ (border changes to teal)
│ Question text                  │
│ ○ Not  ○ Basic  ○ Developing   │
└════════════════════════════════┘
```

**Answered:**
```
┌────────────────────────────────┐
│ Question text                  │
│ ○ Not  ● Basic  ○ Developing   │ (selected option highlighted)
└────────────────────────────────┘
```

### Button States

**Primary Button (Normal):**
```
[ Next ➜ ] (teal background, white text)
```

**Primary Button (Hover):**
```
[ Next ➜ ] (lighter teal background)
```

**Primary Button (Disabled):**
```
[ Next ➜ ] (faded, cursor: not-allowed)
```

**Secondary Button (Normal):**
```
[ ← Previous ] (white background, border)
```

**Secondary Button (Hover):**
```
[ ← Previous ] (light gray background)
```

---

## 🎭 Animations & Transitions

### Page Transitions
- **Fade-in:** 0.3s ease-in when new section appears
- **Slide-up:** Slight upward motion (10px) during fade-in

### Progress Bar
- **Width transition:** 0.25s ease-out as it fills

### Button Hovers
- **All transitions:** 0.2s for smooth hover effects

### Alert Messages
- **Appear:** Slide down from top when validation fails
- **Disappear:** Fade out when resolved

---

## 📊 Results Page Components

### Overall Score Badge

```
┌──────────────────────────────────┐
│ Overall capability: 67/100       │
│                      [Established]│
└──────────────────────────────────┘
```

### Bar Chart (Chart.js)

```
Domain Scores Overview
━━━━━━━━━━━━━━━━━━━━

Governance and      ████████████████ 75%
accountability

Fraud risk          ██████████ 50%
assessment

Data and analytics  ████████████████████ 90%

Controls and        ███████████████ 67%
operations

Monitoring, oversight ████████████████ 73%
and learning

0%  10%  20%  30%  40%  50%  60%  70%  80%  90%  100%
```

### Domain Card Detail

```
┌────────────────────────────────────────┐
│ Governance and accountability          │
│                                        │
│ Score: 75/100                          │
│ Level: Established                     │
│                                        │
│ Fraud prevention is part of regular   │
│ management practice. The next step is │
│ to strengthen data use and continuous │
│ improvement.                           │
│                                        │
│ Next step: Integrate fraud prevention │
│ into strategic planning. Consider     │
│ external benchmarking.                │
└────────────────────────────────────────┘
```

---

## 🖨️ PDF Export Structure

When user clicks "Download PDF Report", the generated PDF includes:

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Fraud Prevention Capability Assessment
Generated: [Date]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Overall Capability
Score: 67/100 (Established)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Domain Scores
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Governance and accountability
Score: 75/100 (Established)
Recommendation: [text]

Fraud risk assessment
Score: 50/100 (Developing)
Recommendation: [text]

[etc. for all domains]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
This is an indicative self-assessment,
not an audit or certification.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## 💾 Data Flow & Storage

### localStorage Structure

```javascript
{
  "fp-assessment-data": {
    "q1": "3",
    "q2": "4",
    "q3": "2",
    ...
    "q15": "5"
  }
}
```

### Save Events
- Triggered on each radio button selection
- Updates localStorage immediately
- No explicit "Save" button needed

### Load Events
- On page load, checks for existing data
- Auto-populates answers if found
- Allows continuation of partially completed assessment

---

## 🚀 Performance Considerations

### Load Time Optimization
- **HTML/CSS/JS:** Inline (no external files except CDN)
- **Chart.js:** Loaded from CDN (~60KB)
- **jsPDF:** Loaded from CDN (~140KB)
- **Total First Load:** < 1 second on broadband

### Runtime Performance
- Vanilla JavaScript (no framework overhead)
- Minimal DOM manipulation
- Event delegation for efficiency
- Chart rendered only once on results page

---

## ♿ Accessibility Features

### Keyboard Navigation
- Tab through all form elements
- Space/Enter to select radio buttons
- Arrow keys to navigate radio groups

### Screen Reader Support
- Proper label associations
- ARIA attributes where needed
- Semantic HTML structure

### Visual Accessibility
- High contrast text (WCAG AA compliant)
- Clear focus indicators
- No color-only information conveyance

---

## 🧪 Testing Checklist

### Functional Testing
- [ ] All radio buttons can be selected
- [ ] Progress bar updates correctly
- [ ] Validation prevents skipping questions
- [ ] localStorage saves and loads correctly
- [ ] Chart renders with all domains
- [ ] PDF downloads with correct data
- [ ] Reset clears all data
- [ ] Back navigation works

### Cross-Browser Testing
- [ ] Chrome
- [ ] Firefox
- [ ] Safari
- [ ] Edge
- [ ] Mobile browsers

### Responsive Testing
- [ ] Desktop (> 900px)
- [ ] Tablet (600-900px)
- [ ] Mobile (< 600px)
- [ ] Print layout

### Performance Testing
- [ ] Page loads in < 2 seconds
- [ ] No JavaScript errors in console
- [ ] Smooth transitions and animations

---

## 📐 Design Specifications

### Component Dimensions

```
Wrapper:           900px max-width
Header Padding:    12px bottom
Progress Bar:      6px height
Question Card:     12px padding
                   8px border-radius
Radio Button:      5px gap between options
Button Padding:    8px vertical, 16px horizontal
Chart Height:      300px max
Result Card:       210px min-width
```

### Z-Index Layers

```
Base Layer:        z-index: 1 (content)
Alert Layer:       z-index: 10 (validation alerts)
Modal Layer:       z-index: 100 (future use)
```

---

## 🎯 Conversion Optimization

### Call-to-Action Hierarchy

**Primary Actions:**
1. "Start Assessment" (intro)
2. "Next" (each domain)
3. "View Results" (last domain)
4. "Download PDF" (results)

**Secondary Actions:**
1. "Previous" (navigation)
2. "Back to answers" (results)
3. "Start New Assessment" (results)

### Progress Indicators
- Visual progress bar (0-100%)
- Text indicator ("Section X of 5")
- Completed state ("Results")

---

This wireframe documentation provides a complete visual reference for understanding and modifying the assessment tool structure.
