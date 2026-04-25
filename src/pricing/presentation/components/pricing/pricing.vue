<script setup>
import { ref } from 'vue'

const plans = ref([
  {
    name: 'Plan Básico',
    price: '0',
    period: '/gratis',
    description: 'Prueba nuestras funciones esenciales',
    features: [
      'Registro de clientes',
      'Gestión de citas',
      'Órdenes de trabajo básicas',
      '1 usuario'
    ],
    buttonText: 'Empezar ahora',
    type: 'basic'
  },
  {
    name: 'Plan Estándar',
    price: '45',
    period: '/mes',
    description: 'Ideal para talleres en crecimiento',
    features: [
      'Todo lo del plan Básico',
      'Control de inventario',
      'Facturación y analítica',
      'Soporte técnico por chat'
    ],
    buttonText: 'Empezar ahora',
    type: 'standard',
    popular: true
  },
  {
    name: 'Plan Premium',
    price: '90',
    period: '/mes',
    description: 'Control total y herramientas avanzadas',
    features: [
      'Todo lo del plan Estándar',
      'Reportes de rentabilidad',
      'Asignación de personal',
      'Usuarios ilimitados'
    ],
    buttonText: 'Empezar ahora',
    type: 'premium'
  }
])
</script>

<template>
  <section class="pricing" id="pricing">
    <div class="pricing-header">
      <div class="pricing-tag">Precios</div>
      <h2 class="pricing-title">Encuentra el plan que se adapte a tus necesidades</h2>
    </div>

    <div class="pricing-grid">
      <div 
        v-for="plan in plans" 
        :key="plan.name"
        :class="['pricing-card', `card--${plan.type}`, { 'card--popular': plan.popular }]"
      >
        <div v-if="plan.popular" class="popular-badge">Más popular</div>
        
        <div class="card-header">
          <h3 class="plan-name">{{ plan.name }}</h3>
          <p class="plan-description">{{ plan.description }}</p>
          <div class="price">
            <span class="currency">S/</span>
            <span class="amount">{{ plan.price }}</span>
            <span class="period">{{ plan.period }}</span>
          </div>
        </div>

        <div class="card-body">
          <ul class="features">
            <li v-for="feature in plan.features" :key="feature">
              <svg class="check-icon" width="20" height="20" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M20 6L9 17L4 12" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"/>
              </svg>
              {{ feature }}
            </li>
          </ul>
        </div>

        <div class="card-footer">
          <button :class="['btn', `btn--${plan.type}`]">
            {{ plan.buttonText }}
          </button>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.pricing {
  padding: 100px 5%;
  max-width: 1400px;
  margin: 0 auto;
}

.pricing-header {
  text-align: center;
  margin-bottom: 80px;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 20px;
}

.pricing-tag {
  background-color: #0071EB;
  color: white;
  font-family: "Mona Sans";
  font-size: 20px;
  font-weight: 700;
  padding: 8px 24px;
  border-radius: 12px;
  display: inline-block;
}

.pricing-title {
  font-family: "Mona Sans";
  font-size: 42px;
  font-weight: 800;
  color: #212121;
  max-width: 700px;
  line-height: 1.2;
}

.pricing-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 32px;
}

.pricing-card {
  position: relative;
  border-radius: 40px;
  padding: 50px 40px;
  display: flex;
  flex-direction: column;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  border: 1px solid rgba(0, 0, 0, 0.05);
}

.card--basic {
  background-color: #F5F9FF;
}

.card--standard {
  background-color: #0071EB;
  color: white;
  transform: scale(1.05);
  box-shadow: 0 20px 40px rgba(0, 113, 235, 0.2);
  z-index: 2;
}

.card--premium {
  background-color: #1E1E1E;
  color: white;
}

.popular-badge {
  position: absolute;
  top: 24px;
  right: 40px;
  background-color: white;
  color: #0071EB;
  padding: 6px 16px;
  border-radius: 20px;
  font-family: "Mona Sans";
  font-weight: 700;
  font-size: 14px;
}

.plan-name {
  font-family: "Mona Sans";
  font-size: 28px;
  font-weight: 700;
  margin-bottom: 12px;
}

.plan-description {
  font-family: "Arimo";
  font-size: 16px;
  margin-bottom: 32px;
  opacity: 0.9;
}

.price {
  display: flex;
  align-items: baseline;
  gap: 4px;
  margin-bottom: 40px;
}

.currency {
  font-family: "Mona Sans";
  font-size: 24px;
  font-weight: 700;
}

.amount {
  font-family: "Mona Sans";
  font-size: 64px;
  font-weight: 800;
  line-height: 1;
}

.period {
  font-family: "Arimo";
  font-size: 18px;
  opacity: 0.8;
}

.features {
  list-style: none;
  padding: 0;
  margin: 0 0 40px 0;
  flex-grow: 1;
}

.features li {
  font-family: "Arimo";
  font-size: 16px;
  margin-bottom: 16px;
  display: flex;
  align-items: center;
  gap: 12px;
}

.check-icon {
  flex-shrink: 0;
}

.card--basic .check-icon { color: #0071EB; }
.card--standard .check-icon { color: white; }
.card--premium .check-icon { color: #0071EB; }

.btn {
  width: 100%;
  padding: 16px;
  border-radius: 16px;
  font-family: "Mona Sans";
  font-weight: 700;
  font-size: 18px;
  cursor: pointer;
  transition: filter 0.2s ease, transform 0.2s ease;
  border: none;
}

.btn--basic {
  background-color: transparent;
  border: 2px solid #0071EB;
  color: #0071EB;
}

.btn--standard {
  background-color: white;
  color: #0071EB;
}

.btn--premium {
  background-color: #0071EB;
  color: white;
}

.btn:hover {
  filter: brightness(0.9);
  transform: translateY(-2px);
}

@media (max-width: 1100px) {
  .pricing-grid {
    gap: 20px;
  }
  
  .pricing-card {
    padding: 40px 30px;
  }
  
  .amount {
    font-size: 48px;
  }
}
</style>
