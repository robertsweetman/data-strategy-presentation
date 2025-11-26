# Timescales for Change

<style>
  /* Default for dark themes - white text */
  .mermaid text {
    fill: white !important;
  }
  .mermaid .taskText, 
  .mermaid .sectionTitle, 
  .mermaid .grid text, 
  .mermaid .tickText,
  .mermaid .titleText,
  .mermaid .labelText,
  .mermaid .loopText,
  .mermaid .actor text {
    fill: white !important;
  }
  
  /* Handle mdBook light and rust themes - black text */
  html.light .mermaid text,
  html.light .mermaid .taskText,
  html.light .mermaid .sectionTitle,
  html.light .mermaid .grid text,
  html.light .mermaid .tickText,
  html.light .mermaid .titleText,
  html.light .mermaid .labelText,
  html.light .mermaid .loopText,
  html.light .mermaid .actor text,
  html.rust .mermaid text,
  html.rust .mermaid .taskText,
  html.rust .mermaid .sectionTitle,
  html.rust .mermaid .grid text,
  html.rust .mermaid .tickText,
  html.rust .mermaid .titleText,
  html.rust .mermaid .labelText,
  html.rust .mermaid .loopText,
  html.rust .mermaid .actor text {
    fill: black !important;
  }
  
  /* Ensure dark themes have white text */
  html.navy .mermaid text,
  html.navy .mermaid .taskText,
  html.navy .mermaid .sectionTitle,
  html.navy .mermaid .grid text,
  html.navy .mermaid .tickText,
  html.navy .mermaid .titleText,
  html.navy .mermaid .labelText,
  html.navy .mermaid .loopText,
  html.navy .mermaid .actor text,
  html.ayu .mermaid text,
  html.ayu .mermaid .taskText,
  html.ayu .mermaid .sectionTitle,
  html.ayu .mermaid .grid text,
  html.ayu .mermaid .tickText,
  html.ayu .mermaid .titleText,
  html.ayu .mermaid .labelText,
  html.ayu .mermaid .loopText,
  html.ayu .mermaid .actor text,
  html.coal .mermaid text,
  html.coal .mermaid .taskText,
  html.coal .mermaid .sectionTitle,
  html.coal .mermaid .grid text,
  html.coal .mermaid .tickText,
  html.coal .mermaid .titleText,
  html.coal .mermaid .labelText,
  html.coal .mermaid .loopText,
  html.coal .mermaid .actor text {
    fill: white !important;
  }
  
  /* Ensure links and other specific elements have correct colors in light themes */
  html.light .mermaid .flowchart-link,
  html.rust .mermaid .flowchart-link {
    stroke: #333 !important;
  }
  
  /* Ensure links have correct colors in dark themes */
  html.navy .mermaid .flowchart-link,
  html.ayu .mermaid .flowchart-link,
  html.coal .mermaid .flowchart-link {
    stroke: #ccc !important;
  }
  
  /* Additional styles for better visibility in all themes */
  .mermaid .grid path {
    stroke-opacity: 0.5;
  }
  .mermaid .today {
    stroke-width: 2px;
  }
</style>

```mermaid
gantt
    title Data Strategy Implementation
    dateFormat YYYY-MM-DD
    axisFormat %b '%y
    tickInterval 1month
    
    section Assess
    Current State   :a1, 2025-06-01, 3w
    Project Brief   :a2, after a1, 4w
    Executive Sponsorship :crit, a2a, after a1, 6w
    Stakeholder Engagement :crit, a2b, after a2, 8w
    Go/No-Go Decision :milestone, a2c, after a2b
   
    section Plan
    Technical Outline :a3, after a2b, 4w
    Ramp up Resources :a4, after a3, 2w
    
    section POC
    Investigation   :a5, after a4, 3w
    POC Development   :a6, after a4, 8w
    Internal Testing :a7, after a6, 4w
```

```mermaid
gantt
    title Data Strategy Implementation - Deployment
    dateFormat YYYY-MM-DD
    axisFormat %b '%y
    tickInterval 1month
    
    section Pilot
    Staff Training   :a1, 2026-02-01, 6w
    Internal Pilot   :a2, after a1, 12w
    Security Testing :crit, a3, after a1, 12w
    Pilot Assesment Period :a4, after a3, 12w
    Pilot Review     :milestone, a5, after a4
    
    section Rollout
    Rollout Go/No-Go Decision :milestone, a6, after a4
    Rollout      :a7, after a6, 24w
    Assessment   :milestone, a8, after a7
```

Assessments will be ongoing to course correct to meet the goals over the long term.
