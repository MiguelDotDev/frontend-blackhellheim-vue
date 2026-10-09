<script setup lang="ts">
interface Product {
  id: number
  name: string
  category: string
  price: number
  size: string
  accent: string
  symbol: string
}

const products: Product[] = [
  {
    id: 1,
    name: 'Hijo del Inframundo',
    category: 'Black Metal',
    price: 649,
    size: 'S · M · L · XL',
    accent: '#a30018',
    symbol: '☠'
  },
  {
    id: 2,
    name: 'Calavera Azteca',
    category: 'Mexican Metal',
    price: 699,
    size: 'S · M · L · XL',
    accent: '#7f0014',
    symbol: '𓂀'
  },
  {
    id: 3,
    name: 'Eternal Darkness',
    category: 'Dark Rock',
    price: 599,
    size: 'S · M · L · XL',
    accent: '#c4152f',
    symbol: '✦'
  },
  {
    id: 4,
    name: 'Tláloc',
    category: 'Mexican Rock',
    price: 679,
    size: 'S · M · L · XL',
    accent: '#930019',
    symbol: '◈'
  },
  {
    id: 5,
    name: 'Blood Ritual',
    category: 'Death Metal',
    price: 729,
    size: 'S · M · L · XL',
    accent: '#b10b23',
    symbol: '†'
  },
  {
    id: 6,
    name: 'Mictlán',
    category: 'Black Metal',
    price: 699,
    size: 'S · M · L · XL',
    accent: '#65000e',
    symbol: '𓆩'
  }
]

const categories = [
  'Black Metal',
  'Death Metal',
  'Rock',
  'Mexican Metal'
]
</script>

<template>
  <div class="app">
    <!-- =========================
         NAVBAR
    ========================== -->
    <header class="navbar">
      <div class="nav-container">
        <a href="#" class="brand">
          <span class="brand-mark">B</span>

          <div class="brand-text">
            <span class="brand-name">BLACKHELLHEIM</span>
            <span class="brand-subtitle">WEAR THE DARKNESS</span>
          </div>
        </a>

        <nav class="nav-links">
          <a href="#" class="active">Inicio</a>
          <a href="#catalogo">Catálogo</a>
          <a href="#categorias">Categorías</a>
          <a href="#nosotros">Nosotros</a>
        </nav>

        <div class="nav-actions">
          <button class="icon-button" aria-label="Buscar">
            <svg viewBox="0 0 24 24">
              <circle cx="11" cy="11" r="7"></circle>
              <path d="m20 20-4-4"></path>
            </svg>
          </button>

          <button class="icon-button" aria-label="Cuenta">
            <svg viewBox="0 0 24 24">
              <circle cx="12" cy="8" r="4"></circle>
              <path d="M4 21c0-4.2 3.6-7 8-7s8 2.8 8 7"></path>
            </svg>
          </button>

          <button class="cart-button" aria-label="Carrito">
            <svg viewBox="0 0 24 24">
              <path d="M3 4h2l2.2 11.2a2 2 0 0 0 2 1.6h7.6a2 2 0 0 0 1.9-1.4L21 8H6"></path>
              <circle cx="10" cy="20" r="1"></circle>
              <circle cx="18" cy="20" r="1"></circle>
            </svg>

            <span class="cart-count">0</span>
          </button>
        </div>
      </div>
    </header>

    <main>
      <!-- =========================
           HERO
      ========================== -->
      <section class="hero">
        <div class="hero-overlay"></div>

        <div class="hero-container">
          <div class="hero-content">
            <span class="eyebrow">
              BLACKHELLHEIM / EST. 2026
            </span>

            <h1>
              VISTE
              <span>EL LADO</span>
              <strong>OSCURO.</strong>
            </h1>

            <p>
              Diseños originales inspirados en el Rock, el Metal
              y la identidad mexicana.
            </p>

            <div class="hero-actions">
              <a href="#catalogo" class="primary-button">
                Explorar catálogo
                <span>→</span>
              </a>

              <a href="#categorias" class="secondary-button">
                Ver categorías
              </a>
            </div>
          </div>

          <div class="hero-symbol">
            <div class="symbol-ring">
              <span>☠</span>
            </div>

            <div class="symbol-text">
              <span>BLACK</span>
              <span>HELL</span>
              <span>HEIM</span>
            </div>
          </div>
        </div>

        <div class="hero-bottom">
          <span>ORIGINAL DESIGNS</span>
          <span></span>
          <span>DROPSHIPPING</span>
          <span></span>
          <span>MADE FOR THE DARK</span>
        </div>
      </section>

      <!-- =========================
           CATEGORY STRIP
      ========================== -->
      <section id="categorias" class="category-section">
        <div class="section-heading">
          <div>
            <span class="section-kicker">EXPLORE</span>
            <h2>Encuentra tu <span>estilo.</span></h2>
          </div>

          <p>
            Una colección construida para quienes
            no buscan vestir como todos.
          </p>
        </div>

        <div class="category-grid">
          <a
            v-for="category in categories"
            :key="category"
            href="#catalogo"
            class="category-card"
          >
            <span class="category-number">
              0{{ categories.indexOf(category) + 1 }}
            </span>

            <h3>{{ category }}</h3>

            <span class="category-arrow">↗</span>
          </a>
        </div>
      </section>

      <!-- =========================
           CATALOG
      ========================== -->
      <section id="catalogo" class="catalog-section">
        <div class="catalog-heading">
          <div>
            <span class="section-kicker">BLACKHELLHEIM COLLECTION</span>
            <h2>Productos <span>destacados.</span></h2>
          </div>

          <a href="#" class="view-all">
            Ver catálogo completo
            <span>→</span>
          </a>
        </div>

        <div class="product-grid">
          <article
            v-for="product in products"
            :key="product.id"
            class="product-card"
          >
            <div class="product-image">
              <div
                class="product-glow"
                :style="{ background: product.accent }"
              ></div>

              <div
                class="shirt"
                :style="{ '--shirt-accent': product.accent }"
              >
                <div class="shirt-neck"></div>

                <div class="shirt-design">
                  <span class="shirt-symbol">
                    {{ product.symbol }}
                  </span>

                  <span class="shirt-title">
                    BLACKHELLHEIM
                  </span>

                  <span class="shirt-line"></span>

                  <span class="shirt-small">
                    EST. 2026
                  </span>
                </div>
              </div>

              <button class="quick-add">
                + Agregar
              </button>

              <span class="product-badge">
                NEW
              </span>
            </div>

            <div class="product-info">
              <div class="product-category">
                {{ product.category }}
              </div>

              <h3>{{ product.name }}</h3>

              <div class="product-bottom">
                <div>
                  <strong>${{ product.price }}</strong>
                  <span> MXN</span>
                </div>

                <span class="sizes">
                  {{ product.size }}
                </span>
              </div>
            </div>
          </article>
        </div>
      </section>

      <!-- =========================
           BRAND BANNER
      ========================== -->
      <section id="nosotros" class="brand-banner">
        <div class="brand-banner-pattern"></div>

        <div class="brand-banner-content">
          <span class="section-kicker">BLACKHELLHEIM</span>

          <h2>
            NO SE TRATA DE
            <span>SEGUIR.</span>
            <br />
            SE TRATA DE
            <strong>PERTENECER.</strong>
          </h2>

          <p>
            Una identidad nacida entre guitarras, sombras,
            símbolos ancestrales y una cultura que nunca desaparece.
          </p>
        </div>

        <div class="banner-mark">
          BHH
        </div>
      </section>
    </main>

    <!-- =========================
         FOOTER
    ========================== -->
    <footer class="footer">
      <div class="footer-container">
        <div class="footer-brand">
          <span class="brand-name">BLACKHELLHEIM</span>

          <p>
            Rock · Metal · México
          </p>
        </div>

        <div class="footer-links">
          <a href="#">Catálogo</a>
          <a href="#">Términos</a>
          <a href="#">Privacidad</a>
          <a href="#">Contacto</a>
        </div>

        <div class="footer-copy">
          © 2026 BlackHellHeim
        </div>
      </div>
    </footer>
  </div>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&family=Unbounded:wght@400;500;600;700;800&display=swap');

:root {
  font-family: 'Inter', sans-serif;

  color: #f4f4f4;
  background: #080808;

  font-synthesis: none;
  text-rendering: optimizeLegibility;
  -webkit-font-smoothing: antialiased;
}

* {
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
}

body {
  margin: 0;
  min-width: 320px;
  background:
    radial-gradient(
      circle at 80% 0%,
      rgba(130, 0, 20, 0.12),
      transparent 30%
    ),
    #080808;
}

button,
a {
  font: inherit;
}

button {
  cursor: pointer;
}

a {
  color: inherit;
  text-decoration: none;
}

.app {
  min-height: 100vh;
  overflow: hidden;
}

/* =========================
   NAVBAR
========================= */

.navbar {
  position: relative;
  z-index: 20;

  border-bottom: 1px solid rgba(255, 255, 255, 0.06);

  background: rgba(7, 7, 7, 0.88);

  backdrop-filter: blur(16px);
}

.nav-container {
  max-width: 1380px;

  margin: 0 auto;

  min-height: 82px;

  padding: 0 40px;

  display: flex;

  align-items: center;

  justify-content: space-between;

  gap: 30px;
}

.brand {
  display: flex;

  align-items: center;

  gap: 12px;
}

.brand-mark {
  width: 42px;
  height: 42px;

  display: grid;
  place-items: center;

  border: 1px solid #970016;

  background:
    linear-gradient(
      145deg,
      #b6001d,
      #42000a
    );

  font-family: 'Unbounded', sans-serif;
  font-size: 17px;
  font-weight: 800;

  transform: skew(-8deg);

  box-shadow:
    0 0 25px rgba(173, 0, 28, 0.22);
}

.brand-text {
  display: flex;
  flex-direction: column;

  gap: 2px;
}

.brand-name {
  font-family: 'Unbounded', sans-serif;
  font-size: 13px;
  font-weight: 800;
  letter-spacing: 0.08em;
}

.brand-subtitle {
  color: #767676;

  font-size: 8px;
  letter-spacing: 0.25em;
}

.nav-links {
  display: flex;

  align-items: center;

  gap: 34px;
}

.nav-links a {
  position: relative;

  color: #878787;

  font-size: 13px;
  font-weight: 600;

  transition: color 0.2s ease;
}

.nav-links a:hover,
.nav-links a.active {
  color: #fff;
}

.nav-links a.active::after {
  content: '';

  position: absolute;

  left: 0;
  right: 0;
  bottom: -11px;

  height: 2px;

  background: #ad001e;

  box-shadow: 0 0 10px rgba(190, 0, 32, 0.6);
}

.nav-actions {
  display: flex;

  align-items: center;

  gap: 8px;
}

.icon-button,
.cart-button {
  position: relative;

  width: 40px;
  height: 40px;

  border: 1px solid rgba(255, 255, 255, 0.08);

  background: rgba(255, 255, 255, 0.025);

  color: #aaa;

  display: grid;
  place-items: center;

  transition:
    border-color 0.2s ease,
    color 0.2s ease,
    background 0.2s ease;
}

.icon-button:hover,
.cart-button:hover {
  color: #fff;

  border-color: rgba(180, 0, 30, 0.65);

  background: rgba(160, 0, 25, 0.1);
}

.icon-button svg,
.cart-button svg {
  width: 17px;
  height: 17px;

  fill: none;

  stroke: currentColor;

  stroke-width: 1.7;

  stroke-linecap: round;

  stroke-linejoin: round;
}

.cart-count {
  position: absolute;

  top: -5px;
  right: -5px;

  width: 16px;
  height: 16px;

  display: grid;
  place-items: center;

  border-radius: 50%;

  background: #b00020;

  color: white;

  font-size: 8px;
  font-weight: 800;
}

/* =========================
   HERO
========================= */

.hero {
  position: relative;

  min-height: 680px;

  display: flex;

  align-items: center;

  overflow: hidden;

  border-bottom: 1px solid rgba(255, 255, 255, 0.06);

  background:
    radial-gradient(
      circle at 80% 48%,
      rgba(125, 0, 20, 0.25),
      transparent 28%
    ),
    linear-gradient(
      110deg,
      #080808 10%,
      #11090a 52%,
      #080808 100%
    );
}

.hero::before {
  content: '';

  position: absolute;

  inset: 0;

  background-image:
    linear-gradient(
      rgba(255, 255, 255, 0.025) 1px,
      transparent 1px
    ),
    linear-gradient(
      90deg,
      rgba(255, 255, 255, 0.025) 1px,
      transparent 1px
    );

  background-size: 60px 60px;

  mask-image:
    linear-gradient(
      to bottom,
      rgba(0, 0, 0, 0.8),
      transparent
    );
}

.hero-overlay {
  position: absolute;

  inset: 0;

  background:
    linear-gradient(
      90deg,
      #080808 0%,
      rgba(8, 8, 8, 0.82) 38%,
      rgba(8, 8, 8, 0.1) 100%
    );
}

.hero-container {
  position: relative;
  z-index: 2;

  width: 100%;
  max-width: 1380px;

  margin: 0 auto;

  padding: 90px 40px;

  display: flex;

  align-items: center;

  justify-content: space-between;
}

.hero-content {
  max-width: 720px;
}

.eyebrow,
.section-kicker {
  display: block;

  color: #a9001d;

  font-size: 10px;

  font-weight: 800;

  letter-spacing: 0.28em;
}

.hero h1 {
  margin: 22px 0;

  font-family: 'Unbounded', sans-serif;

  font-size: clamp(48px, 7vw, 96px);

  line-height: 0.96;

  letter-spacing: -0.065em;

  font-weight: 800;
}

.hero h1 span {
  display: block;

  color: transparent;

  -webkit-text-stroke: 1px #e9e9e9;
}

.hero h1 strong {
  display: block;

  color: #a9001e;

  font-weight: 800;

  text-shadow:
    0 0 50px rgba(169, 0, 30, 0.25);
}

.hero-content > p {
  max-width: 560px;

  margin: 0;

  color: #999;

  font-size: 16px;

  line-height: 1.7;
}

.hero-actions {
  margin-top: 34px;

  display: flex;

  align-items: center;

  gap: 12px;
}

.primary-button,
.secondary-button {
  min-height: 50px;

  padding: 0 22px;

  display: inline-flex;

  align-items: center;

  justify-content: center;

  gap: 16px;

  font-size: 12px;

  font-weight: 800;

  letter-spacing: 0.08em;

  text-transform: uppercase;
}

.primary-button {
  background: #a9001e;

  color: #fff;

  border: 1px solid #c00021;

  box-shadow:
    0 10px 30px rgba(155, 0, 25, 0.25);

  transition:
    transform 0.2s ease,
    background 0.2s ease;
}

.primary-button:hover {
  background: #c00024;

  transform: translateY(-2px);
}

.secondary-button {
  border: 1px solid rgba(255, 255, 255, 0.12);

  color: #aaa;

  background: rgba(255, 255, 255, 0.025);
}

.secondary-button:hover {
  border-color: rgba(255, 255, 255, 0.25);

  color: #fff;
}

.hero-symbol {
  display: flex;

  align-items: center;

  gap: 32px;

  transform: rotate(-5deg);

  opacity: 0.85;
}

.symbol-ring {
  width: 280px;
  height: 280px;

  display: grid;
  place-items: center;

  border: 1px solid rgba(174, 0, 29, 0.45);

  border-radius: 50%;

  box-shadow:
    inset 0 0 80px rgba(160, 0, 20, 0.05),
    0 0 70px rgba(145, 0, 20, 0.1);
}

.symbol-ring::before {
  content: '';

  position: absolute;

  width: 220px;
  height: 220px;

  border: 1px dashed rgba(184, 0, 30, 0.3);

  border-radius: 50%;
}

.symbol-ring span {
  color: #a9001e;

  font-size: 120px;

  filter:
    drop-shadow(
      0 0 20px rgba(160, 0, 25, 0.3)
    );
}

.symbol-text {
  display: flex;

  flex-direction: column;

  color: rgba(255, 255, 255, 0.12);

  font-family: 'Unbounded', sans-serif;

  font-size: 26px;

  font-weight: 800;

  line-height: 1.1;
}

.hero-bottom {
  position: absolute;

  z-index: 3;

  bottom: 0;

  left: 0;
  right: 0;

  min-height: 54px;

  display: flex;

  align-items: center;

  justify-content: center;

  gap: 20px;

  border-top: 1px solid rgba(255, 255, 255, 0.06);

  background: rgba(0, 0, 0, 0.25);

  color: #555;

  font-size: 8px;

  font-weight: 700;

  letter-spacing: 0.2em;
}

.hero-bottom span:nth-child(even) {
  width: 4px;
  height: 4px;

  border-radius: 50%;

  background: #9f001b;
}

/* =========================
   CATEGORIES
========================= */

.category-section,
.catalog-section {
  max-width: 1380px;

  margin: 0 auto;

  padding: 100px 40px;
}

.section-heading,
.catalog-heading {
  display: flex;

  justify-content: space-between;

  align-items: end;

  gap: 40px;

  margin-bottom: 42px;
}

.section-heading h2,
.catalog-heading h2 {
  margin: 10px 0 0;

  font-family: 'Unbounded', sans-serif;

  font-size: clamp(25px, 4vw, 42px);

  letter-spacing: -0.04em;
}

.section-heading h2 span,
.catalog-heading h2 span {
  color: #a9001e;
}

.section-heading p {
  max-width: 340px;

  margin: 0;

  color: #777;

  font-size: 13px;

  line-height: 1.7;
}

.category-grid {
  display: grid;

  grid-template-columns:
    repeat(4, minmax(0, 1fr));

  gap: 1px;

  background: rgba(255, 255, 255, 0.08);
}

.category-card {
  position: relative;

  min-height: 170px;

  padding: 25px;

  display: flex;

  flex-direction: column;

  justify-content: space-between;

  overflow: hidden;

  background: #0d0d0d;

  transition:
    background 0.25s ease,
    transform 0.25s ease;
}

.category-card::before {
  content: '';

  position: absolute;

  left: 0;
  bottom: 0;

  width: 100%;

  height: 2px;

  background: #a9001e;

  transform: scaleX(0);

  transform-origin: left;

  transition: transform 0.25s ease;
}

.category-card:hover {
  background: #131013;
}

.category-card:hover::before {
  transform: scaleX(1);
}

.category-number {
  color: #484848;

  font-family: 'Unbounded', sans-serif;

  font-size: 10px;
}

.category-card h3 {
  margin: 0;

  font-family: 'Unbounded', sans-serif;

  font-size: 13px;

  letter-spacing: -0.01em;
}

.category-arrow {
  align-self: end;

  color: #a9001e;

  font-size: 20px;
}

/* =========================
   CATALOG
========================= */

.catalog-section {
  padding-top: 20px;
}

.view-all {
  color: #999;

  font-size: 11px;

  font-weight: 700;

  letter-spacing: 0.08em;

  text-transform: uppercase;
}

.view-all:hover {
  color: #fff;
}

.view-all span {
  margin-left: 8px;

  color: #a9001e;
}

.product-grid {
  display: grid;

  grid-template-columns:
    repeat(3, minmax(0, 1fr));

  gap: 20px;
}

.product-card {
  min-width: 0;

  background:
    linear-gradient(
      180deg,
      #101010,
      #0b0b0b
    );

  border: 1px solid rgba(255, 255, 255, 0.055);

  transition:
    transform 0.25s ease,
    border-color 0.25s ease;
}

.product-card:hover {
  transform: translateY(-5px);

  border-color: rgba(165, 0, 28, 0.35);
}

.product-image {
  position: relative;

  min-height: 430px;

  display: grid;

  place-items: center;

  overflow: hidden;

  background:
    radial-gradient(
      circle at center,
      rgba(118, 0, 20, 0.17),
      transparent 38%
    ),
    #111;
}

.product-glow {
  position: absolute;

  width: 170px;
  height: 170px;

  border-radius: 50%;

  filter: blur(80px);

  opacity: 0.2;
}

.product-badge {
  position: absolute;

  left: 15px;
  top: 15px;

  padding: 6px 9px;

  background: #a7001c;

  color: white;

  font-size: 8px;

  font-weight: 900;

  letter-spacing: 0.15em;
}

.quick-add {
  position: absolute;

  right: 15px;
  bottom: 15px;

  padding: 9px 14px;

  border: 1px solid rgba(255, 255, 255, 0.14);

  color: #eee;

  background: rgba(8, 8, 8, 0.78);

  backdrop-filter: blur(8px);

  font-size: 9px;

  font-weight: 800;

  letter-spacing: 0.08em;

  text-transform: uppercase;

  opacity: 0;

  transform: translateY(8px);

  transition:
    opacity 0.2s ease,
    transform 0.2s ease;
}

.product-card:hover .quick-add {
  opacity: 1;

  transform: translateY(0);
}

.shirt {
  --shirt-accent: #a9001e;

  position: relative;

  width: 190px;
  height: 235px;

  background:
    linear-gradient(
      130deg,
      #191919,
      #050505
    );

  clip-path: polygon(
    25% 0%,
    39% 10%,
    61% 10%,
    75% 0%,
    100% 18%,
    83% 43%,
    75% 34%,
    75% 100%,
    25% 100%,
    25% 34%,
    17% 43%,
    0% 18%
  );

  filter:
    drop-shadow(
      0 25px 30px rgba(0, 0, 0, 0.8)
    );
}

.shirt::after {
  content: '';

  position: absolute;

  inset: 8px;

  opacity: 0.22;

  background:
    repeating-linear-gradient(
      125deg,
      transparent 0,
      transparent 8px,
      rgba(255, 255, 255, 0.03) 9px
    );

  pointer-events: none;
}

.shirt-neck {
  position: absolute;

  left: 50%;
  top: 7px;

  width: 43px;
  height: 20px;

  transform: translateX(-50%);

  border-radius: 0 0 25px 25px;

  background: #080808;

  border-bottom: 2px solid #242424;
}

.shirt-design {
  position: absolute;

  left: 50%;
  top: 61px;

  transform: translateX(-50%);

  width: 115px;

  display: flex;

  flex-direction: column;

  align-items: center;

  gap: 7px;

  text-align: center;
}

.shirt-symbol {
  color: var(--shirt-accent);

  font-size: 42px;

  line-height: 1;

  text-shadow:
    0 0 15px
      color-mix(
        in srgb,
        var(--shirt-accent),
        transparent 40%
      );
}

.shirt-title {
  font-family: 'Unbounded', sans-serif;

  font-size: 7px;

  font-weight: 800;

  letter-spacing: 0.12em;
}

.shirt-line {
  width: 55px;
  height: 1px;

  background: var(--shirt-accent);
}

.shirt-small {
  color: #696969;

  font-size: 6px;

  letter-spacing: 0.22em;
}

.product-info {
  padding: 22px;
}

.product-category {
  margin-bottom: 7px;

  color: #8f0019;

  font-size: 9px;

  font-weight: 800;

  letter-spacing: 0.12em;

  text-transform: uppercase;
}

.product-info h3 {
  margin: 0;

  font-size: 17px;

  font-weight: 700;
}

.product-bottom {
  margin-top: 18px;

  display: flex;

  align-items: end;

  justify-content: space-between;

  gap: 15px;
}

.product-bottom strong {
  font-size: 19px;
}

.product-bottom span {
  color: #777;

  font-size: 9px;
}

.sizes {
  white-space: nowrap;
}

/* =========================
   BRAND BANNER
========================= */

.brand-banner {
  position: relative;

  min-height: 480px;

  padding: 90px 40px;

  display: flex;

  align-items: center;

  overflow: hidden;

  background:
    linear-gradient(
      110deg,
      #1a080b,
      #090909 55%,
      #110607
    );

  border-top: 1px solid rgba(255, 255, 255, 0.06);

  border-bottom: 1px solid rgba(255, 255, 255, 0.06);
}

.brand-banner-pattern {
  position: absolute;

  inset: 0;

  opacity: 0.16;

  background:
    repeating-linear-gradient(
      -45deg,
      transparent 0,
      transparent 18px,
      rgba(169, 0, 30, 0.17) 19px,
      transparent 20px
    );
}

.brand-banner-content {
  position: relative;

  z-index: 2;

  max-width: 1380px;

  width: 100%;

  margin: auto;
}

.brand-banner h2 {
  max-width: 850px;

  margin: 18px 0;

  font-family: 'Unbounded', sans-serif;

  font-size: clamp(28px, 5vw, 59px);

  line-height: 1.08;

  letter-spacing: -0.05em;
}

.brand-banner h2 span {
  color: transparent;

  -webkit-text-stroke: 1px #a9001e;
}

.brand-banner h2 strong {
  color: #a9001e;
}

.brand-banner p {
  max-width: 560px;

  color: #777;

  font-size: 14px;

  line-height: 1.8;
}

.banner-mark {
  position: absolute;

  right: 5%;

  bottom: -60px;

  color: rgba(173, 0, 28, 0.05);

  font-family: 'Unbounded', sans-serif;

  font-size: clamp(120px, 22vw, 300px);

  font-weight: 900;

  letter-spacing: -0.12em;
}

/* =========================
   FOOTER
========================= */

.footer {
  border-top: 1px solid rgba(255, 255, 255, 0.06);

  background: #050505;
}

.footer-container {
  max-width: 1380px;

  margin: 0 auto;

  padding: 45px 40px;

  display: flex;

  align-items: center;

  justify-content: space-between;

  gap: 30px;
}

.footer-brand {
  display: flex;

  flex-direction: column;

  gap: 7px;
}

.footer-brand .brand-name {
  font-size: 11px;
}

.footer-brand p {
  margin: 0;

  color: #555;

  font-size: 10px;

  letter-spacing: 0.12em;
}

.footer-links {
  display: flex;

  gap: 25px;
}

.footer-links a {
  color: #666;

  font-size: 10px;

  font-weight: 600;
}

.footer-links a:hover {
  color: #fff;
}

.footer-copy {
  color: #444;

  font-size: 9px;
}

/* =========================
   RESPONSIVE
========================= */

@media (max-width: 1000px) {
  .nav-links {
    display: none;
  }

  .hero-symbol {
    opacity: 0.25;

    position: absolute;

    right: -80px;
  }

  .category-grid {
    grid-template-columns:
      repeat(2, minmax(0, 1fr));
  }

  .product-grid {
    grid-template-columns:
      repeat(2, minmax(0, 1fr));
  }
}

@media (max-width: 700px) {
  .nav-container,
  .hero-container,
  .category-section,
  .catalog-section {
    padding-left: 20px;
    padding-right: 20px;
  }

  .navbar {
    position: sticky;
    top: 0;
  }

  .hero {
    min-height: 620px;
  }

  .hero-container {
    padding-top: 70px;
    padding-bottom: 70px;
  }

  .hero-actions {
    flex-direction: column;

    align-items: stretch;
  }

  .primary-button,
  .secondary-button {
    width: 100%;
  }

  .hero-bottom {
    gap: 10px;

    padding: 0 15px;

    overflow: hidden;

    white-space: nowrap;
  }

  .category-section,
  .catalog-section {
    padding-top: 65px;
    padding-bottom: 65px;
  }

  .section-heading,
  .catalog-heading {
    flex-direction: column;

    align-items: start;
  }

  .category-grid {
    grid-template-columns: 1fr;
  }

  .product-grid {
    grid-template-columns: 1fr;
  }

  .product-image {
    min-height: 390px;
  }

  .quick-add {
    opacity: 1;

    transform: none;
  }

  .brand-banner {
    padding: 70px 20px;
  }

  .footer-container {
    flex-direction: column;

    align-items: start;

    padding: 35px 20px;
  }

  .footer-links {
    flex-wrap: wrap;
  }
}
</style>