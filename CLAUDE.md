# AI Agent Configuration for Visualizations Repository

This file provides instructions for AI agents (Claude Code, Claude Desktop, GitHub Copilot, etc.) working in this repository.

---

## Repository Purpose

This repository is for **Val Diaz** (MyBambu President) to deploy interactive web visualizations, dashboards, and reports to GitHub Pages.

**Live Site**: https://pwatson-mybambu.github.io/visualizations/

**Owner**: Non-technical user - simplicity and automation are critical

---

## Core Principles

1. **Simplicity First**: Val is not a developer - everything must be as simple as possible
2. **Automation Preferred**: Claude Desktop automation is the recommended workflow
3. **Modern & Professional**: Use cutting-edge UI frameworks for sleek, impressive visualizations
4. **Self-Contained**: All files must work standalone on GitHub Pages (no build step)
5. **GitHub Pages Compatible**: Static HTML/CSS/JavaScript only - no server-side code

---

## GitHub Pages Capabilities & Limitations

### ✅ What Works on GitHub Pages:

1. **Static Files**:
   - HTML, CSS, JavaScript
   - Images (PNG, JPG, SVG, WebP)
   - Fonts (WOFF, WOFF2, TTF)
   - JSON, CSV data files

2. **Client-Side Frameworks**:
   - Pure vanilla JavaScript
   - React/Vue/Svelte (if bundled to single HTML file)
   - Tailwind CSS (via CDN)
   - Chart.js, D3.js, Plotly.js
   - Mermaid diagrams

3. **CDN Libraries**:
   - Any JavaScript library via CDN (jsDelivr, unpkg, cdnjs)
   - Google Fonts, Font Awesome icons
   - CSS frameworks (Tailwind, Bootstrap)

### ❌ What Doesn't Work:

1. **Server-Side Code**:
   - No Node.js, Python, PHP, Ruby backends
   - No databases (MySQL, PostgreSQL, MongoDB)
   - No API endpoints you create (must use external APIs)

2. **Build Tools**:
   - No npm build step
   - No webpack, Vite, or bundlers
   - Everything must be pre-compiled or use CDN

3. **Dynamic Server Features**:
   - No server-side rendering (SSR)
   - No environment variables at runtime
   - No file uploads or server-side processing

---

## Recommended UI Technologies & Libraries

### 🎨 Styling Frameworks (Choose One Per Project)

#### Option 1: Tailwind CSS (Recommended for Modern Look)
```html
<script src="https://cdn.tailwindcss.com"></script>
```
- **Pros**: Ultra-modern, utility-first, highly customizable
- **Best For**: Dashboards, data displays, professional reports
- **Examples**: ShadCN-style components, modern card layouts

#### Option 2: Custom CSS with CSS Variables
```css
:root {
  --primary: #667eea;
  --secondary: #764ba2;
  --success: #10b981;
  /* Modern color scheme */
}
```
- **Pros**: Full control, no dependencies, clean code
- **Best For**: Unique designs, performance-critical pages

### 📊 Chart & Visualization Libraries

#### Chart.js (Recommended - Simplest)
```html
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
```
- **Best For**: Bar charts, line graphs, pie charts, simple dashboards
- **Pros**: Easy to use, great docs, responsive
- **Examples**: Sales data, metrics, KPIs

#### D3.js (Advanced - Most Powerful)
```html
<script src="https://d3js.org/d3.v7.min.js"></script>
```
- **Best For**: Custom visualizations, complex data relationships
- **Pros**: Extremely flexible, publication-quality graphics
- **Difficulty**: Steeper learning curve

#### Plotly.js (Interactive - Professional)
```html
<script src="https://cdn.plot.ly/plotly-2.27.0.min.js"></script>
```
- **Best For**: Scientific charts, 3D plots, interactive dashboards
- **Pros**: Highly interactive, professional appearance
- **Examples**: Financial data, scientific reports

### 🔀 Diagram Libraries

#### Mermaid (Recommended for Diagrams)
```html
<script type="module">
  import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid@10/dist/mermaid.esm.min.mjs';
  mermaid.initialize({ startOnLoad: true });
</script>
```
- **Best For**: Flowcharts, sequence diagrams, Gantt charts, ER diagrams
- **Pros**: Simple markdown-like syntax
- **Examples**:
```html
<div class="mermaid">
graph TD
    A[Start] --> B{Decision}
    B -->|Yes| C[Option 1]
    B -->|No| D[Option 2]
</div>
```

### 🎭 Animation & Interaction

#### GSAP (GreenSock Animation Platform)
```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
```
- **Best For**: Smooth animations, scroll effects, transitions
- **Pros**: Professional-grade animations, great performance

#### CSS Animations (Built-in)
```css
@keyframes fadeIn {
  from { opacity: 0; transform: translateY(20px); }
  to { opacity: 1; transform: translateY(0); }
}
```
- **Best For**: Simple hover effects, loading states
- **Pros**: No dependencies, fast, modern

---

## Standard File Structure

### Single-Page Visualization
```
artifacts/
└── dashboard-name.html          # Self-contained file
```

### Multi-Page Visualization
```
artifacts/
├── project-overview.html        # Landing page
├── project-details.html         # Detailed view
├── project-summary.html         # Summary/conclusion
└── project-assets/             # Shared resources (optional)
    ├── data.json               # Shared data
    ├── config.js               # Shared configuration
    └── styles.css              # Shared styles (if extracted)
```

**Navigation Pattern** (use relative links):
```html
<!-- In project-overview.html -->
<nav>
  <a href="project-overview.html">Overview</a>
  <a href="project-details.html">Details</a>
  <a href="project-summary.html">Summary</a>
</nav>
```

---

## File Naming Standards

**ALWAYS follow these rules:**

✅ **Good filenames:**
- `q4-revenue-dashboard.html`
- `client-presentation-march-2024.html`
- `team-performance-metrics.html`
- `sales-funnel-analysis.html`

❌ **Bad filenames:**
- `file1.html` (not descriptive)
- `my report.html` (has spaces)
- `Sales_Dashboard.html` (uses underscores)
- `dashboard!.html` (special characters)

**Rules:**
1. Use hyphens (`-`), not spaces or underscores
2. All lowercase
3. Descriptive and clear
4. End with `.html`
5. No special characters except hyphens

---

## HTML Template Pattern (Modern & Professional)

### Base Template with Tailwind CSS & Chart.js

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Your Visualization Title</title>

    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>

    <!-- Chart.js -->
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>

    <!-- Optional: Mermaid for diagrams -->
    <script type="module">
      import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid@10/dist/mermaid.esm.min.mjs';
      mermaid.initialize({ startOnLoad: true, theme: 'default' });
    </script>

    <style>
        /* Custom styles if needed */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .fade-in {
            animation: fadeIn 0.6s ease-out;
        }
    </style>
</head>
<body class="bg-gradient-to-br from-blue-50 to-purple-50 min-h-screen p-6">
    <!-- Container -->
    <div class="max-w-7xl mx-auto">
        <!-- Header -->
        <header class="bg-white rounded-2xl shadow-lg p-8 mb-6 fade-in">
            <h1 class="text-4xl font-bold text-gray-900">Dashboard Title</h1>
            <p class="text-gray-600 mt-2">Subtitle or description</p>
        </header>

        <!-- Content Grid -->
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-6">
            <!-- Card 1 - Chart -->
            <div class="bg-white rounded-2xl shadow-lg p-6 fade-in" style="animation-delay: 0.1s">
                <h2 class="text-2xl font-bold text-gray-800 mb-4">Revenue Trend</h2>
                <canvas id="myChart"></canvas>
            </div>

            <!-- Card 2 - Mermaid Diagram -->
            <div class="bg-white rounded-2xl shadow-lg p-6 fade-in" style="animation-delay: 0.2s">
                <h2 class="text-2xl font-bold text-gray-800 mb-4">Process Flow</h2>
                <div class="mermaid">
                    graph LR
                        A[Start] --> B[Process]
                        B --> C[End]
                </div>
            </div>

            <!-- Card 3 - Stats -->
            <div class="bg-white rounded-2xl shadow-lg p-6 fade-in" style="animation-delay: 0.3s">
                <h2 class="text-2xl font-bold text-gray-800 mb-4">Key Metrics</h2>
                <div class="grid grid-cols-2 gap-4">
                    <div class="text-center p-4 bg-blue-50 rounded-xl">
                        <div class="text-3xl font-bold text-blue-600">$1.2M</div>
                        <div class="text-sm text-gray-600 mt-1">Revenue</div>
                    </div>
                    <div class="text-center p-4 bg-green-50 rounded-xl">
                        <div class="text-3xl font-bold text-green-600">+23%</div>
                        <div class="text-sm text-gray-600 mt-1">Growth</div>
                    </div>
                </div>
            </div>

            <!-- Card 4 - Table -->
            <div class="bg-white rounded-2xl shadow-lg p-6 fade-in" style="animation-delay: 0.4s">
                <h2 class="text-2xl font-bold text-gray-800 mb-4">Top Performers</h2>
                <table class="w-full">
                    <thead>
                        <tr class="border-b border-gray-200">
                            <th class="text-left py-2">Name</th>
                            <th class="text-right py-2">Value</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr class="border-b border-gray-100">
                            <td class="py-2">Item 1</td>
                            <td class="text-right">$100K</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </div>

    <script>
        // Chart.js Example
        const ctx = document.getElementById('myChart').getContext('2d');
        new Chart(ctx, {
            type: 'line',
            data: {
                labels: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun'],
                datasets: [{
                    label: 'Revenue',
                    data: [12, 19, 3, 5, 2, 3],
                    borderColor: 'rgb(102, 126, 234)',
                    backgroundColor: 'rgba(102, 126, 234, 0.1)',
                    tension: 0.4
                }]
            },
            options: {
                responsive: true,
                maintainAspectRatio: true,
                plugins: {
                    legend: {
                        display: true,
                        position: 'top'
                    }
                }
            }
        });
    </script>
</body>
</html>
```

---

## Multi-Page Navigation Pattern

### Navigation Component (Include on Each Page)

```html
<!-- Sticky Navigation Bar -->
<nav class="bg-white rounded-2xl shadow-lg p-4 mb-6 sticky top-6 z-50">
    <div class="flex items-center justify-between">
        <h3 class="text-lg font-bold text-gray-800">Project Name</h3>
        <div class="flex gap-4">
            <a href="overview.html" class="px-4 py-2 rounded-lg hover:bg-blue-50 transition">Overview</a>
            <a href="details.html" class="px-4 py-2 rounded-lg hover:bg-blue-50 transition">Details</a>
            <a href="summary.html" class="px-4 py-2 rounded-lg hover:bg-blue-50 transition">Summary</a>
        </div>
    </div>
</nav>
```

### Active Page Highlighting

```html
<script>
    // Highlight current page in navigation
    const currentPage = window.location.pathname.split('/').pop();
    document.querySelectorAll('nav a').forEach(link => {
        if (link.getAttribute('href') === currentPage) {
            link.classList.add('bg-blue-500', 'text-white');
            link.classList.remove('hover:bg-blue-50');
        }
    });
</script>
```

---

## Best Practices for Val's Visualizations

### 1. **Always Include Page Title & Date**
```html
<div class="text-sm text-gray-500 mt-2">
    Created: <span id="date"></span>
</div>
<script>
    document.getElementById('date').textContent = new Date().toLocaleDateString();
</script>
```

### 2. **Mobile Responsive (Always)**
- Use Tailwind responsive classes: `sm:`, `md:`, `lg:`, `xl:`
- Test on mobile viewport (320px minimum width)
- Stack cards vertically on small screens

### 3. **Loading States for Charts**
```html
<div id="chartContainer" class="relative">
    <div id="loading" class="absolute inset-0 flex items-center justify-center">
        <div class="text-gray-400">Loading chart...</div>
    </div>
    <canvas id="myChart"></canvas>
</div>
<script>
    // Hide loading after chart renders
    const chart = new Chart(ctx, {...});
    document.getElementById('loading').style.display = 'none';
</script>
```

### 4. **Print-Friendly Styles**
```html
<style>
    @media print {
        body { background: white !important; }
        .no-print { display: none !important; }
    }
</style>
```

### 5. **Share Button (Optional)**
```html
<button onclick="navigator.share({title: 'Dashboard', url: window.location.href})"
        class="px-4 py-2 bg-blue-500 text-white rounded-lg no-print">
    Share
</button>
```

---

## Mermaid Diagram Examples

### Flowchart
```html
<div class="mermaid">
graph TD
    A[Start Process] --> B{Check Status}
    B -->|Approved| C[Deploy]
    B -->|Rejected| D[Revise]
    D --> B
    C --> E[Complete]
</div>
```

### Sequence Diagram
```html
<div class="mermaid">
sequenceDiagram
    User->>System: Submit Request
    System->>Database: Query Data
    Database-->>System: Return Results
    System-->>User: Display Data
</div>
```

### Gantt Chart
```html
<div class="mermaid">
gantt
    title Project Timeline
    dateFormat  YYYY-MM-DD
    section Phase 1
    Planning           :2024-01-01, 30d
    Development        :2024-02-01, 60d
    section Phase 2
    Testing            :2024-04-01, 30d
    Deployment         :2024-05-01, 15d
</div>
```

---

## Common Tasks

### Creating a Dashboard for Val

1. **Understand the Goal**:
   - What data needs to be visualized?
   - Who is the audience?
   - What's the key message?

2. **Choose Your Stack**:
   - Simple dashboard → Tailwind + Chart.js
   - Process flows → Tailwind + Mermaid
   - Complex data → Tailwind + D3.js or Plotly

3. **Build the Structure**:
   - Start with the base template
   - Add cards for each visualization
   - Use grid layout for organization

4. **Add Interactivity**:
   - Tooltips on charts
   - Hover effects on cards
   - Click actions if needed

5. **Polish**:
   - Add animations (fade-in effects)
   - Ensure mobile responsive
   - Add proper titles and labels

6. **Deploy**:
   - Save to `artifacts/descriptive-name.html`
   - Run: `./deploy.sh descriptive-name.html "Description"`
   - Share URL with Val

---

## Deployment Process

### Automated Method (Recommended)

When Val has Claude Desktop configured:
```
Val: "Create a Q4 sales dashboard and give me a public link"
```

Claude Desktop automatically:
1. Creates the HTML file
2. Saves to `~/Documents/visualizations/artifacts/`
3. Runs git commands to deploy
4. Provides public URL

### Manual Deployment

```bash
cd ~/Documents/visualizations
./deploy.sh filename.html "Description of changes"
```

Or with raw git commands:
```bash
git add .
git commit -m "Add filename"
git push
```

---

## Don'ts

❌ **Don't** use spaces in filenames
❌ **Don't** create files outside `artifacts/` folder (unless templates/archives)
❌ **Don't** use external CSS/JS files - keep everything inline or CDN
❌ **Don't** use absolute URLs for navigation between pages
❌ **Don't** forget to commit and push after creating files
❌ **Don't** use server-side code (Node.js, PHP, Python)
❌ **Don't** create build steps - must work directly on GitHub Pages
❌ **Don't** use npm packages that need bundling - use CDN versions

---

## Tips for Creating Impressive Visualizations

### Use Modern Color Schemes
```javascript
// Professional gradients
background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
background: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%);
```

### Add Subtle Animations
```css
.card {
    transition: transform 0.3s, box-shadow 0.3s;
}
.card:hover {
    transform: translateY(-5px);
    box-shadow: 0 20px 40px rgba(0,0,0,0.1);
}
```

### Use Icon Libraries
```html
<!-- Font Awesome -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
<i class="fas fa-chart-line"></i>

<!-- Or Unicode Emojis -->
📊 📈 📉 💰 ✅ ❌ 🎯
```

---

## Reference Files

- **For Val**: [INSTRUCTIONS_FOR_VAL.md](INSTRUCTIONS_FOR_VAL.md)
- **For Claude Desktop Setup**: [CLAUDE_DESKTOP_SETUP.md](CLAUDE_DESKTOP_SETUP.md)
- **Setup Summary**: [SETUP_SUMMARY.md](SETUP_SUMMARY.md)
- **Deploy Script**: [deploy.sh](deploy.sh)

---

**Last Updated:** 2025-10-08
**Repository Owner:** Val Diaz
**Maintainer:** Patrick Watson
