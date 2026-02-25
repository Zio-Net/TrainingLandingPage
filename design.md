# Design Document: ZioNet Free Training Program Landing Page

## 1. Visual Design Language (VDL)
This page is an extension of `www.zion-net.co.il`.

### Color Palette
*   **Primary (Backgrounds/Headers):** `Deep Tech Blue (#003366)`
*   **Accent (CTAs/Icons/Checkmarks):** `Innovation Cyan (#00AEEF)`
*   **Secondary Background:** `Light Gray (#F5F5F5)`
*   **Text (Body):** `Dark Slate (#1A1A1A)`
*   **Text (On Dark/Hero):** `White (#FFFFFF)`

### Typography
*   **Headings:** `Montserrat` (Bold / 700)
    *   Used for clear, impactful section titles.
*   **Body:** `Segoe UI` (Regular / 400)
    *   Used for high readability.

### Visual Tone
Professional, growth-oriented, tech-forward (AI/Cloud focus), and human-centric.

---

## 2. Layout & Component Design

### Section A: Hero (Above the Fold)
*   **Layout:** Full-width background image (suggested: diverse young developers).
*   **Style:** Dark blue gradient overlay `rgba(0, 51, 102, 0.8)` for text contrast.
*   **Elements:** H1 Headline, H2 Sub-headline, Primary CTA Button (White Text, High Contrast).

### Section B: Value Proposition ("The Hook")
*   **Layout:** Two-column (Desktop); stacked on mobile.
    *   *Left:* Full intro paragraph explaining the training as a screening process.
    *   *Right:* Benefits checklist under heading "What You Will Gain from Our Training Program".
*   **Placement:** Incorporated near the top of the page, directly after the Hero.
*   **Component Detail:** The benefits list must be presented with checkmarks.
    *   **Icon:** Checkmarks must be **Innovation Cyan (#00AEEF)**.
    *   Highlight key tech terms (AI Agentic System Development, React, C#/NodeJS, DevOps) with bold or accent color.

### Section C: Target Audience ("Who Can Apply")
*   **Background:** White (`#FFFFFF`).
*   **Component:** 3-Card Grid (Academic, Language, Mindset) + a 4th availability item.
    *   **Style:** Each card highlights a specific requirement with a subtle icon (Graduation Cap, Globe, Rocket).
    *   **Academic Card:** Includes asterisk footnote for non-degree candidates.
    *   **Language Card:** Emphasizes training is held in English.
    *   **Mindset Card:** Commitment to learning and passion for tech.
*   **Availability + Open Day CTA:** Distinct banner or bold text stating availability from **June 2026**, with a link/button: "Register for our online Open Day".

### Section D: Process Diagram (Timeline)
*   **Background:** Light Gray (`#F5F5F5`).
*   **Layout:**
    *   *Desktop:* Horizontal timeline connecting 4 nodes.
    *   *Mobile:* Vertical timeline.
*   **Nodes:** Step 0 through Step 3, each with a title badge and bullet-point details.
    *   Step 0: "Open Day & Screening Task" (April-May 2026)
    *   Step 1: "Screening Course" (6-9 sessions, 1 month)
    *   Step 2: "Theoretical and Hands-on Training" (~4 months, flexible)
    *   Step 3: "Employment Opportunity"
*   **Styling:**
    *   Container: Flexbox, `flex-direction: column` on mobile via media query.
    *   Steps: Card-like styling with Deep Tech Blue step-number badges.
    *   Connecting line between nodes (border or pseudo-element).

### Section E: Social Proof (Testimonials)
*   **Heading:** "ZioNet Training Program graduates share their story"
*   **Component:** Carousel or Grid (~3 quote cards).
*   **Card Style:**
    *   Circular Avatar photo.
    *   Short quote text (italicized or in quotation marks).
    *   Metadata: Name, Current Role, Degree, Academic Institution (smaller/lighter text).

### Section F: About ZioNet
*   **Background:** Deep Tech Blue (`#003366`) or White with blue accent border.
*   **Content:** Full company description (3 paragraphs covering solutions, partnerships, and leadership).
*   **CTA:** Link to company landing page.

### Section G: Registration Form (Conversion)
*   **Background:** White or very light blue brand tint.
*   **Heading:** "Would you like us to contact you about the training program? Register here"
*   **Display:** Fields rendered directly on the page (not behind a link or popup).
*   **Layout:**
    *   *Mobile:* Single column.
    *   *Desktop:* Dual column for short fields (Name/Email side-by-side).
*   **Elements:**
    *   Standard Inputs: First Name, Last Name, Email Address, Phone Number.
    *   Text Input: Relevant Academic Degree or Relevant Work Experience.
    *   Text Input: LinkedIn Profile.
    *   **File Upload:** Dashed border "drop-zone" style for CV/Resume.
    *   **Button:** Full-width `Btn-Primary` (Cyan background), Label "Register Now".

### Section H: Footer / Additional Information
*   Link to company "About Us" page.
*   Contact email for questions.
*   Minimal styling, consistent with ZioNet branding.

---

## 3. CSS Implementation Strategy

### Typography Utility Classes
*   `.font-heading` -> `Montserrat`
*   `.font-body` -> `Segoe UI`

### Timeline Component
```css
.timeline-container {
  display: flex;
  justify-content: space-between;
  padding: 40px 0;
  position: relative;
  /* Add media query for flex-direction: column on mobile */
}

.timeline-step {
  flex: 1;
  text-align: center;
  padding: 20px;
  background: var(--color-white);
  border: 1px solid var(--color-border);
  border-radius: var(--border-radius-card);
  margin: 0 10px;
}
```

### Benefit List Component
```css
.benefit-list li {
  position: relative;
  padding-left: 30px;
  margin-bottom: 15px;
}
.benefit-list li::before {
  content: '✓';
  position: absolute;
  left: 0;
  color: #00AEEF; /* Innovation Cyan */
}
```
