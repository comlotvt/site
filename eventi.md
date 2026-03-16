---
layout: page
title: Eventi
css: "/assets/css/index.css"
---

<div class="search-container">
  <div class="search-box">
    <svg class="search-icon" width="20" height="20" viewBox="0 0 24 24" fill="none"
      xmlns="http://www.w3.org/2000/svg">
      <circle cx="11" cy="11" r="8" stroke="currentColor" stroke-width="2" stroke-linecap="round"
        stroke-linejoin="round" />
      <path d="m21 21-4.35-4.35" stroke="currentColor" stroke-width="2" stroke-linecap="round"
        stroke-linejoin="round" />
    </svg>
    <input type="text" id="blog-search" placeholder="Search posts by title, content, or tags..." autocomplete="off">
    <button type="button" id="clear-search" class="clear-search" style="display: none;" title="Clear search">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
        <line x1="18" y1="6" x2="6" y2="18" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" />
        <line x1="6" y1="6" x2="18" y2="18" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" />
      </svg>
    </button>
  </div>
  <span class="post-count" id="post-count">{{ site.posts.size }} eventi</span>
</div>

<div class="event-grid">
  {% for post in site.posts %}
  {% comment %} Extract first image from post content for card display {% endcomment %}
  {% assign image_url = '' %}

  {% comment %} Look for markdown images first {% endcomment %}
  {% assign md_images = post.content | split: '![' %}
  {% if md_images.size > 1 %}
  {% for md_img in md_images %}
  {% if md_img contains '](' %}
  {% assign img_parts = md_img | split: '](' %}
  {% if img_parts.size > 1 %}
  {% assign potential_url = img_parts[1] | split: ')' | first | strip %}
  {% if potential_url contains '/static/img/' or potential_url contains '.png' or potential_url contains '.jpg' or
  potential_url contains '.jpeg' or potential_url contains '.gif' %}
  {% assign image_url = potential_url %}
  {% break %}
  {% endif %}
  {% endif %}
  {% endif %}
  {% endfor %}
  {% endif %}

  {% comment %} Fallback: look for HTML img tags {% endcomment %}
  {% if image_url == '' %}
  {% assign html_images = post.content | split: '<img ' %}
      {% if html_images.size > 1 %}
        {% assign img_tag = html_images[1] | split: '>' | first %}
  {% if img_tag contains 'src="' %}
  {% assign image_url = img_tag | split: 'src="' | last | split: '"' | first | strip %}
  {% endif %}
  {% endif %}
  {% endif %}

<div class="events-timeline">
  <div class="year-section" id="year-2026">
    <div class="year-header">
      <h2 class="year-title">2026</h2>
    </div>
    <div class="event-item">
      <img src="https://raw.githubusercontent.com/comlotvt/site/refs/heads/main/assets/img/2026-02-08 - Convegno Viterbo.jpeg">
      <h4>08-02-2026 - Convegno "Sabotiamo la Guerra e la Repressione"</h4>
      <div class="event-tags">
        <span class="event-tag">convegno</span>
        <span class="event-tag">palestina</span>
      </div>
    </div>
    <div class="event-item">
      <img src="https://raw.githubusercontent.com/comlotvt/site/refs/heads/main/assets/img/2026-02-07 - Corteo Viterbo.jpg">
      <h4>07-02-2026 - Corteo "Sabotiamo la Guerra e la Repressione"</h4>
      <div class="event-tags">
        <span class="event-tag">corteo</span>
        <span class="event-tag">palestina</span>
      </div>
    </div>
    <div class="event-item">
      <img src="https://raw.githubusercontent.com/comlotvt/site/refs/heads/main/assets/img/2026-01-24 - Presidio Viterbo.jpg">
      <h4>24-01-2026 - Presidio contro il DDL Gasparri - Delrio</h4>
      <div class="event-tags">
        <span class="event-tag">palestina</span>
        <span class="event-tag">presidio</span>
      </div>
    </div>
  </div>
</div>

<div class="events-timeline">
  <div class="year-section" id="year-2025">
    <div class="year-header">
      <h2 class="year-title">2025</h2>
    </div>
    <div class="event-item">
      <img src="https://raw.githubusercontent.com/comlotvt/site/refs/heads/main/assets/img/2025-10-26 - Proiezione Anan.jpg">
      <h4>26-10-2025 - Proiezione del documentario "Colpevoli di Palestina"</h4>
      <div class="event-tags">
        <span class="event-tag">palestina</span>
        <span class="event-tag">proiezione</span>
      </div>
    </div>
    <div class="event-item">
      <img src="https://raw.githubusercontent.com/comlotvt/site/refs/heads/main/assets/img/2025-09-28 - Proiezione Anan.jpg">
      <h4>28-09-2025 - Proiezione del documentario "Colpevoli di Palestina"</h4>
      <div class="event-tags">
        <span class="event-tag">palestina</span>
        <span class="event-tag">proiezione</span>
      </div>
    </div>
    <div class="event-item">
      <img src="https://raw.githubusercontent.com/comlotvt/site/refs/heads/main/assets/img/2025-09-18 - Presidio LazioDisco.jpg">
      <h4>18-09-2025 - Presidio per il diritto allo studio per Walaa e Haya</h4>
      <div class="event-tags">
        <span class="event-tag">palestina</span>
        <span class="event-tag">presidio</span>
      </div>
    </div>
    <div class="event-item">
      <img src="https://raw.githubusercontent.com/comlotvt/site/refs/heads/main/assets/img/2025-07-18 - Presidio Gelco.jpg">
      <h4>18-07-2025 - Assemblea presso la Gelco S.P.A.</h4>
      <div class="event-tags">
        <span class="event-tag">palestina</span>
        <span class="event-tag">presidio</span>
      </div>
    </div>
    <div class="event-item">
      <img src="https://raw.githubusercontent.com/comlotvt/site/refs/heads/main/assets/img/2025-06-14 - Presentazione Libro.jpg">
      <h4>14-06-2025 - Presentazione del libro "Senza Stato" di Rosalba Belmonte</h4>
      <div class="event-tags">
        <span class="event-tag">palestina</span>
        <span class="event-tag">presentazione</span>
      </div>
    </div>
    <div class="event-item">
      <img src="https://raw.githubusercontent.com/comlotvt/site/refs/heads/main/assets/img/2025-05-16 - Presidio Nakba.jpg">
      <h4>16-05-2025 - Presidio per i 77 anni dalla Nakba</h4>
      <div class="event-tags">
        <span class="event-tag">palestina</span>
        <span class="event-tag">presidio</span>
      </div>
    </div>
    <div class="event-item">
      <img src="https://raw.githubusercontent.com/comlotvt/site/refs/heads/main/assets/img/2025-05-10 - Presentazione Libro.jpg">
      <h4>10-05-2025 - Presentazione del libro "L'Attacco degli Imprenditori" di Emiliano Gentili</h4>
      <div class="event-tags">
        <span class="event-tag">lavoro</span>
        <span class="event-tag">presentazione</span>
      </div>
    </div>
    <div class="event-item">
      <img src="https://raw.githubusercontent.com/comlotvt/site/refs/heads/main/assets/img/2025-05-01 - Corteo 1 Maggio.jpg">
      <h4>01-05-2025 - Corteo per il 1 Maggio</h4>
      <div class="event-tags">
        <span class="event-tag">lavoro</span>
        <span class="event-tag">corteo</span>
      </div>
    </div>
    <div class="event-item">
      <img src="https://raw.githubusercontent.com/comlotvt/site/refs/heads/main/assets/img/2025-03-15 - Presentazione Libro.jpg">
      <h4>15-03-2025 - Presentazione del libro "Ignorare l'Assenza" di Valeria Roma</h4>
      <div class="event-tags">
        <span class="event-tag">palestina</span>
        <span class="event-tag">presentazione</span>
      </div>
    </div>
    <div class="event-item">
      <img src="https://raw.githubusercontent.com/comlotvt/site/refs/heads/main/assets/img/2025-02-01 - Corteo Viterbo.jpg">
      <h4>01-02-2025 - Corteo per la Palestina libera</h4>
      <div class="event-tags">
        <span class="event-tag">corteo</span>
        <span class="event-tag">palestina</span>
      </div>
    </div>
  </div>
</div>
  {% endfor %}
</div>

<!-- Search Data for JavaScript -->
<script type="application/json" id="search-data">
[
  {% for post in site.posts %}
  {
    "title": {{ post.title | jsonify }},
    "date": "{{ post.date | date: '%B %d, %Y' }}",
    "url": "{{ post.url | relative_url }}",
    "excerpt": {{ post.excerpt | default: post.content | strip_html | truncatewords: 25 | jsonify }},
    "content": {{ post.content | strip_html | jsonify }},
    "tags": {{ post.tags | jsonify }},
    "mathjax": {{ post.mathjax | jsonify }}
  }{% unless forloop.last %},{% endunless %}
  {% endfor %}
]
</script>

<!-- Blog Search JavaScript -->
<script>
  document.addEventListener('DOMContentLoaded', function () {
    const searchInput = document.getElementById('blog-search');
    const clearButton = document.getElementById('clear-search');
    const postCount = document.getElementById('post-count');
    const blogGrid = document.querySelector('.blog-grid');
    const blogCards = document.querySelectorAll('.blog-card');
    const searchData = JSON.parse(document.getElementById('search-data').textContent);

    let totalPosts = blogCards.length;

    // Search functionality
    function performSearch(query) {
      const normalizedQuery = query.toLowerCase().trim();

      if (!normalizedQuery) {
        showAllPosts();
        return;
      }

      let visibleCount = 0;

      blogCards.forEach((card, index) => {
        const post = searchData[index];
        const matchesQuery =
          post.title.toLowerCase().includes(normalizedQuery) ||
          post.content.toLowerCase().includes(normalizedQuery) ||
          post.excerpt.toLowerCase().includes(normalizedQuery) ||
          post.tags.some(tag => tag.toLowerCase().includes(normalizedQuery));

        if (matchesQuery) {
          card.style.display = 'flex';
          card.style.animation = 'fadeInUp 0.3s ease-out';
          visibleCount++;
        } else {
          card.style.display = 'none';
        }
      });

      updatePostCount(visibleCount, normalizedQuery);
      showNoResultsIfNeeded(visibleCount, normalizedQuery);
    }

    function showAllPosts() {
      blogCards.forEach(card => {
        card.style.display = 'flex';
        card.style.animation = 'fadeInUp 0.3s ease-out';
      });
      updatePostCount(totalPosts);
      hideNoResults();
    }

    function updatePostCount(count, query = '') {
      if (query) {
        postCount.textContent = `${count} result${count !== 1 ? 's' : ''} for "${query}"`;
      } else {
        postCount.textContent = `${count} article${count !== 1 ? 's' : ''}`;
      }
    }

    function showNoResultsIfNeeded(count, query) {
      hideNoResults();

      if (count === 0) {
        const noResults = document.createElement('div');
        noResults.className = 'no-search-results';
        noResults.innerHTML = `
        <svg width="64" height="64" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
          <circle cx="11" cy="11" r="8" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="m21 21-4.35-4.35" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          <line x1="11" y1="8" x2="11" y2="14" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          <line x1="8" y1="11" x2="14" y2="11" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
        <h2>No posts found</h2>
        <p>No articles match your search for "<strong>${query}</strong>". Try different keywords or browse all posts.</p>
        <button onclick="clearSearch()" class="clear-search-btn">Clear search</button>
      `;

        blogGrid.appendChild(noResults);
      }
    }

    function hideNoResults() {
      const existing = document.querySelector('.no-search-results');
      if (existing) {
        existing.remove();
      }
    }

    function clearSearch() {
      searchInput.value = '';
      clearButton.style.display = 'none';
      showAllPosts();
      searchInput.focus();
    }

    // Make clearSearch globally available
    window.clearSearch = clearSearch;

    // Search input events
    searchInput.addEventListener('input', function () {
      const query = this.value;

      if (query.length > 0) {
        clearButton.style.display = 'block';
      } else {
        clearButton.style.display = 'none';
      }

      // Debounce search for better performance
      clearTimeout(searchInput.searchTimeout);
      searchInput.searchTimeout = setTimeout(() => {
        performSearch(query);
      }, 150);
    });

    // Clear button event
    clearButton.addEventListener('click', clearSearch);

    // Keyboard shortcuts
    searchInput.addEventListener('keydown', function (e) {
      if (e.key === 'Escape') {
        clearSearch();
      }
    });

    // Focus search on Ctrl/Cmd + K
    document.addEventListener('keydown', function (e) {
      if ((e.ctrlKey || e.metaKey) && e.key === 'k') {
        e.preventDefault();
        searchInput.focus();
      }
    });
  });
</script>
