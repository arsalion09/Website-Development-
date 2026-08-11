# Website Generation Engineering Standard (WGES) v5.0

**A Comprehensive Engineering Handbook for Automated, Enterprise-Grade Website Production**

This document represents the evolution of the Master AI Website Generation Specification (MAWGS) into a formal **Website Generation Engineering Standard (WGES) v5.0**. It defines a robust, multi-agent system designed for the automated production of premium, marketplace-ready WordPress theme packages. WGES v5.0 emphasizes measurable design fidelity through objective metrics, formalized inter-agent contracts, a centralized design knowledge base, comprehensive versioning, advanced testing methodologies including regression analysis, platform-specific marketplace compliance, a detailed error taxonomy, and an extensible plugin architecture. A foundational set of Operating Principles guides every decision and action within the system.

---

## 1. Operating Principles

These principles serve as the guiding doctrine for every agent and every phase of the WGES. They define the philosophy behind our automated website production pipeline:

*   **Preserve Design Language, Not Copyrighted Assets:** The AI must meticulously replicate the aesthetic and functional intent of the inspiration, abstracting its core design language while avoiding direct reproduction of proprietary assets.
*   **Prioritize Maintainability Over Cleverness:** Solutions must be elegant, readable, and easily modifiable by human developers or future AI iterations, eschewing overly complex or obscure implementations.
*   **Prefer Native Platform Capabilities Over Custom Code:** Leverage the inherent strengths and features of WordPress and Elementor wherever possible to ensure stability, compatibility, and ease of updates.
*   **Optimize for Long-Term Editing by Non-Developers:** The generated output must be intuitive and user-friendly for clients or less technical users to manage and update content without requiring specialized coding knowledge.
*   **Ensure Functional and Visual Consistency:** Maintain seamless fidelity across HTML, Elementor, and WordPress implementations, guaranteeing a unified user experience regardless of the underlying technology layer.
*   **Build Reusable Systems, Not One-Off Solutions:** Focus on creating modular, scalable components and patterns that can be efficiently adapted and reused across multiple projects.
*   **Commercial Distribution Readiness:** Every deliverable must be structured and prepared for commercial distribution, adhering to all necessary licensing, documentation, and marketplace requirements.

---

## 2. Overall AI System Architecture & Inter-Phase Memory

WGES v5.0 implements a sophisticated **Multi-Agent Architecture** for enterprise-grade reliability and modularity. Each phase is managed by specialized agents with clearly defined **Agent Contracts** (see Section 2.1), specifying their inputs, outputs, required artifacts, validation rules, failure conditions, and handoff requirements. A robust **AI Memory** mechanism ensures seamless knowledge transfer and consistency across phases, preventing redundant work and maintaining alignment with core project definitions. This memory includes:

*   **Design Tokens (Versioned):** The single source of truth for all stylistic values, with explicit versioning for traceability.
*   **Component & Design Pattern Library:** Reusable UI patterns, layout archetypes, and their specifications.
*   **Business Context & Industry Knowledge Modules:** The emotional tone, brand personality, target audience, conversion strategy, and industry-specific best practices.
*   **Motion Design System:** Defined animation tokens, timing, and easing.
*   **Naming Conventions:** Consistent BEM-compatible naming across all codebases.
*   **AI Decision Trees:** Rules and logic guiding agent behavior based on detected patterns and context.
*   **Prompt Versioning:** Tracking of all prompts and their versions for reproducibility.

### 2.1. Agent Contracts

Formalized interfaces between agents define clear responsibilities and ensure predictable workflow. For each agent, the following must be explicitly defined:

*   **Inputs:** Data, artifacts, and context received from preceding agents.
*   **Outputs:** Deliverables, reports, and transformed data passed to subsequent agents.
*   **Required Artifacts:** Specific files, JSON structures, or code segments that must be produced.
*   **Validation Rules:** Criteria for assessing the correctness and quality of outputs.
*   **Failure Conditions:** Defined scenarios under which an agent cannot complete its task.
*   **Handoff Requirements:** Protocols for transferring control and data to the next agent in the pipeline.

### 2.2. Design Knowledge Base

A centralized, versioned **Design Knowledge Base** serves as the single source of truth for all agents, preventing duplication and ensuring alignment across every phase. This knowledge base includes:

*   **Design Tokens:** All versioned stylistic values.
*   **Component Definitions:** Detailed specifications for all UI components.
*   **Layout Archetypes:** Reusable structural patterns.
*   **Industry Patterns:** Best practices and common elements for specific business types.
*   **Accessibility Rules:** Comprehensive WCAG 2.1 AA compliance guidelines.
*   **Motion System:** All defined animation parameters.
*   **Marketplace Standards:** Requirements and guidelines for various distribution platforms.

---

## 3. Phase 1: AI Reasoning & Planning Pipeline (The "Thinking" Phase)

Before any code generation, the AI agent system executes a multi-step analytical pipeline to establish the project's foundation. This phase is primarily driven by the **Design Analysis Agent**, **Design System Agent**, and **UX/CRO Agent**.

### 3.1. Visual Reverse Engineering & Design Psychology (Design Analysis Agent)

Analyze the inspiration image to extract the "Soul" of the design, with a strong emphasis on **measurable design fidelity**. The agent must preserve and quantify, and report against the **Design Fidelity Scorecard** (see Section 8.1):

*   **Emotional Tone & Brand Personality:** (e.g., Minimalist Luxury, Energetic Tech, Trustworthy Medical).
*   **Target Audience & Conversion Strategy:** Identify who the site is for and the primary actions they should take.
*   **CTA Hierarchy:** Map the primary, secondary, and tertiary call-to-action buttons.
*   **Visual Proportions & Spacing Ratios:** Quantify the relative sizes and distances between elements.
*   **Typography Hierarchy:** Analyze font sizes, weights, and line heights across headings and body text.
*   **Shadow Intensity & Border Radius Scale:** Extract and define the precise characteristics of shadows and corner rounding.
*   **Composition & Alignment:** Document the layout structure and alignment rules.
*   **Image Treatment:** Identify specific filters, overlays, or cropping styles applied to images.
*   **Animation Personality:** Characterize the overall feel and intent of any detected motion.
*   **Premium Cues:** Identify glassmorphism, subtle gradients, parallax, or high-end typography treatments.

### 3.2. Comprehensive Design System Architecture (Design System Agent)

Generate a centralized `tokens.json` (or individual JSON files) and a **Component & Design Pattern Library** that all subsequent outputs (HTML, CSS, Elementor, WordPress) must consume. This extends beyond basic tokens to define reusable UI patterns and layout archetypes.

*   **Versioned Design Tokens:**
    *   `colors.json`: Primary, accent, neutral, semantic (success/error), and surface colors.
    *   `typography.json`: Font families, fluid sizing scales, line heights, and weights.
    *   `spacing.json`: Margin/padding scales based on a consistent base unit (e.g., 4px or 8px).
    *   `radius.json` & `shadows.json`: Consistent corner rounding and elevation levels.
    *   `animations.json` (Motion Design System): Define animation tokens, timing scales, easing curves, hover language, page transitions, scroll behavior, and reduced-motion fallback strategies.
    *   Each token set must be explicitly versioned (e.g., `Design System v1.0`, `Component Library v1.0`, `Motion System v1.0`) for traceability and update management.
*   **Component Specifications:** Detailed definitions for common UI components, including:
    *   **Buttons:** Variants (primary, secondary, ghost), states (hover, active, disabled), sizing, iconography.
    *   **Cards:** Layouts, content areas, image ratios, interactive elements.
    *   **Navigation:** Desktop, mobile (hamburger), dropdowns, active states.
    *   **Hero Sections:** Layouts, content structure, background treatments, CTA placement.
    *   **Testimonials:** Card styles, author attribution, rating systems.
    *   **Pricing Tables:** Tier structures, feature lists, call-to-action emphasis.
    *   Each component specification must include its variants, spacing rules, interaction patterns, responsive behavior, and accessibility requirements.
*   **Design Pattern Library:** Reusable layout archetypes and section blueprints to guide structural generation:
    *   **Hero Patterns:** SaaS Hero, Agency Hero, Restaurant Hero, Portfolio Hero, Medical Hero, E-commerce Hero.
    *   **Section Blueprints:** Split layout, zig-zag sections, feature grids, pricing comparisons, testimonial layouts.

### 3.3. Structural Planning & AI Decision Trees (UX/CRO Agent)

*   **Information Architecture (IA):** Map the flow of sections and their logical hierarchy.
*   **UX Audit:** Ensure the planned layout follows standard usability patterns (F-pattern, Z-pattern) and best practices for conversion rate optimization (CRO).
*   **SEO Plan:** Identify heading structures (H1-H6), semantic tags, and keyword placement strategy, informed by target audience analysis.
*   **Accessibility Strategy:** Plan for WCAG 2.1 AA compliance (aria-labels, focus states, skip links, sufficient contrast ratios, keyboard navigability).
*   **AI Decision Trees:** Implement explicit rules to guide design and structural choices based on analysis. These decision trees are formalized and versioned within the Design Knowledge Base.
    *   **Example:** If inspiration contains asymmetric cards → use layout pattern A.
    *   **Example:** If business is medical → prioritize trust badges and appointment CTAs.
    *   **Example:** If SaaS → prioritize product screenshots, integrations, pricing, FAQs.

### 3.4. Industry Knowledge Modules

Formalized modules containing preferred sections, tone, conversion goals, and visual cues for specific industries. These modules inform the AI Decision Trees and content generation, and are stored in the Design Knowledge Base:

*   **SaaS:** Product screenshots, integration lists, pricing tables, FAQs, case studies.
*   **Agencies:** Portfolio, services, team, testimonials, contact forms.
*   **Restaurants:** Menu, reservations, location, gallery, events.
*   **Hotels:** Rooms, amenities, booking, gallery, reviews.
*   **Medical:** Services, doctors, appointments, patient forms, trust indicators.
*   **Legal:** Practice areas, attorneys, consultations, resources.
*   **Construction:** Projects, services, team, testimonials, contact.
*   **Travel:** Destinations, packages, booking, gallery, reviews.
*   **Education:** Courses, faculty, admissions, events, testimonials.
*   **Nonprofits:** Mission, programs, donate, impact, news.

---

## 4. Phase 2: Frontend Engineering (HTML, Tailwind, Vanilla JS) (Frontend Agent)

Build the "Static Reference" using the shared design tokens, component library, and design pattern library. This phase is executed by the **Frontend Agent**.

### 4.1. Component Intelligence & Classification

Every UI element must be classified before coding, adhering to the established Component & Design Pattern Library:

*   **Classification:** `[Component Name] -> [Layout Type] -> [Variants] -> [Responsive Rules] -> [Animation Rules]`.
*   **Reusability:** Code components as independent, reusable blocks, strictly following the component specifications.
*   **BEM-Compatible Naming:** Use a strict naming convention (e.g., `c-hero`, `c-hero__title`, `c-hero--large`) derived from the Design System.

### 4.2. Implementation Standards

*   **HTML5:** Semantic structure (header, main, section, article, footer) reflecting the IA and chosen design patterns.
*   **Tailwind CSS:** Utility-first styling informed by the versioned design tokens and component specifications.
*   **Vanilla JS:** Framework-free interactivity (scrollspy, smooth-scroll, mobile menu, parallax) adhering to the Motion Design System.
*   **Elementor Mapping Comments:** Wrap every structural block in comments for Phase 3:
    *   `<!-- EL:SECTION -->`, `<!-- EL:COLUMN -->`, `<!-- EL:INNER-SECTION -->`, `<!-- EL:WIDGET:WidgetName -->`.
*   **Asset Pipeline (Expanded):**
    *   **Responsive Image Generation:** Automatically generate and optimize images for various screen sizes.
    *   **Automatic WebP/AVIF Recommendations:** Implement modern image formats for performance.
    *   **Favicon Generation:** Create a complete set of favicons for all platforms.
    *   **Social Preview Image Specifications:** Generate `og:image` and Twitter card images.
    *   **Icon Sprite Optimization:** Consolidate and optimize icons for efficient loading.
    *   Use high-quality placeholders with credits.
    *   Implement WebP-ready structures and responsive `srcset` sizes.
    *   Include a "Replacement Guide" for the end user, detailing how to swap placeholders with final assets.

---

## 5. Phase 3: Native Elementor Architecture (Elementor Agent)

Translate the HTML reference into a functional Elementor ecosystem. This phase is executed by the **Elementor Agent**.

### 5.1. Template Generation & Ecosystem Integration

*   **Page Templates:** The complete layout as a `.json` import.
*   **Section Templates:** Individual sections exported for the Elementor Library.
*   **Reusable Templates:** Generate templates for frequently used blocks that can be inserted across multiple pages.
*   **Global Definitions:** Generate JSON for Global Colors and Global Typography matching the versioned design tokens.
*   **Global Widget Strategy:** Define and implement a strategy for using Elementor's global widgets to maintain consistency.
*   **Global Presets:** Create and apply global presets for widgets to ensure uniform styling.
*   **Native Widgets Only:** Zero use of the HTML widget for content. Use Heading, Text Editor, Button, Icon Box, etc., mapping directly to the Component Library.
*   **Import Order:** Specify the correct order for importing templates and global settings to ensure proper application.
*   **Version Compatibility:** Ensure generated Elementor assets are compatible with specified Elementor and WordPress versions.

### 5.2. Mapping & Styling

*   **Advanced CSS Classes:** Apply the BEM classes from Phase 2 to the `Advanced -> CSS Classes` field of every section, column, and widget.
*   **Zero Inline CSS:** All styling must be inherited from the external `custom.css` or global settings, adhering to the Design System.

---

## 6. Phase 4: Enterprise-Grade WordPress Theme Development (WordPress Agent)

Construct a modern, future-proof WordPress theme following `WP-Coding-Standards`. This phase is executed by the **WordPress Agent**.

### 6.1. Core Architecture & Extended Compatibility

*   **`theme.json`:** Implement the modern WordPress Global Styles and Settings system, consuming versioned design tokens.
*   **Template Parts & Patterns:** Break the theme into reusable parts (header, footer) and block patterns, aligning with the Component & Design Pattern Library.
*   **Theme Supports:** `add_theme_support()` for custom-logo, post-thumbnails, title-tag, HTML5, etc.
*   **Hooks & Filters:** Use standard WordPress hooks (`wp_head`, `wp_footer`) and custom filters for extensibility.
*   **Child-Theme Compatibility:** Ensure the theme is fully compatible with child themes, allowing for easy customization without modifying the parent theme.
*   **Multisite Compatibility:** Design and develop the theme to function correctly within a WordPress Multisite network.
*   **RTL (Right-to-Left) Support:** Implement proper styling and layout adjustments for RTL languages.
*   **Block Editor Compatibility:** Full support for the Gutenberg block editor, including custom block styles if necessary.
*   **REST API Compatibility:** Ensure the theme is compatible with the WordPress REST API for headless or decoupled architectures.
*   **XML Import/Export Guidance:** Provide clear instructions or mechanisms for importing and exporting content and settings.
*   **Plugin Conflict Considerations:** Develop with common plugin compatibility in mind, using best practices to avoid conflicts.

### 6.2. Security & Performance

*   **Sanitization & Escaping:** Use `esc_html()`, `esc_attr()`, `wp_kses()` for all dynamic output to prevent XSS and other vulnerabilities.
*   **Asset Management:** Enqueue scripts and styles with proper versioning and dependencies, optimizing for performance.
*   **PHP Standards:** Adhere to PHP 8.3+ and PSR-12 coding standards for maintainability and security.
*   **Translation Ready:** Full internationalization support using `__()` and `_e()` for all translatable strings.

---

## 7. Phase 5: Marketplace Production & Packaging (Marketplace Packaging Agent)

Transform the code into a retail-ready product for Gumroad, Etsy, or Envato. This phase is executed by the **Marketplace Packaging Agent**.

### 7.1. Product Asset Generation

*   **Documentation:** Comprehensive `README.md` and `Installation-Guide.pdf`.
*   **Marketing Assets:** Generate a full suite of marketing materials tailored for various platforms:
    *   `screenshot.png` (Theme preview).
    *   **Gumroad Hero Image & Gallery:** High-resolution images optimized for Gumroad's platform.
    *   **Envato Preview Images:** Specific dimensions and content for Envato Market.
    *   **Etsy Listing Images:** Multiple images showcasing features and design for Etsy.
    *   **Animated Preview GIF/Video:** A short, engaging animation demonstrating key features and interactions.
    *   **Product Description:** Compelling copy highlighting features, benefits, and target audience.
    *   **Feature List:** Detailed breakdown of all functionalities.
    *   **Changelog & Release Notes:** Documenting updates, bug fixes, and new features.
    *   **SEO Keywords & Tags:** Optimized keywords for marketplace search visibility.
*   **Legal & Meta:** `LICENSE.txt`, `CHANGELOG.md`, `CREDITS.md` (for images/fonts), and `FAQ.md`.
*   **Marketplace Compliance Matrix:** Platform-specific matrices (e.g., Gumroad, Envato, Etsy) detailing requirements for ZIP structure, cover images, product descriptions, documentation, theme requirements, licensing, preview assets, coding standards, digital download structure, listing imagery, and product file organization. This ensures deterministic marketplace preparation.

### 7.2. Final Packaging (The ZIP Manifest)

The final output is a single `[SITE_NAME]-Package.zip` containing:

1.  **`/HTML/`**: The static reference build.
2.  **`/Elementor/`**: The `.json` templates, global styles, reusable templates, and global presets.
3.  **`/WordPress/`**: The installable theme folder.
4.  **`/Documentation/`**: All guides and manuals.
5.  **`Project-Manifest.json`**: Comprehensive metadata including:
    *   `specificationVersion`: The version of this WGES document.
    *   `promptVersion`: The version of the initial prompt used.
    *   `designSystemVersion`: The version of the Design System (tokens, components, motion).
    *   `themeVersion`
    *   `wordpressVersion`
    *   `elementorVersion`
    *   `phpVersion`
    *   `browserSupport` (e.g., `["IE >= 11", "Chrome >= 80", "Firefox >= 70", "Safari >= 13"]`)
    *   `externalDependencies` (e.g., `Font Awesome`, `Google Fonts`)
    *   `fonts` (list of font files used)
    *   `icons` (list of icon sets used)
    *   `licenses` (details of all third-party licenses)
    *   `checksum` / `versionHistory` (for integrity and tracking changes)

---

## 8. Phase 6: QA & Self-Healing Workflow (QA Agent)

The agent system must perform a final verification before delivery, with a robust **AI Self-Healing** mechanism. This phase is executed by the **QA Agent**.

### 8.1. Testing Standards & Design Fidelity Metrics

*   **Validation:** Run internal checks for HTML/CSS validity, PHP linting, and adherence to all defined specifications (versioned design tokens, component library, naming conventions).
*   **Accessibility Check:** Verify WCAG 2.1 AA compliance, including contrast ratios, keyboard navigability, and proper ARIA attributes.
*   **Responsive Audit:** Test layouts at a comprehensive range of breakpoints (e.g., 320px, 375px, 425px, 768px, 1024px, 1280px, 1440px, 1920px) to ensure fluid and consistent presentation across devices.
*   **Browser Compatibility Matrix:** Conduct tests across specified browser versions (e.g., latest Chrome, Firefox, Safari, Edge, and IE11 if required).
*   **Keyboard-Only Navigation Tests:** Verify full site navigability and interaction using only the keyboard.
*   **Dark Mode Verification:** If applicable, test the site's appearance and functionality in dark mode.
*   **Print Stylesheet Validation:** Ensure the site renders correctly when printed.
*   **Lighthouse Thresholds:** Achieve predefined scores for Performance, Accessibility, SEO, and Best Practices.
*   **Design Fidelity Scorecard:** Objectively measure the output against the original design inspiration:

| Metric                | Target  |
| :-------------------- | :------ |
| Layout similarity     | ≥95%    |
| Typography hierarchy  | ≥95%    |
| Color accuracy        | ≥98%    |
| Spacing consistency   | ≥95%    |
| Component fidelity    | ≥95%    |
| Animation fidelity    | ≥90%    |

### 8.2. Design Diff Analysis & Regression Testing

Before final delivery, and especially when regenerating an existing project, a **Design Diff Analysis** must be performed to compare the AI's output against the original inspiration or previous versions. This analysis verifies:

*   **Layout Proportions:** Consistency in relative sizing and positioning of major blocks.
*   **Spacing Rhythm:** Adherence to the defined spacing scales.
*   **Typography Hierarchy:** Accurate reproduction of font sizes, weights, and line heights.
*   **Color Relationships:** Correct application of color palette and contrasts.
*   **Component Placement:** Precise positioning of UI elements within their respective sections.

This process generates a **Design Fidelity Report** with objective scores. For regeneration tasks, **Regression Testing** is performed to ensure no unintended regressions in:

*   Layout
*   Responsiveness
*   Accessibility
*   SEO
*   Component Behavior

### 8.3. AI Self-Healing Repair Loop & Error Taxonomy

If any check fails, the QA Agent must initiate a defined repair loop, guided by a formalized **Error Taxonomy**:

1.  **Detect:** Identify the specific issue and its location.
2.  **Diagnose:** Determine the root cause of the failure based on established rules and previous phase outputs.
3.  **Repair:** Automatically apply the necessary fix, referencing the Design Knowledge Base, component library, or coding standards.
4.  **Re-test:** Re-run the relevant validation checks.
5.  **Repeat:** Continue the Detect-Diagnose-Repair-Re-test cycle until the issue is resolved or a predefined maximum number of attempts is reached, at which point it flags for human intervention.

**Error Taxonomy:** Failures are categorized to guide repair actions and reporting:

*   **Critical:** System-breaking errors, rendering the output unusable (e.g., site won't load, major functionality broken). Requires immediate, high-priority repair.
*   **Major:** Significant functional or visual defects impacting user experience (e.g., broken forms, incorrect layouts on key breakpoints). Requires high-priority repair.
*   **Minor:** Small functional or visual inconsistencies (e.g., slight spacing discrepancies, minor alignment issues). Requires standard repair.
*   **Cosmetic:** Aesthetic imperfections that do not impact functionality (e.g., pixel-perfect deviations). Requires low-priority repair or human review.

### 8.4. AI Confidence Reporting

At the completion of every project, the AI system will generate a comprehensive report summarizing its performance and adherence to standards:

*   **Design Fidelity:** [Score from Scorecard]
*   **Accessibility:** [Pass/Fail]
*   **SEO:** [Pass/Fail]
*   **Responsive:** [Pass/Fail]
*   **WordPress Compatibility:** [Pass/Fail]
*   **Elementor Compatibility:** [Pass/Fail]
*   **Marketplace Readiness:** [Pass/Fail]
*   **Lighthouse Scores:** [Performance, Accessibility, SEO, Best Practices]
*   **Regression Test Status:** [Pass/Fail, if applicable]

---

## 9. Execution Instructions for AI Agent System

*   **Continuous Generation:** If the task exceeds token limits, the agent system MUST explicitly state "Continuing generation of [File Name]" and proceed until the entire ZIP manifest is fulfilled.
*   **No Stop Policy:** The task is only complete when the `Project-Manifest.json` is generated and the final `.zip` is ready for download.
*   **Industry Specificity:** Adapt layouts and copy based on the detected business type (e.g., trust indicators for Medical, conversion funnels for SaaS), informed by the initial business context analysis and **Industry Knowledge Modules**.
*   **Plugin Architecture:** The WGES is designed with an extensible plugin architecture, allowing future capabilities (e.g., WooCommerce support, multilingual support, additional page builders) to be added without rewriting the core specification. New plugins must adhere to Agent Contracts and integrate with the Design Knowledge Base.
*   **AI Learning Log:** At the end of each project, a structured report will be generated containing:
    *   Lessons learned from the project execution.
    *   Reusable components or patterns created.
    *   New design patterns or architectural insights discovered.
    *   Identified areas for future improvements to the WGES or agent capabilities.

---

## 10. Appendices & Supporting Documentation (Implied)

This Engineering Standard serves as the top-level document. Supporting documentation, which would be versioned and referenced, includes:

*   Agent definitions and responsibilities (detailed JSON schemas).
*   Standard Operating Procedures (SOPs) for each agent's workflow.
*   Decision trees and workflow diagrams for complex scenarios.
*   Validation matrices for quality assurance.
*   JSON schemas for design tokens and component specifications.
*   WordPress file architecture diagrams.
*   Elementor widget mapping tables.
*   Marketplace submission checklists (platform-specific).
*   Quality assurance matrices.
*   Troubleshooting guides.
*   Versioning and release processes.

This comprehensive **Website Generation Engineering Standard (WGES) v5.0** ensures that the AI agent system consistently produces premium, marketplace-ready website packages, adhering to the highest engineering and design standards, and is built for continuous evolution and operational excellence.
