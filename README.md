# Fraud Prevention Capability Assessment Tool

A modern, self-hosted web application for assessing organizational fraud risk management maturity across multiple domains.

![Assessment Tool](https://img.shields.io/badge/Type-Self--Assessment-blue)
![License](https://img.shields.io/badge/License-MIT-green)
![Status](https://img.shields.io/badge/Status-Production%20Ready-brightgreen)

---

## 🎯 Overview

This is a complete, production-ready fraud prevention capability assessment tool that helps organizations evaluate their fraud risk management maturity. It provides immediate, actionable feedback across five critical domains:

1. **Governance and Accountability**
2. **Fraud Risk Assessment**
3. **Data and Analytics for Fraud Prevention**
4. **Controls and Operations**
5. **Monitoring, Oversight, and Learning**

---

## ✨ Features

### Core Functionality
- ✅ **15 Assessment Questions** across 5 fraud risk domains
- ✅ **5-Point Maturity Scale** (Emerging → Leading)
- ✅ **Real-Time Scoring** with visual results dashboard
- ✅ **Interactive Chart** using Chart.js
- ✅ **PDF Export** for sharing and documentation
- ✅ **Auto-Save Progress** using browser localStorage
- ✅ **Responsive Design** works on desktop, tablet, and mobile
- ✅ **No Backend Required** - pure HTML/CSS/JavaScript

### User Experience
- 📊 Visual progress bar
- 🎨 Clean, professional design
- ⚡ Fast and lightweight (~100KB)
- 🔄 Back/Forward navigation
- 💾 Automatic progress saving
- 🖨️ Print-friendly results page

### Technical Features
- 🚀 Zero dependencies (uses CDN for Chart.js and jsPDF)
- 🔒 Privacy-focused (all data stays in browser)
- ♿ Accessible design
- 📱 Mobile-optimized
- 🎯 Easy to customize

---

## 📁 Project Files

```
PJRFun/
├── fraud-assessment-tool.html          # Main assessment tool (complete, ready to use)
├── README.md                            # This file - project overview
├── WORDPRESS-SETUP.md                   # WordPress embedding instructions
├── CONTENT-STRUCTURE-TEMPLATE.md        # Guide for customizing questions/domains
├── WIREFRAME-FLOW.md                    # Visual user flow documentation
└── LICENSE                              # License information (if applicable)
```

---

## 🚀 Quick Start

### Option 1: Open Directly (Fastest)
1. Open `fraud-assessment-tool.html` in any modern web browser
2. That's it! The tool is fully functional

### Option 2: Host on Web Server
1. Upload `fraud-assessment-tool.html` to your web server
2. Access via URL (e.g., `https://yourdomain.com/fraud-assessment-tool.html`)

### Option 3: Embed in WordPress
Follow instructions in **WORDPRESS-SETUP.md** (takes ~2 minutes)

---

## 🎨 Customization

### Change Branding Colors

Edit the CSS variables at the top of the file:

```css
:root {
  --pia-teal: #00404a;        /* Primary color */
  --pia-teal-light: #0f9c91;  /* Secondary color */
  --pia-orange: #e84e0f;      /* Accent color */
}
```

### Add Your Own Questions

See **CONTENT-STRUCTURE-TEMPLATE.md** for complete instructions on:
- Adding new domains
- Modifying questions
- Customizing maturity levels
- Writing domain-specific recommendations

### Modify Assessment Text

All text is in plain HTML. Simply search and replace:
- **Title:** Find `<h1 class="fp-title">`
- **Questions:** Find `<div class="fp-question-text">`
- **Domain names:** Find `data-domain="`

---

## 📊 How It Works

### User Flow

```
1. Introduction Page
   ↓
2. Domain 1 (3 questions)
   ↓
3. Domain 2 (3 questions)
   ↓
4. Domain 3 (3 questions)
   ↓
5. Domain 4 (3 questions)
   ↓
6. Domain 5 (3 questions)
   ↓
7. Results Page
   - Overall score & maturity level
   - Domain breakdown with chart
   - Recommendations by domain
   - PDF download option
```

### Scoring Logic

Each question uses a 1-5 scale:
1. Not in place (20%)
2. Basic (40%)
3. Developing (60%)
4. Good (80%)
5. Fully in place (100%)

**Domain Score** = Average of questions in that domain
**Overall Score** = Average of all 15 questions

**Maturity Levels:**
- **Emerging** (0-29%): Basic, ad hoc practices
- **Developing** (30-59%): Building blocks in place, uneven
- **Established** (60-79%): Systematic, regular practice
- **Leading** (80-100%): Data-informed, innovative

---

## 🔧 Technical Details

### Technologies Used
- **HTML5** for structure
- **CSS3** for styling (with CSS variables for easy theming)
- **Vanilla JavaScript** for logic (no frameworks)
- **Chart.js 4.4** for visualizations
- **jsPDF 2.5** for PDF generation
- **localStorage API** for progress saving

### Browser Compatibility
- ✅ Chrome 90+
- ✅ Firefox 88+
- ✅ Safari 14+
- ✅ Edge 90+
- ✅ Mobile browsers (iOS Safari, Chrome Mobile)

### Performance
- **Page Load:** < 1 second (with CDN)
- **File Size:** ~75KB HTML + ~200KB libraries (loaded from CDN)
- **No Server Required:** Runs entirely in the browser

---

## 💾 Data Storage & Privacy

### How Data is Stored
- All responses are saved in **browser localStorage**
- No data is sent to any server
- No cookies, no tracking, no external data collection

### Data Persistence
- Responses persist across browser sessions
- Clearing browser data will erase saved progress
- "Start New Assessment" button clears all data

### PDF Export
- Generated entirely in the browser
- No data sent to external services
- Download happens locally

---

## 📋 Use Cases

### For Organizations
- **Annual fraud risk maturity assessments**
- **Gap analysis and improvement planning**
- **Board/leadership reporting**
- **Compliance documentation**
- **Internal audit preparation**

### For Consultants
- **Client initial diagnostics**
- **Engagement scoping**
- **Before/after improvement measurement**
- **Benchmarking across clients**

### For Training & Education
- **Workshop exercises**
- **Self-paced learning**
- **Case study discussions**
- **Certification programs**

---

## 🎯 Customization Examples

### Example 1: Payment Fraud Focus

Replace domains with:
1. Payment Authorization
2. Vendor Verification
3. Transaction Monitoring
4. Data Quality
5. Investigation & Response

See **CONTENT-STRUCTURE-TEMPLATE.md** for complete example.

### Example 2: Healthcare Fraud

Customize for healthcare with domains like:
1. Claims Validation
2. Provider Enrollment
3. Utilization Review
4. Medical Necessity Controls
5. Recovery Operations

### Example 3: Grant Fraud

Adapt for grant management:
1. Application Screening
2. Award Authorization
3. Expenditure Verification
4. Progress Monitoring
5. Close-Out Review

---

## 🔐 Security Considerations

### What This Tool DOES
- ✅ Runs entirely in the browser (no server-side code)
- ✅ Stores data locally (no transmission)
- ✅ Loads libraries from reputable CDNs

### What This Tool DOES NOT
- ❌ Send any data to external servers
- ❌ Use cookies or tracking
- ❌ Collect personally identifiable information
- ❌ Require user accounts or authentication

### For Production Use
- Consider hosting libraries locally instead of using CDN
- Add Content Security Policy headers
- Use HTTPS for hosting
- Review and customize based on your security requirements

---

## 📦 WordPress Integration

This tool can be embedded in WordPress in multiple ways:

1. **Direct HTML** (recommended) - paste entire HTML into page
2. **iFrame embed** - host separately and embed
3. **Plugin/shortcode** - use a code snippet plugin

See **WORDPRESS-SETUP.md** for step-by-step instructions.

---

## 🤝 Contributing & Customization

This tool is designed to be easily customizable. You can:

- Modify questions and domains
- Change scoring logic
- Add new maturity levels
- Customize visual design
- Add additional analytics
- Integrate with backend systems

See **CONTENT-STRUCTURE-TEMPLATE.md** for detailed guidance.

---

## 📝 License

[Specify your license here - e.g., MIT, Creative Commons, etc.]

---

## 🆘 Support & Troubleshooting

### Common Issues

**Problem:** PDF download doesn't work
- Check that jsPDF library is loading from CDN
- Try a different browser
- Check browser console for errors

**Problem:** Responses aren't saving
- Ensure localStorage is enabled in browser
- Check if you're in private/incognito mode (localStorage may be restricted)
- Verify no browser extensions are blocking localStorage

**Problem:** Chart doesn't display
- Confirm Chart.js library is loading from CDN
- Check browser console for errors
- Ensure you have an internet connection (for CDN)

**Problem:** Styling looks broken
- Verify the entire `<style>` section is included
- Check for CSS conflicts if embedded in WordPress
- Try using iframe method instead

### Getting Help

1. Check **WORDPRESS-SETUP.md** for embedding issues
2. Check **CONTENT-STRUCTURE-TEMPLATE.md** for customization questions
3. Review browser console (F12) for JavaScript errors
4. Test in a different browser to isolate issues

---

## 🎓 Methodological Notes

This assessment is based on fraud risk management best practices from:

- **COSO Fraud Risk Management Guide**
- **Association of Certified Fraud Examiners (ACFE)** frameworks
- **UK National Audit Office** fraud standards
- **GAO Fraud Risk Framework** (US Government Accountability Office)
- **ISO 37001** Anti-Bribery Management Systems

The maturity model follows a capability maturity approach:
- Focus on **prevention** not just detection
- Emphasize **systematic practices** over ad hoc responses
- Value **data-informed decision making**
- Recognize **continuous improvement**

---

## 📊 Sample Results Output

After completing the assessment, users receive:

### Overall Score
- Numeric score (0-100)
- Maturity level badge (Emerging/Developing/Established/Leading)
- Brief interpretation

### Domain Breakdown
- Individual score for each of 5 domains
- Visual bar chart
- Domain-specific maturity level
- Tailored recommendations for improvement

### Export Options
- PDF download (includes all scores and recommendations)
- Browser print (formatted for printing)
- Future: CSV export, email delivery, etc.

---

## 🗺️ Roadmap & Future Enhancements

Possible additions (not yet implemented):

- [ ] Multiple language support
- [ ] Comparison to sector benchmarks
- [ ] Historical tracking (multiple assessments over time)
- [ ] Team/multi-user assessments
- [ ] Integration with survey platforms (Qualtrics, SurveyMonkey)
- [ ] Email delivery of results
- [ ] Backend database integration
- [ ] API for programmatic access
- [ ] Pre-built integration with GRC platforms

---

## 📞 Contact & Credits

**Developed by:** [Your Name/Organization]
**Contact:** [Your Email]
**Website:** [Your Website]

**Technology Credits:**
- Chart.js - https://www.chartjs.org/
- jsPDF - https://github.com/parallax/jsPDF

---

## 🎉 Quick Start Checklist

- [ ] Open `fraud-assessment-tool.html` in browser
- [ ] Complete a test assessment
- [ ] Review results page and PDF download
- [ ] Customize colors in CSS (optional)
- [ ] Customize questions/domains (optional)
- [ ] Test on mobile device
- [ ] Deploy to web server or WordPress
- [ ] Share with users!

---

**Ready to assess your fraud prevention capability? Open fraud-assessment-tool.html and get started!**
