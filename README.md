🖱️ Click and Reveal: Developing a Scenario

A sophisticated interactive learning component designed for case studies and scenario-based training. This activity uses a "sidebar-to-detail" architecture to guide learners through multi-stage narratives.

🚀 Live Demo

Explore the Scenario Development Activity Here

✨ Project Overview

This component facilitates "Progressive Disclosure," a design pattern that sequences information to prevent overwhelming the user. It is structured into three distinct narrative beats: Initial Setup, The Challenge, and Proposed Outcome.

Key Features

Multi-Stage Navigation: A vertical sidebar allows learners to toggle between different scenarios or "stages" of a single evolving case study.

Step-by-Step Reveal: Content within a stage is locked behind interaction triggers. Learners must click "Reveal Challenge" and then the "Consultant Icon" to see the full picture.

Visual Hierarchy: Uses high-contrast color coding for different types of information (Teal for outcomes, Light Aqua for setups, White/Grey for challenges).

Entrance Animations: Smooth CSS keyframe animations (fadeIn) provide a polished feel as details slide into view.

🛠️ Technical Implementation

Data-Driven UI: All scenario text is stored in a scenarioData JavaScript object. This makes the component "headless," allowing developers to update content without touching the HTML structure.

State Reset Logic: Every time a new stage is opened via openStage(), the UI state resets—hiding previously revealed challenges and outcomes to ensure the learner follows the intended path.

Flexbox Layout: Utilizes a responsive flex-row (desktop) and flex-col (mobile) strategy to ensure the sidebar remains accessible across devices.

SVG Wayfinding: Each stage card features a unique SVG icon to differentiate parts of the learning journey (Checkmark, Lightning Bolt, Group Icon).

📂 Design Tokens

Midnight Blue (#1f2a52): Primary branding color used for the header bar and text headings.

Teal (#00bec7): The "Action" color, used for primary buttons, active icons, and the final response box.

Light Aqua (#d2f0f0): Secondary background color for sidebar cards and initial setup boxes.

Slate Grey (#abb5bf): Used for borders and inactive UI elements.

📖 Usage Instructions

Updating Content

To change the scenario text, modify the scenarioData object in the <script> section:

const scenarioData = {
    'stage1': {
        title: 'New Title',
        initial: 'Background info...',
        challenge: 'The problem...',
        response: 'The solution...'
    }
};


Adding Stages

Add a new entry to the scenarioData object with a unique ID (e.g., 'stage4').

Add a corresponding stage-card div in the .sidebar-column section:

<div class="stage-card" onclick="openStage('stage4', this)">
    <div class="icon-box">
        <!-- Your SVG Icon -->
    </div>
    <span class="stage-title">Stage Four</span>
</div>


📄 License

MIT License - Developed as part of the accounts-eles UI component library.
