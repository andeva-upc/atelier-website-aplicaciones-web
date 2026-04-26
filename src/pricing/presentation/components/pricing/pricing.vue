<script setup>
import { ref } from 'vue'

const isAnnual = ref(false)

const plans = ref([
  {
    name: 'Lite',
    description: 'Conoce y explora el uso de atelier',
    price: 99,
    features: [
      'Gestión básica ERP',
      'Inventario',
      'Conexión de hasta 5 vehículos',
      'Próximas funciones'
    ],
    type: 'light'
  },
  {
    name: 'Pro',
    description: 'Experimenta el poder de infinitas posibilidades',
    price: 249,
    features: [
      'Todas las funciones del Plan Lite',
      'Gestión avanzada ERP',
      'Módulo de facturación electrónica',
      'Conexión de hasta 20 vehículos'
    ],
    type: 'main'
  },
  {
    name: 'Max',
    description: 'Desbloquea el máximo rendimiento de atelier',
    price: 499,
    features: [
      'Todas las funciones del Plan Pro',
      'Reportes de rentabilidad',
      'Conexión de hasta 50 vehículos',
      'Automatizaciones'
    ],
    type: 'light'
  }
])
</script>

<template>
  <section class="pricing" id="pricing">
    <!-- Header exacto -->
    <div class="pricing-header">
      <div class="header-left">
        <span class="tag-precios">Precios</span>
      </div>
      <div class="header-right">
        <p class="header-desc">
          Ofrecemos diferentes modelos de subscripción que se adaptan a ti y escalan contigo con beneficios únicos para crecer tu taller.
        </p>
      </div>
    </div>

    <!-- Selector de periodo -->
    <div class="toggle-container">
      <div class="toggle-switch">
        <button :class="{ active: !isAnnual }" @click="isAnnual = false">Mensual</button>
        <button :class="{ active: isAnnual }" @click="isAnnual = true">
          Anual <span class="savings">· Ahorra 17%</span>
        </button>
      </div>
    </div>

    <!-- Cuadrícula de planes -->
    <div class="pricing-grid">
      <div 
        v-for="plan in plans" 
        :key="plan.name" 
        :class="['card', `card--${plan.type}`]"
      >
        <div class="card-top">
          <h3 class="plan-name">{{ plan.name }}</h3>
          <p class="plan-desc">{{ plan.description }}</p>
          <div class="price-box">
            <span class="currency">S/.</span>
            <span class="amount">{{ isAnnual ? Math.round(plan.price * 0.83) : plan.price }}</span>
            <span class="period">/mes</span>
          </div>
        </div>

        <div class="features-box">
          <ul class="feature-list">
            <li v-for="feat in plan.features" :key="feat">
              <span class="check-icon">
                <svg width="22" height="22" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <circle cx="12" cy="12" r="10" fill="#0071EB"/>
                  <path d="M8 12L11 15L16 9" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
              </span>
              {{ feat }}
            </li>
          </ul>
          <div class="button-container">
            <button class="select-btn">Seleccionar {{ plan.name }}</button>
          </div>
        </div>
      </div>
    </div>

    <!-- Footer exacto -->
    <div class="pricing-footer">
      <p class="footer-disclaimer">
        Los precios mostrados no incluyen los impuestos aplicables. Los precios y los planes están sujetos a cambios a discreción de Andeva. Para planes Empresariales contactar con un asesor.
      </p>
      <div class="footer-action">
        <button class="contact-btn">Contactar con un asesor</button>
      </div>
    </div>
  </section>
</template>

<style scoped>
.pricing {
  padding: 100px 8%;
  max-width: 1400px;
  margin: 0 auto;
}

.pricing-header {
  display: flex;
  align-items: center;
  gap: 40px;
  margin-bottom: 60px;
}

.tag-precios {
  background-color: #0071EB;
  color: white;
  font-family: "Mona Sans";
  font-size: 24px;
  font-weight: 700;
  padding: 8px 24px;
  border-radius: 12px;
}

.header-desc {
  font-family: "Arimo";
  font-size: 18px;
  color: #757575;
  max-width: 600px;
  line-height: 1.4;
}

.toggle-container {
  display: flex;
  justify-content: center;
  margin-bottom: 60px;
}

.toggle-switch {
  background-color: #D1E4FF;
  padding: 8px;
  border-radius: 16px;
  display: flex;
  gap: 8px;
}

.toggle-switch button {
  padding: 12px 32px;
  border-radius: 12px;
  border: none;
  font-family: "Mona Sans";
  font-weight: 700;
  font-size: 18px;
  cursor: pointer;
  transition: all 0.3s ease;
  background: transparent;
  color: #212121;
}

.toggle-switch button.active {
  background-color: #0071EB;
  color: white;
}

.savings {
  font-size: 14px;
  font-weight: 400;
  opacity: 0.9;
}

.pricing-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 32px;
  align-items: stretch;
}

.card {
  background-color: white;
  border-radius: 40px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05);
  display: flex;
  flex-direction: column;
  border: 1px solid rgba(0, 0, 0, 0.05);
  transition: transform 0.3s ease;
}

.card--main {
  background-color: #0071EB;
  color: white;
  transform: scale(1.05);
  z-index: 2;
  box-shadow: 0 20px 50px rgba(0, 113, 235, 0.2);
}

.card-top {
  padding: 60px 40px 20px;
  text-align: center;
}

.plan-name {
  font-family: "Mona Sans";
  font-size: 32px;
  font-weight: 800;
  margin-bottom: 8px;
}

.plan-desc {
  font-family: "Arimo";
  font-size: 15px;
  margin-bottom: 24px;
  opacity: 0.9;
}

.price-box {
  display: flex;
  justify-content: center;
  align-items: flex-start;
  gap: 4px;
}

.currency {
  font-family: "Mona Sans";
  font-size: 20px;
  font-weight: 700;
  margin-top: 8px;
}

.amount {
  font-family: "Mona Sans";
  font-size: 80px;
  font-weight: 900;
  line-height: 1;
}

.period {
  font-family: "Arimo";
  font-size: 16px;
  opacity: 0.8;
  align-self: flex-end;
  margin-bottom: 12px;
}

.features-box {
  background-color: #D1E4FF;
  padding: 30px 40px;
  margin: 0 15px 15px;
  border-radius: 40px;
  flex-grow: 1;
  display: flex;
  flex-direction: column;
  overflow: hidden;
}

.card--main .features-box {
  background-color: white;
  color: #212121;
}

.feature-list {
  list-style: none;
  padding: 0;
  margin: 0 0 30px 0;
  flex-grow: 1;
}

.feature-list li {
  font-family: "Arimo";
  font-size: 16px;
  font-weight: 600;
  margin-bottom: 16px;
  display: flex;
  align-items: flex-start;
  gap: 12px;
  text-align: left;
  line-height: 1.2;
}

.check-icon {
  flex-shrink: 0;
  margin-top: 2px;
}

.button-container {
  margin-top: auto;
}

.select-btn {
  width: 100%;
  padding: 16px;
  border-radius: 14px;
  font-family: "Mona Sans";
  font-weight: 700;
  font-size: 18px;
  cursor: pointer;
  background-color: white;
  color: #0071EB;
  border: 2px solid #0071EB;
  transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
}

.card--main .select-btn {
  background-color: #0071EB;
  color: white;
  border: none;
}

.select-btn:hover {
  transform: translateY(-5px) scale(1.02);
  box-shadow: 0 10px 20px rgba(0, 113, 235, 0.2);
  filter: brightness(1.1);
}

.card--main .select-btn:hover {
  background-color: #0056b3;
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.15);
}

.pricing-footer {
  margin-top: 60px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.footer-disclaimer {
  font-family: "Arimo";
  font-size: 14px;
  color: #757575;
  max-width: 900px;
  margin: 0 auto 30px;
  line-height: 1.6;
  text-align: center;
}

.footer-action {
  width: 100%;
  display: flex;
  justify-content: flex-end; /* Botón a la derecha */
}

.contact-btn {
  background-color: #0071EB;
  color: white;
  font-family: "Mona Sans";
  font-weight: 700;
  font-size: 18px;
  padding: 16px 40px;
  border-radius: 12px;
  border: none;
  cursor: pointer;
  box-shadow: 0 8px 24px rgba(0, 113, 235, 0.2);
  transition: transform 0.2s ease;
}

.contact-btn:hover {
  transform: translateY(-2px);
  filter: brightness(1.05);
}

@media (max-width: 1100px) {
  .pricing-grid {
    grid-template-columns: 1fr;
    gap: 40px;
  }
  
  .card--main {
    transform: none;
  }
  
  .pricing-header {
    flex-direction: column;
    text-align: center;
  }

  .amount {
    font-size: 90px;
  }
}
</style>
