<script setup>
// Fase 1: Estructura básica
</script>

<template>
  <section class="pricing" id="pricing">
    <div class="pricing-header">
      <div class="pricing-tag">Precios</div>
      <h2 class="pricing-title">Encuentra el plan que se adapte a tus necesidades</h2>
    </div>

    <div class="pricing-grid">
      <!-- Plan Básico -->
      <div class="pricing-card card--basic">
        <div class="card-header">
          <h3>Plan Básico</h3>
          <div class="price">S/ 0 <span>/gratis</span></div>
        </div>
        <div class="card-body">
          <ul class="features">
            <li>Funciones esenciales</li>
          </ul>
        </div>
        <div class="card-footer">
          <button class="btn btn--outline">Empezar</button>
        </div>
      </div>

      <!-- Plan Estándar -->
      <div class="pricing-card card--standard">
        <div class="card-header">
          <span class="badge">Más popular</span>
          <h3>Plan Estándar</h3>
          <div class="price">S/ 45 <span>/mes</span></div>
        </div>
        <div class="card-body">
          <ul class="features">
            <li>Todo lo del básico</li>
          </ul>
        </div>
        <div class="card-footer">
          <button class="btn btn--primary">Empezar</button>
        </div>
      </div>

      <!-- Plan Premium -->
      <div class="pricing-card card--premium">
        <div class="card-header">
          <h3>Plan Premium</h3>
          <div class="price">S/ 90 <span>/mes</span></div>
        </div>
        <div class="card-body">
          <ul class="features">
            <li>Todo lo del estándar</li>
          </ul>
        </div>
        <div class="card-footer">
          <button class="btn btn--dark">Empezar</button>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.pricing {
  padding: 80px 5%;
  max-width: 1400px;
  margin: 0 auto;
}

.pricing-header {
  text-align: center;
  margin-bottom: 60px;
}

.pricing-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 30px;
}
</style>
