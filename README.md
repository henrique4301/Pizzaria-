# Pizzaria-
Pizzaria 
/* ===========================
   FORNO BELLO – style.css
   Paleta: Vermelho tomate, verde manjericão e creme de massa
=========================== */

/* ── VARIABLES ── */
:root {
  --red-light:   #fde3df;
  --red-mid:     #ef6b5f;
  --red-dark:    #c62828;
  --green-light: #e6f4e8;
  --green-mid:   #81c784;
  --green-dark:  #2e7d32;
  --gold:        #f4b942;
  --cream:       #fff7ea;
  --text-dark:   #2b1810;
  --text-mid:    #6b4a3a;
  --text-light:  #a58b7c;
  --white:       #ffffff;
  --shadow:      0 8px 32px rgba(198, 40, 40, 0.10);
  --radius:      20px;
  --radius-sm:   12px;
  --font-title:  'Alfa Slab One', serif;
  --font-body:   'Nunito', sans-serif;
}

/* ── RESET ── */
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

html { scroll-behavior: smooth; }

body {
  font-family: var(--font-body);
  background: var(--cream);
  color: var(--text-dark);
  min-height: 100vh;
  overflow-x: hidden;
}

/* ── HEADER ── */
.header {
  background: linear-gradient(135deg, #ffd9a0 0%, #ffeccc 55%, #fde3df 100%);
  text-align: center;
  padding: 3rem 1rem 0;
  position: relative;
  overflow: hidden;
}

.header::before {
  content: '';
  position: absolute;
  top: -60px; left: -60px;
  width: 220px; height: 220px;
  background: radial-gradient(circle, #ef6b5f 0%, transparent 70%);
  opacity: 0.4;
  pointer-events: none;
}

.header::after {
  content: '';
  position: absolute;
  bottom: 40px; right: -40px;
  width: 180px; height: 180px;
  background: radial-gradient(circle, #81c784 0%, transparent 70%);
  opacity: 0.5;
  pointer-events: none;
}

.header-inner {
  position: relative;
  z-index: 1;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.75rem;
  padding-bottom: 1.5rem;
}

.logo-wrap {
  display: flex;
  align-items: center;
  gap: 1rem;
  animation: floatIn 0.8s ease both;
}

.logo-icon {
  font-size: 5rem;
  filter: drop-shadow(0 4px 12px rgba(198,40,40,0.4));
  animation: bounce 2.5s infinite ease-in-out;
}

.logo-text {
  display: flex;
  flex-direction: column;
  text-align: left;
}

.logo-name {
  font-family: var(--font-title);
  font-size: clamp(2.5rem, 6vw, 4.5rem);
  color: var(--red-dark);
  line-height: 1;
  text-shadow: 2px 4px 12px rgba(198,40,40,0.2);
  letter-spacing: 1px;
}

.logo-sub {
  font-size: 1rem;
  color: var(--green-dark);
  font-weight: 700;
  letter-spacing: 2px;
  text-transform: uppercase;
}

.header-slogan {
  font-size: 1.15rem;
  color: var(--text-mid);
  font-weight: 600;
  animation: floatIn 1s 0.3s ease both;
}

.header-wave svg {
  display: block;
  width: 100%;
}

/* ── HERO ── */
.hero {
  position: relative;
  height: clamp(380px, 60vh, 580px);
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
}

.hero-img-wrap {
  position: absolute;
  inset: 0;
}

.hero-img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center 40%;
  display: block;
  transition: transform 8s ease;
}

.hero:hover .hero-img {
  transform: scale(1.04);
}

.hero-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(
    135deg,
    rgba(150, 25, 20, 0.70) 0%,
    rgba(46, 125, 50, 0.45) 100%
  );
}

.hero-content {
  position: relative;
  z-index: 2;
  text-align: center;
  color: var(--white);
  padding: 2rem 1.5rem;
  max-width: 700px;
  animation: floatIn 0.9s ease both;
}

.hero-tag {
  font-size: 1rem;
  font-weight: 700;
  letter-spacing: 2px;
  text-transform: uppercase;
  opacity: 0.9;
  margin-bottom: 0.4rem;
}

.hero-title {
  font-family: var(--font-title);
  font-size: clamp(3rem, 8vw, 6rem);
  line-height: 1;
  text-shadow: 0 4px 24px rgba(0,0,0,0.3);
  margin-bottom: 1rem;
}

.hero-desc {
  font-size: clamp(1rem, 2.5vw, 1.2rem);
  font-weight: 600;
  opacity: 0.95;
  line-height: 1.7;
  margin-bottom: 1.75rem;
}

.hero-btns {
  display: flex;
  gap: 1rem;
  justify-content: center;
  flex-wrap: wrap;
}

.hero-btn {
  text-decoration: none;
  font-family: var(--font-body);
  font-weight: 800;
  font-size: 1rem;
  padding: 0.75rem 2rem;
  border-radius: 50px;
  transition: all 0.25s ease;
  display: inline-block;
}

.hero-btn.primary {
  background: var(--gold);
  color: var(--text-dark);
  box-shadow: 0 6px 24px rgba(0,0,0,0.22);
}

.hero-btn.primary:hover {
  background: var(--white);
  color: var(--red-dark);
  transform: translateY(-3px);
  box-shadow: 0 10px 32px rgba(244,185,66,0.5);
}

.hero-btn.secondary {
  background: transparent;
  color: var(--white);
  border: 2px solid rgba(255,255,255,0.8);
}

.hero-btn.secondary:hover {
  background: rgba(255,255,255,0.15);
  transform: translateY(-3px);
}

.hero-btn:focus-visible,
.nav-btn:focus-visible {
  outline: 3px solid var(--gold);
  outline-offset: 3px;
}

.hero-wave {
  position: absolute;
  bottom: -2px;
  left: 0;
  width: 100%;
  z-index: 3;
  line-height: 0;
}

.hero-wave svg {
  display: block;
  width: 100%;
}

/* ── NAVBAR ── */
.navbar {
  background: var(--white);
  position: sticky;
  top: 0;
  z-index: 100;
  box-shadow: 0 4px 24px rgba(198,40,40,0.12);
  border-bottom: 3px solid var(--red-light);
}

.nav-inner {
  max-width: 1100px;
  margin: 0 auto;
  display: flex;
  gap: 0.25rem;
  overflow-x: auto;
  padding: 0.75rem 1rem;
  scrollbar-width: none;
}

.nav-inner::-webkit-scrollbar { display: none; }

.nav-btn {
  font-family: var(--font-body);
  font-weight: 700;
  font-size: 0.95rem;
  padding: 0.55rem 1.25rem;
  border: 2px solid transparent;
  border-radius: 50px;
  background: var(--red-light);
  color: var(--text-mid);
  cursor: pointer;
  white-space: nowrap;
  transition: all 0.25s ease;
  flex-shrink: 0;
}

.nav-btn:hover {
  background: var(--red-mid);
  color: var(--white);
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(239,107,95,0.4);
}

.nav-btn.active {
  background: linear-gradient(135deg, var(--red-dark), var(--green-dark));
  color: var(--white);
  border-color: transparent;
  box-shadow: 0 4px 16px rgba(198,40,40,0.3);
}

/* ── MAIN ── */
.main {
  max-width: 1200px;
  margin: 0 auto;
  padding: 2rem 1.5rem 4rem;
  display: flex;
  flex-direction: column;
  gap: 4rem;
}

/* ── CATEGORY ── */
.category-header {
  text-align: center;
  margin-bottom: 2rem;
}

.category-icon {
  font-size: 3rem;
  display: block;
  margin-bottom: 0.5rem;
  animation: bounce 3s infinite ease-in-out;
}

.category-header h2 {
  font-family: var(--font-title);
  font-size: clamp(1.8rem, 4vw, 2.8rem);
  color: var(--red-dark);
  line-height: 1.1;
}

.category-header p {
  color: var(--text-mid);
  font-size: 1rem;
  margin-top: 0.4rem;
  font-weight: 600;
}

/* ── GRID ── */
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
  gap: 1.75rem;
}

/* ── CARD ── */
.card {
  background: var(--white);
  border-radius: var(--radius);
  box-shadow: var(--shadow);
  overflow: hidden;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  border: 2px solid var(--red-light);
  display: flex;
  flex-direction: column;
}

.card:hover {
  transform: translateY(-8px) scale(1.01);
  box-shadow: 0 16px 48px rgba(198,40,40,0.18);
  border-color: var(--red-mid);
}

.card.featured {
  border-color: var(--green-mid);
  background: linear-gradient(180deg, var(--green-light) 0%, var(--white) 40%);
}

.card.featured:hover {
  border-color: var(--green-dark);
  box-shadow: 0 16px 48px rgba(46,125,50,0.22);
}

.card-img-wrap {
  position: relative;
  overflow: hidden;
  height: 200px;
  background: linear-gradient(135deg, #ffd9a0, #fde3df); /* aparece se a foto falhar */
}

.card-img-wrap img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.4s ease;
  display: block;
}

.card:hover .card-img-wrap img {
  transform: scale(1.08);
}

.badge {
  position: absolute;
  top: 12px;
  left: 12px;
  background: linear-gradient(135deg, var(--red-dark), #ef5350);
  color: var(--white);
  font-size: 0.72rem;
  font-weight: 800;
  padding: 4px 10px;
  border-radius: 50px;
  text-transform: uppercase;
  letter-spacing: 1px;
  box-shadow: 0 2px 8px rgba(198,40,40,0.35);
}

.badge.new {
  background: linear-gradient(135deg, #66bb6a, #2e7d32);
}

.badge.chef {
  background: linear-gradient(135deg, var(--gold), #e08a00);
  color: var(--text-dark);
}

.card-body {
  padding: 1.25rem;
  flex: 1;
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.card-body h3 {
  font-size: 1.1rem;
  font-weight: 800;
  color: var(--text-dark);
  line-height: 1.3;
}

.card-body p {
  font-size: 0.9rem;
  color: var(--text-mid);
  line-height: 1.6;
  flex: 1;
}

.price {
  display: inline-block;
  font-family: var(--font-title);
  font-size: 1.4rem;
  color: var(--red-dark);
  margin-top: 0.5rem;
  letter-spacing: 0.5px;
}

.card.featured .price {
  color: var(--green-dark);
}

/* ── FOOTER ── */
.footer {
  background: linear-gradient(135deg, #2b1810 0%, #6d1b14 100%);
  color: rgba(255,255,255,0.85);
  margin-top: 2rem;
  position: relative;
}

.footer-wave {
  margin-bottom: -4px;
}

.footer-wave svg {
  display: block;
  width: 100%;
}

.footer-inner {
  max-width: 1100px;
  margin: 0 auto;
  padding: 2.5rem 1.5rem;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 2rem;
}

.footer-col {
  display: flex;
  flex-direction: column;
  gap: 0.6rem;
}

.footer-logo {
  font-family: var(--font-title);
  font-size: 1.8rem;
  color: var(--gold);
  margin-bottom: 0.4rem;
}

.footer-col h4 {
  font-size: 1rem;
  font-weight: 800;
  color: var(--green-mid);
  text-transform: uppercase;
  letter-spacing: 1px;
  margin-bottom: 0.4rem;
}

.footer-col p {
  font-size: 0.92rem;
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.footer-col p .fa {
  color: var(--gold);
  width: 16px;
}

.footer-bottom {
  text-align: center;
  padding: 1rem;
  border-top: 1px solid rgba(255,255,255,0.1);
  font-size: 0.85rem;
  color: rgba(255,255,255,0.5);
}

/* ── CATEGORY TRANSITION ── */
.category {
  animation: fadeUp 0.6s ease both;
}

.category.hidden {
  display: none;
}

.category.fade-in {
  animation: fadeUp 0.45s ease both;
}

/* ── ANIMATIONS ── */
@keyframes bounce {
  0%, 100% { transform: translateY(0); }
  50%       { transform: translateY(-8px); }
}

@keyframes floatIn {
  from { opacity: 0; transform: translateY(24px); }
  to   { opacity: 1; transform: translateY(0); }
}

@keyframes fadeUp {
  from { opacity: 0; transform: translateY(32px); }
  to   { opacity: 1; transform: translateY(0); }
}

@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after { animation: none !important; transition: none !important; }
}

/* ── RESPONSIVE ── */
@media (max-width: 640px) {
  .logo-wrap  { flex-direction: column; text-align: center; }
  .logo-text  { text-align: center; }
  .grid       { grid-template-columns: 1fr; }
  .nav-inner  { gap: 0.5rem; }
  .footer-inner { grid-template-columns: 1fr; text-align: center; }
  .footer-col p { justify-content: center; }
}
