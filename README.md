# FAFSA Corrections Troubleshooting Flowchart

An interactive educational tool designed to help students identify and resolve FAFSA correction issues through a step-by-step guided troubleshooting process with personalized feedback and actionable solutions.

## 📋 Overview

This project is an interactive web application that guides students through a systematic troubleshooting process to identify what type of FAFSA correction they need to make. Using a flowchart-style decision tree, students answer simple yes/no questions about their FAFSA issues and receive specific, actionable guidance on how to fix them.

### Try it out

[Try FASFA Troubleshooting Flowchart (Online Link)](https://thiinkmg.github.io/FASFA-Troubleshooting-Flowchart/)

---

## ✨ Features

- **Interactive Flowchart Navigation**: Step-by-step guided troubleshooting through decision nodes
- **Personalized Correction Guidance**: Specific instructions for each type of FAFSA issue
- **Smart Button States**: Visual feedback showing selected answers throughout the process
- **Readiness Score System**: Comprehensive scoring based on FAFSA completion status
- **Detailed Review Section**: Complete breakdown of all answers and recommendations
- **Saved Results Functionality**: Resume where you left off with automatic progress saving
- **Dual PDF Export Options**:
  - **jsPDF Download**: Personalized results report with readiness score
  - **Browser Print**: Complete troubleshooting guide with all steps
- **Dark/Light Mode**: Toggle between themes for comfortable viewing
- **Keyboard Navigation**: Quick answers with Y/N keyboard shortcuts
- **Smart Sticky Header**: Auto-hide on scroll for better content visibility
- **Responsive Design**: Optimized for desktop, tablet, and mobile devices
- **Accessibility Features**: ARIA labels, focus indicators, and skip links

## 🎯 Educational Value

The troubleshooting flowchart covers essential FAFSA correction scenarios including:
- Personal information errors (name, birthdate, SSN)
- Financial and tax data corrections
- Missing or incorrect signatures
- School code and college list updates
- Household size and dependent changes
- Submission status and confirmation tracking

## 🚀 Getting Started

### Prerequisites
- A modern web browser (Chrome, Firefox, Safari, Edge)
- No additional software installation required

### Installation
1. Clone or download this repository
2. Open `index.html` in your web browser
3. Start troubleshooting your FAFSA issues immediately!

### Usage
1. **Start the Flowchart**: Click "Start FAFSA Troubleshooting" to begin
2. **Answer Questions**: Select Yes or No for each FAFSA issue presented
3. **Follow Guidance**: Read the correction instructions for issues you identified
4. **Review Results**: View your complete answers and readiness score
5. **Export Results**: Download your troubleshooting report as a PDF

## 🛠️ Technical Details

### Built With
- **HTML5**: Semantic markup and accessibility features
- **CSS3**: Modern styling with CSS Grid, Flexbox, and custom properties
- **Vanilla JavaScript**: No frameworks required - pure ES6+
- **jsPDF**: Client-side PDF generation for results export
- **Local Storage**: Automatic progress and results saving
- **Print CSS**: Optimized print stylesheets for browser PDF export

### Browser Compatibility
- Chrome 60+
- Firefox 55+
- Safari 12+
- Edge 79+

## 📱 Responsive Design

The application is fully responsive and optimized for:
- **Desktop**: Full feature experience with hover effects (80px header)
- **Tablet**: Touch-friendly interface with enhanced touch targets (76px header, 52px buttons)
- **Mobile**: Streamlined single-column layout (64px header, full-width buttons)

### Breakpoints
- **XS (≤375px)**: Very small phones - minimal padding, tighter spacing
- **SM (≤576px)**: Small phones - compact layouts
- **MD (≤768px)**: Tablets and large phones - mobile optimizations
- **LG (768px-1024px)**: Tablets - enhanced touch targets and spacing

## 🎨 Customization

The application uses CSS custom properties (variables) for easy theming:

### MCF Brand Colors
```css
--mcf-primary-color: #012699;    /* Brand blue */
--mcf-secondary-color: #26e011;  /* Brand green */
--mcf-accent-color: #fdc003;     /* Brand amber */
```

### Touch Targets
```css
--touch-target-min: 44px;        /* WCAG minimum */
--touch-target-recommended: 48px; /* Material Design */
```

### Typography Scale
- Base font: 16px mobile → 18px desktop
- Fluid scaling using `clamp()` for headings
- Line heights: 1.2 (tight), 1.5 (normal), 1.7 (relaxed)

## 📊 Flowchart Data Structure

The flowchart follows a decision tree structure with state management:

```javascript
flowchartState = {
  currentStep: string,      // Current active step ID
  history: array,           // Navigation history
  userAnswers: object       // User selections { step: 'yes'|'no' }
}

flowMap = {
  'personal-yes': 'personal-action',
  'personal-no': 'financial',
  // ... decision paths
}
```

## 🔧 Development

### Local Development
1. Clone the repository
2. Open `index.html` in your browser
3. Make changes to the code
4. Refresh the browser to see changes (page auto-reloads after print)

### Adding New Troubleshooting Steps
To add new flowchart steps:
1. Add a new `.flowchart-step` div in the HTML
2. Update the `flowMap` object with decision paths
3. Add question data to `questionData` object for results display
4. The application will automatically include the new step

### Modifying Readiness Score Logic
The readiness score calculation is in `updateReadinessScore()`:
- "No" answers = No problems = Higher score (18-25 points)
- "Yes" answers = Has problems = Lower score (8-12 points)
- Weighted scoring by category importance

## 📄 PDF Export Features

The application includes two distinct PDF export methods:

### 1. jsPDF Results Report
- **Trigger**: "Download PDF" button in results section
- **Content**: Personalized readiness score report
- **Features**:
  - Your Readiness Score with percentage
  - Complete answers review with feedback
  - Personalized recommendations
  - MCF branding and footer
  - Multi-page support with page numbers
- **Emoji Handling**: Comprehensive Unicode emoji removal using regex
- **Filename**: `FAFSA-Corrections-Report.pdf`

### 2. Browser Print/PDF
- **Trigger**: Browser's print function (Ctrl+P / Cmd+P)
- **Content**: Complete troubleshooting flowchart guide
- **Features**:
  - All flowchart steps shown sequentially
  - Step numbers for clarity
  - Print-only header with generation date
  - Optimized typography (10pt body, clean layout)
  - No interactive elements (buttons hidden)
- **Emoji Handling**: TreeWalker-based emoji removal from all text nodes
- **Auto-reload**: Page reloads after printing to restore original content

### Emoji Removal System
Both PDF methods use comprehensive Unicode regex to remove:
- Basic emojis (😀-🙏)
- Symbols & Pictographs (🌀-🗿, 🚀-🛿)
- Compound emojis with Zero-Width Joiners (👨‍👩‍👧‍👦)
- Variation selectors, flags, dingbats
- 30+ Unicode emoji ranges for clean PDF output

## 🎓 Educational Use Cases

Perfect for:
- **High School Students**: First-time FAFSA applicants encountering issues
- **College Students**: Fixing FAFSA errors before deadlines
- **Transfer Students**: Updating FAFSA information for new schools
- **Parents**: Understanding how to help students fix FAFSA mistakes
- **Financial Aid Counselors**: Educational tool for troubleshooting workshops
- **Community Organizations**: Financial literacy programs and FAFSA assistance events
- **High School Counselors**: Helping students resolve FAFSA submission issues

## 🎯 FAFSA Issue Categories Covered

### Personal Information Errors
- Name corrections (must match SSN records)
- Birthdate corrections
- Social Security Number corrections
- **Solution**: Log into StudentAid.gov → Make FAFSA Corrections

### Financial/Tax Data Errors
- Income corrections
- AGI (Adjusted Gross Income) errors
- Tax filing status mistakes
- **Solution**: Use IRS Data Retrieval Tool or manual corrections

### Signature Issues
- Missing student signature
- Missing parent signature (dependent students)
- **Solution**: Electronic signing via FSA ID on StudentAid.gov

### School List Updates
- Adding new schools
- Removing schools
- Changing school order
- **Solution**: Up to 20 schools can be listed

### Household Changes
- Family size changes
- Marital status updates
- Dependent changes
- Asset reporting corrections
- **Solution**: Update Student Demographics section

### Status Tracking
- Confirmation email timing (24-48 hours)
- Processing time (3-5 business days)
- School notification process
- Financial aid package updates

## 🏆 Readiness Score System

### Score Calculation
The readiness score is calculated based on weighted responses:
- **Personal Info**: 20% weight (20 points max)
- **Financial Info**: 25% weight (25 points max)
- **Signature**: 15% weight (15 points max)
- **School List**: 20% weight (20 points max)
- **Household Info**: 20% weight (20 points max)

### Score Interpretation
- **90-100%**: 🎉 Excellent - Fully prepared, no corrections needed
- **75-89%**: ✅ Good - Well-prepared with minor areas to address
- **60-74%**: ⚙️ Fair - Making progress with some important areas to complete
- **Below 60%**: 📚 Needs Work - Focus on completing essential steps

### Scoring Logic
- **"No" answers** = No problems detected = **Higher score**
- **"Yes" answers** = Problems to fix = **Lower score**

## 🔧 Advanced Features

### Smart Sticky Header
- Hides on scroll down to maximize content visibility
- Shows on scroll up for easy access to theme toggle
- Fixed 80px height on desktop, 64px on mobile
- Smooth transitions with backdrop blur effect

### Saved Results System
- **Auto-save on completion**: Results saved to localStorage
- **Welcome Back Screen**: Shown on return visits with completion date
- **Quick Actions**: View results, download PDF, or start new flowchart
- **Data persistence**: Maintains readiness score and all answers
- **Warning prompts**: Alerts before clearing saved results

### Button State Management
- **Default state**: White/neutral appearance
- **Hover state**: Green preview (both buttons)
- **Selected state**: Green background with scale effect
- **Unselected state**: Faded appearance (non-selected option)
- **Visual feedback**: 300ms transition animations

### Keyboard Navigation
- **Y key**: Select "Yes" answer
- **N key**: Select "No" answer
- **Enter**: Activate focused button
- **Tab**: Navigate between interactive elements
- **Skip link**: Jump to main content (keyboard users)

### Accessibility Features
- ARIA labels on all interactive elements
- Focus indicators with 3px outlines
- Sufficient color contrast (WCAG AA compliant)
- Semantic HTML structure
- Screen reader-friendly text alternatives
- Touch target minimums (44-48px)

### Dark Mode Support
- Automatic theme persistence via localStorage
- Adjusted brand colors for dark backgrounds
- Inverted text and border colors
- Smooth theme transitions (0.3s)
- Print-friendly (forces light mode)

## 📊 Question Data Structure

Each troubleshooting question includes:

```javascript
questionData = {
  'step-id': {
    icon: 'emoji',
    question: 'Section Title',
    description: 'Question text',
    feedback: {
      yes: 'Feedback for Yes answer',
      no: 'Feedback for No answer'
    }
  }
}
```

## 🔍 Technical Implementation Highlights

### State Management
- Pure JavaScript state object (`flowchartState`)
- Decision tree navigation via `flowMap` object
- localStorage persistence for saved results

### CSS Architecture
- Mobile-first approach with progressive enhancement
- CSS custom properties for theming
- Responsive breakpoints with content-specific queries
- Print-specific stylesheet with optimizations

### JavaScript Patterns
- Event delegation for dynamic button handling
- TreeWalker for comprehensive text node manipulation
- Async/await for PDF generation
- beforeprint/afterprint handlers for print optimizations

### Performance Optimizations
- Reduced animations on mobile (`prefers-reduced-motion`)
- Passive scroll listeners
- Debounced auto-save operations
- Efficient emoji removal algorithms

## 🤝 Contributing

We welcome contributions to improve this educational tool:
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Make your improvements
4. Test on multiple devices and browsers
5. Submit a pull request

### Development Guidelines
- Follow existing code style and conventions
- Test all interactive features
- Verify PDF exports (both methods)
- Check responsive layouts on all breakpoints
- Ensure accessibility compliance

## 📞 Support

For questions or support, please contact:
- [**My College Finance Technical Feedback Form**](https://docs.google.com/forms/d/e/1FAIpQLScyBwnqiz1L3ZOxV3C4f40jsOAW-YCw8xxfoBhPg2mgORshFA/viewform)

## 📜 License

© 2025 My College Finance. All rights reserved.

## 🙏 Acknowledgments

**Created by**: [Thiink Media Graphics](https://www.thiinkmediagraphics.com/)
**In partnership with**: [My College Finance](https://www.mycollegefinance.com/)

## 🔗 Related Resources

- [FAFSA Interactive Research Web Report](https://my-college-finance.github.io/FAFSA-Interactive-Research-Web-Report/)
- [My College Finance Main Website](https://www.mycollegefinance.com/)
- [FAFSA Official Website](https://studentaid.gov/h/apply-for-aid/fafsa)
- [StudentAid.gov - Make FAFSA Corrections](https://studentaid.gov/apply-for-aid/fafsa/review-and-correct)

## 🐛 Known Issues & Resolutions

### Resolved Issues
- ✅ **Emoji rendering in PDFs**: Fixed with comprehensive Unicode removal
- ✅ **Inverted readiness score logic**: Corrected scoring ("No" = higher score)
- ✅ **Blocking results banner**: Removed sticky banner, kept welcome screen
- ✅ **Button state persistence**: Fixed selected/unselected visual feedback
- ✅ **Mobile spacing issues**: Optimized padding and margins for small screens

### Browser-Specific Notes
- Safari: Requires user interaction before localStorage access
- Chrome/Edge: PDF print may show security dialog (expected behavior)
- Firefox: Print preview may take longer with emoji removal

---

*This educational tool is designed to help students identify and resolve FAFSA correction issues. Always verify correction requirements with StudentAid.gov and consult with financial aid professionals for personalized assistance. FAFSA processing times and deadlines may vary by institution and state.*
