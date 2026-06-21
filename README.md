<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="MERAIR Travels - Interactive travel packages, bookings, and unforgettable experiences">
  <title>MERAIR Travels - Interactive Travel Platform</title>
  <link href="https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;500;600;700&display=swap" rel="stylesheet">
  <style>
    :root {
      --primary: #0F1B3C;
      --accent: #E63946;
      --accent-light: #FF5A5F;
      --white: #ffffff;
      --gray: #f5f5f5;
      --gray-2: #e8e8e8;
      --gray-4: #999999;
      --border: rgba(0,0,0,0.08);
      --transition: all 0.3s cubic-bezier(0.25, 0.46, 0.45, 0.94);
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      font-family: 'Outfit', sans-serif;
      background: var(--white);
      color: var(--primary);
      line-height: 1.6;
      overflow-x: hidden;
    }

    /* HEADER */
    header {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      padding: 16px 60px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      background: rgba(255, 255, 255, 0.98);
      backdrop-filter: blur(10px);
      z-index: 100;
      box-shadow: 0 2px 20px rgba(0, 0, 0, 0.05);
      transition: var(--transition);
    }

    header.scrolled {
      padding: 12px 60px;
      box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
    }

    .logo {
      font-size: 22px;
      font-weight: 700;
      color: var(--primary);
      cursor: pointer;
      transition: var(--transition);
    }

    .logo:hover {
      color: var(--accent);
    }

    .logo .accent {
      color: var(--accent);
    }

    .nav-center {
      display: flex;
      gap: 40px;
    }

    .nav-center a {
      font-size: 12px;
      text-decoration: none;
      color: var(--primary);
      font-weight: 500;
      text-transform: uppercase;
      letter-spacing: 0.05em;
      cursor: pointer;
      transition: var(--transition);
      position: relative;
    }

    .nav-center a:hover {
      color: var(--accent);
    }

    .nav-center a::after {
      content: '';
      position: absolute;
      bottom: -4px;
      left: 0;
      width: 0;
      height: 2px;
      background: var(--accent);
      transition: width 0.3s ease;
    }

    .nav-center a:hover::after {
      width: 100%;
    }

    .search-icon {
      font-size: 18px;
      cursor: pointer;
      transition: var(--transition);
    }

    .search-icon:hover {
      color: var(--accent);
    }

    .cta-button {
      padding: 12px 28px;
      background: var(--accent);
      color: var(--white);
      border: none;
      border-radius: 8px;
      font-size: 12px;
      font-weight: 600;
      cursor: pointer;
      transition: var(--transition);
      text-transform: uppercase;
      letter-spacing: 0.05em;
    }

    .cta-button:hover {
      background: var(--accent-light);
      transform: translateY(-2px);
      box-shadow: 0 8px 20px rgba(230, 57, 70, 0.3);
    }

    /* PROMO BANNER */
    .promo-banner {
      background: linear-gradient(135deg, var(--accent) 0%, var(--accent-light) 100%);
      color: var(--white);
      padding: 12px 60px;
      text-align: center;
      font-size: 13px;
      font-weight: 600;
      margin-top: 60px;
      animation: slideDown 0.5s ease;
    }

    @keyframes slideDown {
      from {
        transform: translateY(-100%);
        opacity: 0;
      }
      to {
        transform: translateY(0);
        opacity: 1;
      }
    }

    /* HERO SECTION */
    .hero {
      position: relative;
      height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      text-align: center;
      color: var(--white);
      overflow: hidden;
      margin-top: -60px;
      padding-top: 60px;
    }

    .hero-bg {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: linear-gradient(135deg, var(--primary) 0%, #1a2d5a 100%);
      z-index: 1;
      animation: gradientShift 8s ease infinite;
    }

    @keyframes gradientShift {
      0%, 100% { background: linear-gradient(135deg, var(--primary) 0%, #1a2d5a 100%); }
      50% { background: linear-gradient(135deg, #1a2d5a 0%, var(--primary) 100%); }
    }

    .hero-overlay {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: radial-gradient(circle at 20% 50%, rgba(230, 57, 70, 0.2) 0%, transparent 50%),
                  radial-gradient(circle at 80% 80%, rgba(230, 57, 70, 0.15) 0%, transparent 50%);
      z-index: 2;
    }

    .hero-content {
      position: relative;
      z-index: 3;
      max-width: 800px;
      animation: fadeInUp 0.8s ease 0.2s both;
    }

    @keyframes fadeInUp {
      from {
        opacity: 0;
        transform: translateY(40px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    .hero-content h1 {
      font-size: 64px;
      font-weight: 700;
      margin-bottom: 16px;
      letter-spacing: -0.02em;
      line-height: 1.1;
      animation: fadeInUp 0.8s ease 0.4s both;
    }

    .hero-content p {
      font-size: 18px;
      margin-bottom: 32px;
      opacity: 0.95;
      line-height: 1.6;
      animation: fadeInUp 0.8s ease 0.6s both;
    }

    .hero-buttons {
      display: flex;
      gap: 16px;
      justify-content: center;
      animation: fadeInUp 0.8s ease 0.8s both;
    }

    .btn-primary, .btn-secondary {
      padding: 16px 40px;
      border: none;
      border-radius: 8px;
      font-size: 13px;
      font-weight: 600;
      cursor: pointer;
      transition: var(--transition);
      text-transform: uppercase;
      letter-spacing: 0.05em;
    }

    .btn-primary {
      background: var(--accent);
      color: var(--white);
    }

    .btn-primary:hover {
      background: var(--accent-light);
      transform: translateY(-4px);
      box-shadow: 0 12px 30px rgba(230, 57, 70, 0.4);
    }

    .btn-secondary {
      background: transparent;
      color: var(--white);
      border: 2px solid var(--white);
    }

    .btn-secondary:hover {
      background: var(--white);
      color: var(--primary);
      transform: translateY(-4px);
    }

    /* TRUST INDICATORS */
    .trust-indicators {
      background: var(--white);
      padding: 50px 60px;
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 40px;
      max-width: 1300px;
      margin: -60px auto 0;
      position: relative;
      z-index: 5;
      border-radius: 12px;
      box-shadow: 0 20px 60px rgba(0, 0, 0, 0.12);
    }

    .trust-item {
      text-align: center;
      cursor: pointer;
      transition: var(--transition);
      padding: 20px;
      border-radius: 12px;
    }

    .trust-item:hover {
      background: var(--gray);
      transform: translateY(-4px);
    }

    .trust-icon {
      font-size: 40px;
      margin-bottom: 16px;
      display: block;
      animation: bounce 2s infinite;
    }

    .trust-item:nth-child(2) .trust-icon { animation-delay: 0.2s; }
    .trust-item:nth-child(3) .trust-icon { animation-delay: 0.4s; }
    .trust-item:nth-child(4) .trust-icon { animation-delay: 0.6s; }

    @keyframes bounce {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-8px); }
    }

    .trust-title {
      font-size: 16px;
      font-weight: 600;
      color: var(--primary);
      margin-bottom: 6px;
    }

    .trust-desc {
      font-size: 12px;
      color: var(--gray-4);
    }

    /* SECTIONS */
    .section {
      padding: 100px 60px;
      opacity: 0;
      animation: fadeIn 0.8s ease forwards;
    }

    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }

    .section-header {
      text-align: center;
      margin-bottom: 60px;
    }

    .section-label {
      font-size: 11px;
      text-transform: uppercase;
      letter-spacing: 0.15em;
      color: var(--accent);
      margin-bottom: 12px;
      font-weight: 600;
      animation: fadeInUp 0.6s ease;
    }

    .section-title {
      font-size: 42px;
      font-weight: 700;
      margin-bottom: 12px;
      letter-spacing: -0.02em;
      animation: fadeInUp 0.6s ease 0.1s both;
    }

    .section-title .accent {
      color: var(--accent);
    }

    .section-subtitle {
      font-size: 16px;
      color: var(--gray-4);
      max-width: 600px;
      margin: 0 auto;
      animation: fadeInUp 0.6s ease 0.2s both;
    }

    /* TABS */
    .tabs {
      display: flex;
      gap: 12px;
      justify-content: center;
      margin-bottom: 60px;
      flex-wrap: wrap;
      animation: fadeInUp 0.6s ease 0.3s both;
    }

    .tab-btn {
      padding: 12px 24px;
      background: var(--gray);
      border: 2px solid transparent;
      border-radius: 8px;
      font-size: 12px;
      font-weight: 600;
      cursor: pointer;
      transition: var(--transition);
      text-transform: uppercase;
      letter-spacing: 0.05em;
      color: var(--primary);
    }

    .tab-btn:hover {
      border-color: var(--accent);
      background: var(--white);
    }

    .tab-btn.active {
      background: var(--primary);
      color: var(--white);
      border-color: var(--accent);
    }

    /* DESTINATIONS */
    .destinations {
      background: var(--white);
    }

    .destinations-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
      gap: 24px;
      max-width: 1300px;
      margin: 0 auto;
    }

    .destination-card {
      position: relative;
      height: 280px;
      border-radius: 12px;
      overflow: hidden;
      cursor: pointer;
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
      transition: var(--transition);
      animation: cardSlideIn 0.6s ease forwards;
      opacity: 0;
    }

    .destination-card:nth-child(1) { animation-delay: 0s; }
    .destination-card:nth-child(2) { animation-delay: 0.1s; }
    .destination-card:nth-child(3) { animation-delay: 0.2s; }
    .destination-card:nth-child(4) { animation-delay: 0.3s; }
    .destination-card:nth-child(n+5) { animation-delay: 0.4s; }

    @keyframes cardSlideIn {
      from {
        opacity: 0;
        transform: translateY(20px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    .destination-card:hover {
      transform: translateY(-12px);
      box-shadow: 0 25px 50px rgba(0, 0, 0, 0.2);
    }

    .destination-bg {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: linear-gradient(135deg, var(--primary) 0%, var(--accent) 100%);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 80px;
      z-index: 1;
      transition: var(--transition);
    }

    .destination-card:hover .destination-bg {
      transform: scale(1.1);
    }

    .destination-overlay {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: linear-gradient(180deg, rgba(0,0,0,0) 0%, rgba(0,0,0,0.7) 100%);
      z-index: 2;
      transition: var(--transition);
    }

    .destination-card:hover .destination-overlay {
      background: linear-gradient(180deg, rgba(0,0,0,0.2) 0%, rgba(0,0,0,0.8) 100%);
    }

    .destination-content {
      position: absolute;
      bottom: 0;
      left: 0;
      right: 0;
      padding: 24px;
      color: var(--white);
      z-index: 3;
      transition: var(--transition);
      transform: translateY(10px);
    }

    .destination-card:hover .destination-content {
      transform: translateY(0);
    }

    .destination-content h3 {
      font-size: 18px;
      font-weight: 600;
      margin-bottom: 4px;
    }

    .destination-content p {
      font-size: 13px;
      opacity: 0.9;
    }

    .destination-content .price {
      font-size: 14px;
      font-weight: 700;
      margin-top: 8px;
      color: var(--accent);
    }

    /* FEATURED DEALS */
    .featured-deals {
      background: linear-gradient(135deg, var(--gray) 0%, var(--white) 100%);
    }

    .deals-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
      gap: 32px;
      max-width: 1300px;
      margin: 0 auto;
    }

    .deal-card {
      background: var(--white);
      border-radius: 12px;
      overflow: hidden;
      transition: var(--transition);
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
      animation: cardSlideIn 0.6s ease forwards;
      opacity: 0;
    }

    .deal-card:nth-child(1) { animation-delay: 0s; }
    .deal-card:nth-child(2) { animation-delay: 0.15s; }
    .deal-card:nth-child(3) { animation-delay: 0.3s; }
    .deal-card:nth-child(4) { animation-delay: 0.45s; }
    .deal-card:nth-child(n+5) { animation-delay: 0.6s; }

    .deal-card:hover {
      transform: translateY(-12px);
      box-shadow: 0 25px 50px rgba(0, 0, 0, 0.15);
    }

    .deal-image {
      width: 100%;
      height: 200px;
      background: linear-gradient(135deg, var(--primary) 0%, var(--accent) 100%);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 64px;
      position: relative;
      overflow: hidden;
    }

    .deal-image::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: linear-gradient(45deg, rgba(230, 57, 70, 0.1) 0%, transparent 100%);
      z-index: 1;
    }

    .deal-image > * {
      position: relative;
      z-index: 2;
      transition: var(--transition);
    }

    .deal-card:hover .deal-image > * {
      transform: scale(1.15);
    }

    .deal-content {
      padding: 24px;
    }

    .deal-content h3 {
      font-size: 18px;
      font-weight: 600;
      margin-bottom: 8px;
      color: var(--primary);
      transition: var(--transition);
    }

    .deal-card:hover .deal-content h3 {
      color: var(--accent);
    }

    .deal-content p {
      font-size: 13px;
      color: var(--gray-4);
      line-height: 1.6;
      margin-bottom: 16px;
      min-height: 40px;
    }

    .deal-cta {
      display: inline-block;
      padding: 12px 24px;
      background: linear-gradient(135deg, var(--primary) 0%, var(--accent) 100%);
      color: var(--white);
      border: none;
      border-radius: 6px;
      font-size: 12px;
      font-weight: 600;
      cursor: pointer;
      transition: var(--transition);
      text-transform: uppercase;
      letter-spacing: 0.05em;
    }

    .deal-cta:hover {
      transform: translateX(4px);
      box-shadow: 0 8px 20px rgba(230, 57, 70, 0.3);
    }

    /* CTA BANNER */
    .cta-banner {
      background: linear-gradient(135deg, var(--primary) 0%, var(--accent) 100%);
      color: var(--white);
      padding: 80px 60px;
      text-align: center;
      animation: fadeIn 0.8s ease;
    }

    .cta-banner h2 {
      font-size: 42px;
      font-weight: 700;
      margin-bottom: 16px;
      letter-spacing: -0.02em;
      animation: fadeInUp 0.6s ease;
    }

    .cta-banner p {
      font-size: 16px;
      margin-bottom: 32px;
      opacity: 0.95;
      max-width: 600px;
      margin-left: auto;
      margin-right: auto;
      animation: fadeInUp 0.6s ease 0.1s both;
    }

    .cta-banner button {
      padding: 14px 36px;
      background: var(--white);
      color: var(--primary);
      border: none;
      border-radius: 8px;
      font-size: 13px;
      font-weight: 600;
      cursor: pointer;
      transition: var(--transition);
      text-transform: uppercase;
      letter-spacing: 0.05em;
      animation: fadeInUp 0.6s ease 0.2s both;
    }

    .cta-banner button:hover {
      transform: translateY(-2px);
      box-shadow: 0 12px 30px rgba(0, 0, 0, 0.2);
    }

    /* FOOTER */
    footer {
      background: var(--primary);
      color: var(--white);
      padding: 60px;
      text-align: center;
      font-size: 13px;
      opacity: 0.9;
    }

    /* SEARCH MODAL */
    .search-modal {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.6);
      backdrop-filter: blur(4px);
      z-index: 1000;
      animation: fadeIn 0.3s ease;
    }

    .search-modal.active {
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .search-box {
      background: var(--white);
      width: 90%;
      max-width: 600px;
      padding: 40px;
      border-radius: 12px;
      box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
      animation: scaleIn 0.3s ease;
    }

    @keyframes scaleIn {
      from {
        opacity: 0;
        transform: scale(0.9);
      }
      to {
        opacity: 1;
        transform: scale(1);
      }
    }

    .search-box h2 {
      font-size: 24px;
      margin-bottom: 20px;
      color: var(--primary);
    }

    .search-box input {
      width: 100%;
      padding: 16px;
      font-size: 14px;
      border: 2px solid var(--border);
      border-radius: 8px;
      margin-bottom: 16px;
      font-family: 'Outfit', sans-serif;
      transition: var(--transition);
    }

    .search-box input:focus {
      outline: none;
      border-color: var(--accent);
      box-shadow: 0 0 0 3px rgba(230, 57, 70, 0.1);
    }

    .search-results {
      max-height: 300px;
      overflow-y: auto;
    }

    .search-result-item {
      padding: 12px 16px;
      background: var(--gray);
      margin-bottom: 8px;
      border-radius: 6px;
      cursor: pointer;
      transition: var(--transition);
    }

    .search-result-item:hover {
      background: var(--accent);
      color: var(--white);
    }

    .close-search {
      position: absolute;
      top: 20px;
      right: 20px;
      font-size: 28px;
      cursor: pointer;
      color: var(--primary);
      transition: var(--transition);
    }

    .close-search:hover {
      color: var(--accent);
    }

    /* RESPONSIVE */
    @media (max-width: 1024px) {
      header, .promo-banner, .section, .trust-indicators, .cta-banner {
        padding-left: 30px;
        padding-right: 30px;
      }

      .hero-content h1 { font-size: 42px; }
      .section-title { font-size: 32px; }
      .trust-indicators { grid-template-columns: repeat(2, 1fr); margin: -30px auto 0; }
    }

    @media (max-width: 768px) {
      header { padding: 12px 20px; }
      .nav-center { gap: 20px; display: none; }
      .promo-banner { padding: 10px 20px; font-size: 12px; }
      .hero { height: 70vh; }
      .hero-content h1 { font-size: 28px; }
      .hero-content p { font-size: 14px; }
      .hero-buttons { flex-direction: column; }
      .section, .cta-banner { padding: 40px 20px; }
      .trust-indicators { grid-template-columns: 1fr; margin: -20px 10px 0; padding: 30px 20px; }
      .destinations-grid, .deals-grid { grid-template-columns: 1fr; }
      .tabs { flex-direction: column; }
      .tab-btn { width: 100%; }
    }
  </style>
</head>
<body>
  <!-- HEADER -->
  <header id="header">
    <div class="logo">MER<span class="accent">AIR</span></div>
    <nav class="nav-center">
      <a href="#home">Home</a>
      <a href="#destinations">Destinations</a>
      <a href="#deals">Deals</a>
      <a href="#services">Services</a>
      <a href="#contact">Contact</a>
    </nav>
    <div style="display: flex; gap: 20px; align-items: center;">
      <span class="search-icon" onclick="openSearch()">🔍</span>
      <button class="cta-button">Book Now</button>
    </div>
  </header>

  <!-- SEARCH MODAL -->
  <div class="search-modal" id="searchModal">
    <div class="search-box">
      <span class="close-search" onclick="closeSearch()">&times;</span>
      <h2>Search Destinations</h2>
      <input type="text" id="searchInput" placeholder="Search destinations, packages, deals..." oninput="filterSearch()">
      <div class="search-results" id="searchResults"></div>
    </div>
  </div>

  <!-- PROMO BANNER -->
  <div class="promo-banner">
    🎉 SUMMER SPECIAL - Get up to 30% off + ₹10,000 cashback on international packages!
  </div>

  <!-- HERO SECTION -->
  <section class="hero" id="home">
    <div class="hero-bg"></div>
    <div class="hero-overlay"></div>
    <div class="hero-content">
      <h1>Where Every Journey <span class="accent">Begins</span></h1>
      <p>Crafting unforgettable journeys, just for you. Explore 120+ destinations with expert guides and exclusive deals.</p>
      <div class="hero-buttons">
        <button class="btn-primary" onclick="scrollToSection('deals')">Plan Your Trip</button>
        <button class="btn-secondary" onclick="scrollToSection('destinations')">Explore Packages</button>
      </div>
    </div>
  </section>

  <!-- TRUST INDICATORS -->
  <div class="trust-indicators">
    <div class="trust-item">
      <span class="trust-icon">⭐</span>
      <div class="trust-title">4.8 Rating</div>
      <div class="trust-desc">Trusted by 100K+ travelers</div>
    </div>
    <div class="trust-item">
      <span class="trust-icon">✈️</span>
      <div class="trust-title">Best Price Guarantee</div>
      <div class="trust-desc">Unbeatable deals, no hidden costs</div>
    </div>
    <div class="trust-item">
      <span class="trust-icon">🎯</span>
      <div class="trust-title">190+ Custom Itineraries</div>
      <div class="trust-desc">Tailor-made for you</div>
    </div>
    <div class="trust-item">
      <span class="trust-icon">🛡️</span>
      <div class="trust-title">24/7 Travel Support</div>
      <div class="trust-desc">Help anytime, anywhere</div>
    </div>
  </div>

  <!-- DESTINATIONS SECTION -->
  <section class="section destinations" id="destinations">
    <div class="section-header">
      <div class="section-label">Explore The World</div>
      <h2 class="section-title">Unforgettable <span class="accent">Destinations</span></h2>
      <p class="section-subtitle">Discover extraordinary journeys to the world's most captivating places</p>
    </div>

    <div class="tabs" id="destinationTabs">
      <button class="tab-btn active" onclick="filterDestinations('all')">All Destinations</button>
      <button class="tab-btn" onclick="filterDestinations('asia')">Asia</button>
      <button class="tab-btn" onclick="filterDestinations('europe')">Europe</button>
      <button class="tab-btn" onclick="filterDestinations('africa')">Africa</button>
    </div>

    <div class="destinations-grid" id="destinationsGrid">
      <!-- Populated by JavaScript -->
    </div>
  </section>

  <!-- FEATURED DEALS SECTION -->
  <section class="section featured-deals" id="deals">
    <div class="section-header">
      <div class="section-label">Best Offers</div>
      <h2 class="section-title">Featured <span class="accent">Packages</span></h2>
      <p class="section-subtitle">Handpicked deals for amazing experiences</p>
    </div>

    <div class="tabs">
      <button class="tab-btn active" onclick="filterDeals('all')">All Packages</button>
      <button class="tab-btn" onclick="filterDeals('honeymoon')">Honeymoon</button>
      <button class="tab-btn" onclick="filterDeals('family')">Family</button>
      <button class="tab-btn" onclick="filterDeals('adventure')">Adventure</button>
    </div>

    <div class="deals-grid" id="dealsGrid">
      <!-- Populated by JavaScript -->
    </div>
  </section>

  <!-- CTA BANNER -->
  <section class="cta-banner">
    <h2>Discover Your Perfect Journey</h2>
    <p>Let our expert travel consultants craft a personalized itinerary that matches your dreams, budget, and style.</p>
    <button onclick="alert('Opening booking form...')">Get Your Free Quote</button>
  </section>

  <!-- FOOTER -->
  <footer>
    <p>© 2026 MERAIR Travels and Tours Pvt. Ltd. | Trusted Travel Partner Since 2009</p>
    <p style="margin-top: 12px; opacity: 0.7;">📍 Bengaluru | 📞 +91 80473-55-555 | ✉️ contact@merairtravel.com</p>
  </footer>

  <script>
    // DESTINATIONS DATA
    const destinations = [
      { name: 'Bali, Indonesia', emoji: '🏖️', region: 'asia', price: '₹48,000', description: 'Temples & tropical shores' },
      { name: 'Dubai, UAE', emoji: '🏙️', region: 'asia', price: '₹45,000', description: 'Luxury & desert adventures' },
      { name: 'Maldives', emoji: '🏝️', region: 'asia', price: '₹1,20,000', description: 'Overwater villas & lagoons' },
      { name: 'Singapore', emoji: '🌆', region: 'asia', price: '₹52,000', description: 'Modern city, infinite flavors' },
      { name: 'Switzerland', emoji: '🏔️', region: 'europe', price: '₹1,65,000', description: 'Alpine peaks & villages' },
      { name: 'Paris, France', emoji: '🗿', region: 'europe', price: '₹85,000', description: 'Romance & beauty' },
      { name: 'Italy', emoji: '🏛️', region: 'europe', price: '₹90,000', description: 'Art & history' },
      { name: 'South Africa', emoji: '🦁', region: 'africa', price: '₹95,000', description: 'Wildlife safari' },
    ];

    // DEALS DATA
    const deals = [
      { name: 'South Africa Safari', emoji: '🦁', category: 'adventure', description: 'Roar into adventure with wildlife safari' },
      { name: 'Australia Holiday', emoji: '🦘', category: 'adventure', description: 'Nature, culture & adventure' },
      { name: 'Maldives Honeymoon', emoji: '💑', category: 'honeymoon', description: 'Romantic paradise getaway' },
      { name: 'Japan Experience', emoji: '🏯', category: 'adventure', description: 'Iconic cities & scenic wonders' },
      { name: 'Europe Grand Tour', emoji: '🇪🇺', category: 'family', description: 'Cultural journey across Europe' },
      { name: 'Thailand Family Trip', emoji: '👨‍👩‍👧‍👦', category: 'family', description: 'Perfect family vacation' },
    ];

    // RENDER DESTINATIONS
    function renderDestinations(filter = 'all') {
      const grid = document.getElementById('destinationsGrid');
      grid.innerHTML = '';
      
      const filtered = filter === 'all' ? destinations : destinations.filter(d => d.region === filter);
      
      filtered.forEach((dest, index) => {
        const card = document.createElement('div');
        card.className = 'destination-card';
        card.innerHTML = `
          <div class="destination-bg">${dest.emoji}</div>
          <div class="destination-overlay"></div>
          <div class="destination-content">
            <h3>${dest.name}</h3>
            <p>${dest.description}</p>
            <div class="price">${dest.price}</div>
          </div>
        `;
        card.style.animationDelay = (index * 0.1) + 's';
        card.addEventListener('click', () => {
          alert(`Booking ${dest.name}...\nPrice: ${dest.price}`);
        });
        grid.appendChild(card);
      });
    }

    // RENDER DEALS
    function renderDeals(filter = 'all') {
      const grid = document.getElementById('dealsGrid');
      grid.innerHTML = '';
      
      const filtered = filter === 'all' ? deals : deals.filter(d => d.category === filter);
      
      filtered.forEach((deal, index) => {
        const card = document.createElement('div');
        card.className = 'deal-card';
        card.innerHTML = `
          <div class="deal-image">${deal.emoji}</div>
          <div class="deal-content">
            <h3>${deal.name}</h3>
            <p>${deal.description}</p>
            <button class="deal-cta" onclick="alert('Exploring ${deal.name}...')">Explore Now</button>
          </div>
        `;
        card.style.animationDelay = (index * 0.15) + 's';
        grid.appendChild(card);
      });
    }

    // FILTER DESTINATIONS
    function filterDestinations(category) {
      document.querySelectorAll('#destinationTabs .tab-btn').forEach(btn => btn.classList.remove('active'));
      event.target.classList.add('active');
      renderDestinations(category);
    }

    // FILTER DEALS
    function filterDeals(category) {
      document.querySelectorAll('.featured-deals .tabs .tab-btn').forEach(btn => btn.classList.remove('active'));
      event.target.classList.add('active');
      renderDeals(category);
    }

    // SEARCH FUNCTIONALITY
    function openSearch() {
      document.getElementById('searchModal').classList.add('active');
      document.getElementById('searchInput').focus();
    }

    function closeSearch() {
      document.getElementById('searchModal').classList.remove('active');
    }

    function filterSearch() {
      const input = document.getElementById('searchInput').value.toLowerCase();
      const allItems = [...destinations, ...deals];
      const results = allItems.filter(item => item.name.toLowerCase().includes(input));
      
      const resultsDiv = document.getElementById('searchResults');
      resultsDiv.innerHTML = '';
      
      results.forEach(item => {
        const result = document.createElement('div');
        result.className = 'search-result-item';
        result.innerHTML = `${item.emoji} ${item.name}`;
        result.onclick = () => {
          closeSearch();
          alert(`Selected: ${item.name}`);
        };
        resultsDiv.appendChild(result);
      });
    }

    // SCROLL TO SECTION
    function scrollToSection(id) {
      document.getElementById(id).scrollIntoView({ behavior: 'smooth' });
    }

    // HEADER SCROLL EFFECT
    window.addEventListener('scroll', () => {
      const header = document.getElementById('header');
      if (window.scrollY > 50) {
        header.classList.add('scrolled');
      } else {
        header.classList.remove('scrolled');
      }
    });

    // CLOSE SEARCH ON ESCAPE
    document.addEventListener('keydown', (e) => {
      if (e.key === 'Escape') closeSearch();
    });

    // INITIAL RENDER
    renderDestinations();
    renderDeals();
  </script>
</body>
</html>

