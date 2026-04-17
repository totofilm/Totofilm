<meta name='viewport' content='width=device-width, initial-scale=1'/><!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
  <title>TOTO FILM - أفلام ومسلسلات | مشاهدة حلقات</title>
  <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;600;700;800&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    body {
      background: #0a0a0f;
      font-family: 'Cairo', sans-serif;
      color: #f0f0f0;
    }
    ::-webkit-scrollbar { width: 6px; }
    ::-webkit-scrollbar-track { background: #1a1a24; }
    ::-webkit-scrollbar-thumb { background: #e50914; border-radius: 10px; }

    .header {
      background: linear-gradient(135deg, #0b0b10, #14141e);
      padding: 1rem 5%;
      display: flex;
      align-items: center;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 1rem;
      position: sticky;
      top: 0;
      z-index: 1000;
      border-bottom: 1px solid #e50914;
    }
    .logo h1 {
      font-size: 2rem;
      background: linear-gradient(135deg, #e50914, #ffaa00);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }
    .logo span {
      font-size: 0.8rem;
      color: #ffaa00;
    }
    .search-box {
      display: flex;
      background: #252530;
      border-radius: 50px;
      padding: 0.5rem 1rem;
      gap: 0.5rem;
      border: 1px solid #3a3a48;
    }
    .search-box input {
      background: none;
      border: none;
      outline: none;
      color: white;
      font-size: 1rem;
      width: 240px;
    }
    .search-box i { color: #e50914; }
    .nav-links a {
      color: #ddd;
      margin-right: 1.5rem;
      font-weight: 600;
      transition: 0.2s;
    }
    .nav-links a.active, .nav-links a:hover { color: #e50914; }

    .hero-slider {
      padding: 0 5%;
      margin: 1rem 0 2rem;
    }
    .hero-track {
      display: flex;
      gap: 1rem;
      overflow-x: auto;
      padding-bottom: 0.5rem;
    }
    .hero-item {
      min-width: 280px;
      background: #1f1f2a;
      border-radius: 20px;
      overflow: hidden;
      cursor: pointer;
      transition: 0.2s;
    }
    .hero-item img {
      width: 100%;
      height: 160px;
      object-fit: cover;
    }
    .hero-item div {
      padding: 8px;
    }

    .container { padding: 0 5%; margin: 2rem 0; }
    .section-header {
      display: flex;
      justify-content: space-between;
      border-right: 4px solid #e50914;
      padding-right: 15px;
      margin-bottom: 1.2rem;
    }
    .movie-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(170px, 1fr));
      gap: 1.8rem;
    }
    .movie-card {
      background: #15151f;
      border-radius: 20px;
      overflow: hidden;
      cursor: pointer;
      transition: 0.25s;
    }
    .movie-card:hover { transform: translateY(-6px); box-shadow: 0 12px 20px rgba(0,0,0,0.5); }
    .poster {
      aspect-ratio: 2/3;
      position: relative;
    }
    .poster img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
    .rating {
      position: absolute;
      top: 8px;
      right: 8px;
      background: #000000aa;
      padding: 2px 8px;
      border-radius: 20px;
      font-size: 0.8rem;
      color: gold;
    }
    .movie-info { padding: 0.7rem; }
    .movie-info h3 { font-size: 1rem; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }

    /* Modal */
    .modal {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0,0,0,0.96);
      z-index: 2000;
      display: flex;
      align-items: center;
      justify-content: center;
      backdrop-filter: blur(6px);
    }
    .modal-content {
      background: #12121c;
      width: 90%;
      max-width: 1100px;
      max-height: 90vh;
      border-radius: 28px;
      overflow-y: auto;
      direction: rtl;
    }
    .modal-header {
      background-size: cover;
      padding: 2rem;
      position: relative;
    }
    .close-modal {
      position: absolute;
      left: 20px;
      top: 20px;
      background: #e50914;
      width: 36px;
      height: 36px;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      cursor: pointer;
    }
    .season-tab {
      display: flex;
      gap: 0.8rem;
      flex-wrap: wrap;
      border-bottom: 1px solid #333;
      padding-bottom: 0.8rem;
      margin-bottom: 1rem;
    }
    .season-btn {
      background: #2a2a36;
      border: none;
      padding: 6px 18px;
      border-radius: 30px;
      color: white;
      cursor: pointer;
    }
    .season-btn.active { background: #e50914; }
    .episode-item {
      background: #1e1e2a;
      border-radius: 16px;
      padding: 0.8rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
      gap: 0.8rem;
      margin-bottom: 0.5rem;
    }
    .watch-ep-btn, .watch-movie-btn {
      background: #e50914;
      border: none;
      padding: 6px 18px;
      border-radius: 40px;
      cursor: pointer;
    }
    iframe {
      width: 100%;
      height: 380px;
      border-radius: 20px;
      border: none;
      margin-top: 1rem;
    }
    footer {
      background: #08080c;
      text-align: center;
      padding: 1.5rem;
      margin-top: 2rem;
      border-top: 1px solid #222;
    }
    .instagram-link {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      background: #1e1e2a;
      padding: 6px 16px;
      border-radius: 40px;
      margin-top: 10px;
      color: #f0f0f0;
      text-decoration: none;
      transition: 0.2s;
    }
    .instagram-link i { color: #e4405f; font-size: 1.2rem; }
    .instagram-link:hover { background: #e50914; }
    .btn-watch { background: #e50914; padding: 6px 18px; border-radius: 40px; border: none; color: white; cursor: pointer; }
    @media (max-width: 700px) {
      .movie-grid { grid-template-columns: repeat(auto-fill, minmax(130px, 1fr)); }
    }
  </style>
</head>
<body>

<header class="header">
  <div class="logo">
    <h1>🎬 TOTO FILM</h1>
    <span>أفلام ومسلسلات | مشاهدة حلقات</span>
  </div>
  <div class="search-box">
    <i class="fas fa-search"></i>
    <input type="text" id="searchInput" placeholder="ابحث عن فيلم أو مسلسل...">
  </div>
  <div class="nav-links">
    <a href="#" data-type="movie" class="active">أفلام</a>
    <a href="#" data-type="tv">مسلسلات</a>
  </div>
</header>

<div class="hero-slider" id="heroSlider"></div>

<main>
  <div class="container">
    <div class="section-header"><h2 id="sectionTitle">أحدث الأفلام</h2></div>
    <div class="movie-grid" id="moviesGrid">جاري التحميل...</div>
    <div style="text-align:center; margin:2rem"><button id="loadMoreBtn" class="btn-watch" style="background:#333;">تحميل المزيد</button></div>
  </div>
</main>

<footer>
  <p>© 2026 TOTO FILM - جميع الحقوق محفوظة</p>
  <p>المدير: <strong style="color:#e50914;">TAHA</strong></p>
  <a href="https://www.instagram.com/taha__officel" target="_blank" class="instagram-link">
    <i class="fab fa-instagram"></i> متابعة على إنستغرام: taha__officel
  </a>
</footer>

<script>
  const API_KEY = 'c45a857c193f6302f2b5061c3b85e743';
  const IMG = 'https://image.tmdb.org/t/p/w500';
  const BACKDROP = 'https://image.tmdb.org/t/p/original';
  
  let currentType = 'movie';
  let currentPage = 1;
  let totalPages = 100;
  let searchQuery = '';
  let isLoading = false;

  const moviesGrid = document.getElementById('moviesGrid');
  const sectionTitle = document.getElementById('sectionTitle');
  const searchInput = document.getElementById('searchInput');
  const loadMoreBtn = document.getElementById('loadMoreBtn');
  const navLinks = document.querySelectorAll('.nav-links a');

  async function fetchAPI(endpoint, params = {}) {
    const url = `https://api.themoviedb.org/3/${endpoint}?api_key=${API_KEY}&language=ar-SA&${new URLSearchParams(params)}`;
    const res = await fetch(url);
    if (!res.ok) return null;
    return await res.json();
  }

  async function fetchMedia(type, page = 1, query = '') {
    if (query.trim()) {
      const data = await fetchAPI('search/multi', { query, page });
      if (data) {
        let filtered = data.results.filter(item => item.media_type === type || (type === 'movie' && item.title) || (type === 'tv' && item.name));
        return { results: filtered, total_pages: data.total_pages };
      }
    } else {
      let endpoint = type === 'movie' ? 'movie/now_playing' : 'tv/on_the_air';
      const data = await fetchAPI(endpoint, { page });
      return { results: data?.results || [], total_pages: data?.total_pages || 0 };
    }
    return { results: [], total_pages: 0 };
  }

  function renderItems(items, append = false) {
    if (!append) moviesGrid.innerHTML = '';
    if (!items.length && !append) { moviesGrid.innerHTML = '<div style="grid-column:1/-1; text-align:center;">❌ لا توجد نتائج</div>'; return; }
    items.forEach(item => {
      const isMovie = !!item.title;
      const title = isMovie ? item.title : item.name;
      const date = isMovie ? (item.release_date || '').split('-')[0] : (item.first_air_date || '').split('-')[0];
      const posterPath = item.poster_path ? IMG + item.poster_path : 'https://via.placeholder.com/300x450?text=No+Image';
      const vote = item.vote_average ? item.vote_average.toFixed(1) : '0';
      const card = document.createElement('div');
      card.className = 'movie-card';
      card.dataset.id = item.id;
      card.dataset.type = isMovie ? 'movie' : 'tv';
      card.dataset.title = title;
      card.dataset.backdrop = item.backdrop_path ? BACKDROP + item.backdrop_path : '';
      card.dataset.overview = item.overview || '';
      card.dataset.date = date;
      card.dataset.vote = vote;
      card.innerHTML = `
        <div class="poster">
          <img src="${posterPath}" alt="${title}" loading="lazy">
          <div class="rating">⭐ ${vote}</div>
        </div>
        <div class="movie-info"><h3>${title}</h3><div class="movie-date">${date || ''}</div></div>
      `;
      card.addEventListener('click', () => openDetails(card.dataset));
      moviesGrid.appendChild(card);
    });
  }

  async function openDetails(data) {
    const type = data.type;
    const id = data.id;
    let embedHtml = '';
    if (type === 'movie') {
      embedHtml = `
        <iframe id="movieFrame" src="https://vidsrc.xyz/embed/movie/${id}" allowfullscreen></iframe>
        <div style="display:flex; gap:10px; margin-top:10px;">
          <button class="watch-movie-btn" data-src="vidsrc">مشغل 1</button>
          <button class="watch-movie-btn" data-src="2embed">مشغل 2</button>
        </div>
      `;
    } else {
      const tvDetails = await fetchAPI(`tv/${id}`);
      if (tvDetails && tvDetails.seasons) {
        const seasons = tvDetails.seasons.filter(s => s.season_number > 0);
        let seasonsHtml = `<div class="season-tab" id="seasonTabs"></div><div id="episodesList">جاري تحميل الحلقات...</div><div style="margin-top:20px;"><iframe id="episodeFrame" width="100%" height="360" frameborder="0"></iframe></div>`;
        embedHtml = seasonsHtml;
        // سنقوم بملء التبويبات لاحقاً بعد إضافة المودال
        setTimeout(async () => {
          const tabsContainer = document.getElementById('seasonTabs');
          const episodesContainer = document.getElementById('episodesList');
          const frame = document.getElementById('episodeFrame');
          if (!tabsContainer) return;
          for (let s of seasons) {
            const btn = document.createElement('button');
            btn.className = 'season-btn';
            btn.innerText = `الموسم ${s.season_number}`;
            btn.dataset.season = s.season_number;
            btn.addEventListener('click', async () => {
              document.querySelectorAll('.season-btn').forEach(b => b.classList.remove('active'));
              btn.classList.add('active');
              const epsData = await fetchAPI(`tv/${id}/season/${s.season_number}`);
              if (epsData && epsData.episodes) {
                episodesContainer.innerHTML = epsData.episodes.map(ep => `
                  <div class="episode-item">
                    <span class="episode-num">الحلقة ${ep.episode_number}</span>
                    <span>${ep.name}</span>
                    <button class="watch-ep-btn" data-season="${s.season_number}" data-episode="${ep.episode_number}">▶ تشغيل</button>
                  </div>
                `).join('');
                document.querySelectorAll('.watch-ep-btn').forEach(btn => {
                  btn.addEventListener('click', (e) => {
                    const season = btn.dataset.season;
                    const ep = btn.dataset.episode;
                    frame.src = `https://vidsrc.xyz/embed/tv/${id}/${season}/${ep}`;
                  });
                });
              } else episodesContainer.innerHTML = '<div>لا توجد حلقات</div>';
            });
            tabsContainer.appendChild(btn);
          }
          if (seasons.length) {
            seasons[0].season_number && document.querySelector('.season-btn')?.click();
          } else episodesContainer.innerHTML = '<div>لا توجد مواسم</div>';
        }, 100);
      } else {
        embedHtml = '<div>لا توجد معلومات للمسلسل</div>';
      }
    }

    const modalDiv = document.createElement('div');
    modalDiv.className = 'modal';
    modalDiv.innerHTML = `
      <div class="modal-content">
        <div class="modal-header" style="background:linear-gradient(rgba(0,0,0,0.7), rgba(0,0,0,0.9)), url('${data.backdrop || ''}'); background-size:cover;">
          <div class="close-modal">✕</div>
          <h2>${data.title}</h2>
          <p>⭐ ${data.vote} | 📅 ${data.date || ''}</p>
          <p>${data.overview?.substring(0, 200) || ''}</p>
        </div>
        <div style="padding:1rem;">
          ${embedHtml}
        </div>
      </div>
    `;
    document.body.appendChild(modalDiv);
    modalDiv.querySelector('.close-modal').onclick = () => modalDiv.remove();
    modalDiv.addEventListener('click', (e) => { if(e.target === modalDiv) modalDiv.remove(); });

    if (type === 'movie') {
      const iframe = modalDiv.querySelector('#movieFrame');
      const btns = modalDiv.querySelectorAll('.watch-movie-btn');
      btns.forEach(btn => {
        btn.addEventListener('click', () => {
          if (btn.dataset.src === 'vidsrc') iframe.src = `https://vidsrc.xyz/embed/movie/${id}`;
          else iframe.src = `https://2embed.org/embed/movie/${id}`;
        });
      });
    }
  }

  async function loadContent(reset = true) {
    if (isLoading) return;
    isLoading = true;
    if (reset) { currentPage = 1; moviesGrid.innerHTML = '<div style="text-align:center;">⏳ جاري التحميل...</div>'; }
    const { results, total_pages } = await fetchMedia(currentType, currentPage, searchQuery);
    if (total_pages) totalPages = Math.min(total_pages, 200);
    if (results && results.length) renderItems(results, !reset);
    else if (reset) moviesGrid.innerHTML = '<div style="text-align:center;">😥 لا توجد نتائج</div>';
    loadMoreBtn.style.display = (currentPage < totalPages && results?.length) ? 'block' : 'none';
    isLoading = false;
  }

  async function loadHero() {
    const trending = await fetchAPI('trending/all/week', { page: 1 });
    if (trending && trending.results) {
      const top5 = trending.results.slice(0, 5);
      const heroDiv = document.getElementById('heroSlider');
      heroDiv.innerHTML = `<div class="hero-track">${top5.map(item => {
        const title = item.title || item.name;
        const backdrop = item.backdrop_path ? BACKDROP + item.backdrop_path : IMG + item.poster_path;
        const type = item.title ? 'movie' : 'tv';
        return `<div class="hero-item" data-id="${item.id}" data-type="${type}" data-title="${title}" data-backdrop="${BACKDROP + item.backdrop_path}" data-overview="${item.overview || ''}" data-date="${item.release_date || item.first_air_date || ''}" data-vote="${item.vote_average?.toFixed(1)}">
                  <img src="${backdrop}" loading="lazy">
                  <div><strong>${title}</strong><br>⭐ ${item.vote_average?.toFixed(1)}</div>
                </div>`;
      }).join('')}</div>`;
      document.querySelectorAll('.hero-item').forEach(el => {
        el.addEventListener('click', () => {
          openDetails({
            id: el.dataset.id,
            type: el.dataset.type,
            title: el.dataset.title,
            backdrop: el.dataset.backdrop,
            overview: el.dataset.overview,
            date: el.dataset.date,
            vote: el.dataset.vote
          });
        });
      });
    }
  }

  let timeout;
  searchInput.addEventListener('input', () => {
    clearTimeout(timeout);
    timeout = setTimeout(() => {
      searchQuery = searchInput.value.trim();
      currentPage = 1;
      sectionTitle.innerText = searchQuery ? `نتائج البحث: "${searchQuery}"` : (currentType === 'movie' ? 'أحدث الأفلام' : 'أحدث المسلسلات');
      loadContent(true);
    }, 500);
  });

  function setType(type) {
    currentType = type;
    currentPage = 1;
    searchQuery = '';
    searchInput.value = '';
    sectionTitle.innerText = type === 'movie' ? 'أحدث الأفلام' : 'أحدث المسلسلات';
    loadContent(true);
    navLinks.forEach(link => {
      if (link.dataset.type === type) link.classList.add('active');
      else link.classList.remove('active');
    });
  }

  navLinks.forEach(link => {
    link.addEventListener('click', (e) => {
      e.preventDefault();
      setType(link.dataset.type);
    });
  });

  loadMoreBtn.addEventListener('click', () => {
    if (!isLoading && currentPage < totalPages) {
      currentPage++;
      loadContent(false);
    }
  });

  async function init() {
    await loadHero();
    setType('movie');
  }
  init();
</script>
</body>
</html>
