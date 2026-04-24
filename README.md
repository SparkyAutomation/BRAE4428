# Agricultural Robotics and Automation

---

<style>
  /* Modern Font Stack & Background */
  :root {
    --primary: #003831; /* Cal Poly Green */
    --accent: #d4af37; /* Cal Poly Gold */
    --card-bg: rgba(255, 255, 255, 0.8);
  }

  /* Grid Layout */
  .module-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
    gap: 25px;
    padding: 20px 0;
  }

  /* Glassmorphism Card Design */
  .module-card {
    position: relative;
    background: var(--card-bg);
    backdrop-filter: blur(10px);
    -webkit-backdrop-filter: blur(10px);
    border: 1px solid rgba(255, 255, 255, 0.3);
    border-radius: 16px;
    padding: 24px;
    text-decoration: none !important;
    color: #1f2937 !important;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
    transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }

  /* Hover Animations */
  .module-card:hover {
    transform: translateY(-8px) scale(1.02);
    box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
    border-color: var(--accent);
  }

  .module-card h3 {
    margin: 0 0 10px 0;
    font-size: 1.25rem;
    font-weight: 700;
    color: var(--primary);
  }

  .module-card p {
    font-size: 0.9rem;
    line-height: 1.5;
    color: #4b5563;
    margin-bottom: 20px;
  }

  /* Interactive Button Effect */
  .btn-launch {
    align-self: flex-start;
    background: var(--primary);
    color: white !important;
    padding: 8px 16px;
    border-radius: 8px;
    font-size: 0.8rem;
    font-weight: 600;
    transition: background 0.2s;
  }

  .module-card:hover .btn-launch {
    background: #005a4e;
  }

  /* Badge styling */
  .badge {
    background: #ecfdf5;
    color: #065f46;
    padding: 4px 10px;
    border-radius: 99px;
    font-size: 0.7rem;
    font-weight: 700;
    text-transform: uppercase;
    margin-bottom: 12px;
    display: inline-block;
  }
</style>

<div class="module-grid">
{% for file in site.static_files %}
  {% if file.extname == ".html" and file.name != "index.html" %}
    <a href="{{ file.path | relative_url }}" class="module-card">
      <div>
        <span class="badge">Interactive Lab</span>
        <h3>{{ file.basename | replace: "_", " " | replace: "ArtificialNeutralNetwork", "Neural Networks" }}</h3>
        <p>Explore the mathematical foundations and real-time simulations for {{ file.basename | replace: "_", " " }}.</p>
      </div>
      <div class="btn-launch">Launch Module →</div>
    </a>
  {% endif %}
{% endfor %}
</div>

---

### Instructions for Students
1. Select a module from the grid above.
2. Ensure your browser supports JavaScript (Chrome or Firefox recommended).
3. Use the interactive sliders to adjust parameters in real-time.

*Maintained by Bo Liu*
