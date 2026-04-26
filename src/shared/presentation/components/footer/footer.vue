<script setup>
</script>

<template>
  <footer class="site-footer" id="contact">
    <div class="footer-container">
      <div class="footer-top">
        <a class="footer-logo" href="#" aria-label="Ir al inicio de atelier">
          <svg
            class="footer-logo-icon"
            width="56"
            height="52"
            viewBox="0 0 56 52"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
            aria-hidden="true"
          >
            <path
              d="M46.6667 13.4333L30.3333 4.89667C29.6239 4.51634 28.8192 4.31611 28 4.31611C27.1808 4.31611 26.3761 4.51634 25.6667 4.89667L9.33334 13.4117C8.61773 13.7953 8.02464 14.3484 7.61468 15.0146C7.20473 15.6808 6.99261 16.4361 7 17.2033V34.7967C6.99674 35.5602 7.21082 36.3111 7.62057 36.9731C8.03032 37.6351 8.62118 38.1849 9.33334 38.5667L25.6667 47.1033C26.3761 47.4837 27.1808 47.6839 28 47.6839C28.8192 47.6839 29.6239 47.4837 30.3333 47.1033L46.6667 38.5883C47.3823 38.2047 47.9754 37.6516 48.3853 36.9854C48.7953 36.3192 49.0074 35.5639 49 34.7967V17.2033C49.0033 16.4398 48.7892 15.6889 48.3794 15.0269C47.9697 14.3649 47.3788 13.8151 46.6667 13.4333ZM28 32.5C26.6155 32.5 25.2622 32.1188 24.111 31.4046C22.9599 30.6903 22.0627 29.6752 21.5328 28.4874C21.003 27.2997 20.8644 25.9928 21.1345 24.7319C21.4046 23.471 22.0713 22.3128 23.0503 21.4038C24.0292 20.4948 25.2765 19.8757 26.6344 19.6249C27.9922 19.3741 29.3997 19.5028 30.6788 19.9948C31.9579 20.4868 33.0511 21.3199 33.8203 22.3888C34.5895 23.4577 35 24.7144 35 26C35 27.7239 34.2625 29.3772 32.9497 30.5962C31.637 31.8152 29.8565 32.5 28 32.5Z"
              fill="white"
            />
          </svg>
          <span class="footer-logo-text">atelier</span>
        </a>

        <div class="footer-socials" aria-label="Redes sociales de atelier">
          <a href="#" aria-label="Facebook de atelier">f</a>
          <a href="#" aria-label="Twitter de atelier">t</a>
        </div>
      </div>

      <div class="footer-content">
        <section class="footer-contact" aria-labelledby="footer-contact-title">
          <h2 id="footer-contact-title">Contáctanos:</h2>
          <p><strong>Email:</strong> info@andeva.com</p>
          <p><strong>Número Telefónico:</strong> 999-999-999</p>
          <p>
            <strong>Dirección:</strong> Av. Alameda<br>
            San Marcos, Chorrillos, Lima
          </p>
        </section>

        <section class="footer-newsletter" aria-label="Suscripción a noticias">
          <form class="newsletter-form" @submit.prevent>
            <label class="sr-only" for="newsletter-email">Correo electrónico</label>
            <input
              id="newsletter-email"
              type="email"
              name="email"
              placeholder="Email"
              autocomplete="email"
              required
            >
            <button type="submit">Suscríbete para noticias</button>
          </form>
        </section>
      </div>

      <div class="footer-divider"></div>

      <div class="footer-bottom">
        <p>© 2026 Andeva. All Rights Reserved.</p>
        <nav class="footer-legal" aria-label="Enlaces legales">
          <a href="#">Políticas de Privacidad</a>
          <a href="#">Términos y Condiciones</a>
        </nav>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.site-footer {
  padding: 40px 5% 0;
  background-color: #ffffff;
}

.footer-container {
  width: 100%;
  max-width: 1400px;
  margin: 0 auto;
  padding: 48px 64px 32px;
  border-radius: 40px 40px 0 0;
  background-color: #0059b8;
  color: #ffffff;
}

.footer-top {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 44px;
}

.footer-logo {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  color: #ffffff;
  text-decoration: none;
}

.footer-logo-icon {
  width: 40px;
  height: 40px;
}

.footer-logo-text {
  font-family: "Zizou Slab Medium", "Mona Sans", system-ui, sans-serif;
  font-size: 44px;
  font-weight: 700;
  line-height: 1;
}

.footer-socials {
  display: flex;
  align-items: center;
  gap: 12px;
}

.footer-socials a {
  width: 28px;
  height: 28px;
  border-radius: 50%;
  background-color: #ffffff;
  color: #0059b8;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  font-family: "Mona Sans", system-ui, sans-serif;
  font-size: 16px;
  font-weight: 800;
  text-decoration: none;
  transition: transform 0.2s ease, background-color 0.2s ease;
}

.footer-socials a:hover {
  transform: translateY(-2px);
  background-color: #d1e4ff;
}

.footer-content {
  display: grid;
  grid-template-columns: 1fr 1.8fr;
  gap: 80px;
  align-items: center;
}

.footer-contact h2 {
  display: inline-block;
  margin-bottom: 24px;
  font-family: "Mona Sans", system-ui, sans-serif;
  font-size: 18px;
  font-weight: 700;
  color: #ffffff;
  text-decoration: underline;
}

.footer-contact p {
  margin-bottom: 12px;
  font-family: "Arimo", system-ui, sans-serif;
  font-size: 15px;
  line-height: 1.5;
  color: #ffffff;
}

.footer-contact strong {
  font-weight: 700;
}

.footer-newsletter {
  padding: 36px;
  border-radius: 12px;
  background-color: #d1e4ff;
}

.newsletter-form {
  display: grid;
  grid-template-columns: 1fr auto;
  gap: 16px;
}

.newsletter-form input {
  width: 100%;
  min-height: 56px;
  padding: 0 20px;
  border: 1.5px solid #0071eb;
  border-radius: 10px;
  background-color: transparent;
  color: #212121;
  font-family: "Arimo", system-ui, sans-serif;
  font-size: 16px;
  outline: none;
}

.newsletter-form input::placeholder {
  color: #0071eb;
}

.newsletter-form input:focus {
  border-color: #0059b8;
  box-shadow: 0 0 0 3px rgba(0, 113, 235, 0.18);
}

.newsletter-form button {
  min-height: 56px;
  padding: 0 32px;
  border: none;
  border-radius: 10px;
  background-color: #0071eb;
  color: #ffffff;
  font-family: "Mona Sans", system-ui, sans-serif;
  font-size: 16px;
  font-weight: 700;
  cursor: pointer;
  transition: transform 0.2s ease, filter 0.2s ease;
}

.newsletter-form button:hover {
  transform: translateY(-2px);
  filter: brightness(1.05);
}

.footer-divider {
  height: 1px;
  margin: 48px 0 28px;
  background-color: rgba(255, 255, 255, 0.35);
}

.footer-bottom {
  display: flex;
  align-items: center;
  gap: 48px;
  flex-wrap: wrap;
}

.footer-bottom p,
.footer-legal a {
  font-family: "Arimo", system-ui, sans-serif;
  font-size: 14px;
  color: #ffffff;
}

.footer-bottom p {
  margin: 0;
}

.footer-legal {
  display: flex;
  align-items: center;
  gap: 36px;
  flex-wrap: wrap;
}

.footer-legal a {
  text-decoration: underline;
}

.footer-legal a:hover {
  color: #d1e4ff;
}

.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  white-space: nowrap;
  border: 0;
}

@media (max-width: 900px) {
  .footer-container {
    padding: 40px 32px 28px;
    border-radius: 32px 32px 0 0;
  }

  .footer-content {
    grid-template-columns: 1fr;
    gap: 32px;
  }

  .newsletter-form {
    grid-template-columns: 1fr;
  }

  .footer-bottom {
    flex-direction: column;
    align-items: flex-start;
    gap: 16px;
  }
}

@media (max-width: 650px) {
  .site-footer {
    padding: 32px 24px 0;
  }

  .footer-container {
    padding: 32px 24px 24px;
  }

  .footer-top {
    align-items: flex-start;
    gap: 24px;
  }

  .footer-logo-text {
    font-size: 34px;
  }

  .footer-newsletter {
    padding: 24px;
  }

  .footer-legal {
    flex-direction: column;
    align-items: flex-start;
    gap: 12px;
  }
}
</style>
