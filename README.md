# BRAE 4428: Agricultural Robotics and Automation

---

<style>
  .grid-container {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    gap: 20px;
    margin-top: 20px;
  }
  .card {
    border: 1px solid #e1e4e8;
    border-radius: 10px;
    padding: 20px;
    background: #ffffff;
    box-shadow: 0 4px 6px rgba(0,0,0,0.05);
    transition: transform 0.2s, box-shadow 0.2s;
    text-decoration: none !important;
    color: inherit !important;
  }
  .card:hover {
    transform: translateY(-5px);
    box-shadow: 0 8px 15px rgba(0,0,0,0.1);
    border-color: #0366d6;
  }
  .card h3 {
    margin-top: 0;
    color: #0366d6;
    font-size: 1.2rem;
  }
  .card p {
    font-size: 0.9rem;
    color: #586069;
    margin-bottom: 0;
  }
  .tag {
    display: inline-block;
    background: #f1f8ff;
    color: #0366d6;
    padding: 2px 8px;
    border-radius: 12px;
    font-size: 0.75rem;
    font-weight: bold;
    margin-bottom: 10px;
  }
</style>

<div class="grid-container">
{% for file in site.static_files %}
  {% if file.extname == ".html" and file.name != "index.html" %}
    <a href="{{ file.path | relative_url }}" class="card">
      <span class="tag">Module</span>
      <h3>{{ file.basename | replace: "_", " " }}</h3>
      <p>Click to open the interactive engineering tool.</p>
    </a>
  {% endif %}
{% endfor %}
</div>
