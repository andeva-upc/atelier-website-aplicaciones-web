<script setup>
import { ref, onMounted } from 'vue'

const fullText = "Ofrecemos una variedad de servicios y beneficios interesantes que pueden ayudarte a aumentar tu productividad en el trabajo y gestionar tu taller fácilmente. Estos servicios son:"
const displayedText = ref('')

onMounted(() => {
  let i = 0
  const interval = setInterval(() => {
    if (i < fullText.length) {
      displayedText.value += fullText.charAt(i)
      i++
    } else {
      clearInterval(interval)
    }
  }, 30)
})
</script>

<template>
  <section class="services">
    <div class="services-header">
      <div class="services-tag">Servicios</div>
      <p class="services-description">
        {{ displayedText }}<span class="cursor">|</span>
      </p>
    </div>

    <div class="services-grid">
      <!-- Card 1: Analítica y Facturación -->
      <div class="service-card card--light">
        <div class="card-content">
          <div class="card-title-badge badge--blue">
            Analítica y <br> Facturación
          </div>
        </div>
        <div class="card-image">
          <img src="../../../../assets/images/1.svg" alt="Analítica y Facturación">
        </div>
      </div>

      <!-- Card 2: Órdenes de trabajo -->
      <div class="service-card card--blue">
        <div class="card-content">
          <div class="card-title-badge badge--white">
            Órdenes de <br> trabajo
          </div>
        </div>
        <div class="card-image">
          <img src="../../../../assets/images/2.svg" alt="Órdenes de trabajo">
        </div>
      </div>

      <!-- Card 3: Fidelización de clientes -->
      <div class="service-card card--dark">
        <div class="card-content">
          <div class="card-title-badge badge--white">
            Fidelización <br> de clientes
          </div>
        </div>
        <div class="card-image">
          <img src="../../../../assets/images/3.svg" alt="Fidelización de clientes">
        </div>
      </div>

      <!-- Card 4: Registro de citas y clientes -->
      <div class="service-card card--light">
        <div class="card-content">
          <div class="card-title-badge badge--blue">
            Registro de citas <br> y clientes
          </div>
        </div>
        <div class="card-image">
          <img src="../../../../assets/images/4.svg" alt="Registro de citas y clientes">
        </div>
      </div>

      <!-- Card 5: Control de Inventario -->
      <div class="service-card card--blue">
        <div class="card-content">
          <div class="card-title-badge badge--white">
            Control de <br> Inventario
          </div>
        </div>
        <div class="card-image">
          <img src="../../../../assets/images/5.svg" alt="Control de Inventario">
        </div>
      </div>

      <!-- Card 6: Asignación de personal -->
      <div class="service-card card--dark">
        <div class="card-content">
          <div class="card-title-badge badge--blue">
            Asignación de <br> personal
          </div>
        </div>
        <div class="card-image">
          <img src="../../../../assets/images/6.svg" alt="Asignación de personal">
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.services {
  padding: 80px 5%;
  max-width: 1400px;
  margin: 0 auto;
}

.services-header {
  display: flex;
  align-items: flex-start;
  gap: 24px;
  margin-bottom: 60px;
}

.services-tag {
  background-color: #0071EB;
  color: white;
  font-family: "Mona Sans";
  font-size: 24px;
  font-weight: 700;
  padding: 8px 24px;
  border-radius: 12px;
}

.services-description {
  font-family: "Arimo";
  font-size: 18px;
  color: #757575;
  line-height: 1.5;
  max-width: 700px;
  min-height: 3em; /* Evita saltos de layout mientras se escribe */
}

.cursor {
  display: inline-block;
  width: 2px;
  background-color: #0071EB;
  margin-left: 2px;
  animation: blink 1s step-end infinite;
}

@keyframes blink {
  from, to { opacity: 1; }
  50% { opacity: 0; }
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 32px;
}

.service-card {
  position: relative;
  border-radius: 40px;
  height: 280px;
  padding: 40px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  overflow: hidden;
  border: 1px solid rgba(0, 0, 0, 0.1);
  box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.05);
}

.card--light {
  background-color: #E1F0FF;
}

.card--blue {
  background-color: #0071EB;
}

.card--dark {
  background-color: #1E1E1E;
}

.card-title-badge {
  font-family: "Mona Sans";
  font-size: 24px;
  font-weight: 700;
  padding: 8px 16px;
  border-radius: 8px;
  display: inline-block;
  line-height: 1.2;
}

.badge--blue {
  background-color: #0071EB;
  color: white;
}

.badge--white {
  background-color: white;
  color: #1E1E1E;
}

.card-image {
  width: 45%;
  height: auto;
  display: flex;
  justify-content: center;
  align-items: center;
}

.card-image img {
  max-width: 100%;
  height: auto;
  object-fit: contain;
  transition: transform 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
}

.service-card:hover .card-image img {
  transform: scale(1.1) rotate(2deg);
}

@media (max-width: 1000px) {
  .services-grid {
    gap: 20px;
  }
  
  .service-card {
    height: 240px;
    padding: 30px;
  }
  
  .card-title-badge {
    font-size: 20px;
  }
}

@media (max-width: 850px) {
  .services-grid {
    grid-template-columns: 1fr;
  }
  
  .services-header {
    flex-direction: column;
    gap: 16px;
  }
  
  .services-description {
    font-size: 16px;
  }
}

@media (max-width: 650px) {
  .services {
    padding: 40px 30px;
  }
  
  .service-card {
    height: auto;
    flex-direction: column;
    text-align: center;
    gap: 24px;
    padding: 40px 20px;
  }
  
  .card-image {
    width: 80%;
  }
}
</style>
