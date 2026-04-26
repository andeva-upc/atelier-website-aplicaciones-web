<script setup>
import { ref } from 'vue'

import joelImg from '@/assets/images/joel.png'
import adielImg from '@/assets/images/adiel.png'
import aldoImg from '@/assets/images/aldo.png'
import danielImg from '@/assets/images/daniel.png'
import jenniferImg from '@/assets/images/jennifer.png'

const members = ref([
  {
    name: 'Joel Huamani Estefanero',
    role: 'Team Leader',
    description: 'Estudiante de la Universidad Peruana de Ciencias Aplicadas de la carrera de Ingeniería de Software. Especializado en liderar y controlar el flujo del proyecto.',
    imageUrl: joelImg
  },
  {
    name: 'Adiel Abdiaz Sanchez Santin',
    role: 'Team Member',
    description: 'Estudiante de la Universidad Peruana de Ciencias Aplicadas de la carrera de Ingeniería de Software. Especializado en Front-End.',
    imageUrl: adielImg
  },
  {
    name: 'Aldo Jeanfranco Machacca Soto',
    role: 'Team Member',
    description: 'Estudiante de la Universidad Peruana de Ciencias Aplicadas de la carrera de Ingeniería de Software. Especializado en Web Services.',
    imageUrl: aldoImg
  },
  {
    name: 'Luis Daniel Granda Ibarra',
    role: 'Team Member',
    description: 'Estudiante de la Universidad Peruana de Ciencias Aplicadas cursando la carrera de Ingeniería de Software. Especializado en los datos y visualización del proyecto.',
    imageUrl: danielImg
  },
  {
    name: 'Jennifer Yamilet Riveros Vera',
    role: 'Team Member',
    description: 'Estudiante de la Universidad Peruana de Ciencias Aplicadas de la carrera de Ingeniería de Software. Especializada en datos.',
    imageUrl: jenniferImg
  }
])
</script>

<template>
  <section class="team-section" id="team">
    <div class="team-header">
      <div class="header-left">
        <h2 class="team-badge">Nuestro Equipo</h2>
      </div>
      <div class="header-right">
        <p class="team-subtitle">
          Conozca al equipo que está detrás de atelier.
        </p>
      </div>
    </div>

    <div class="team-grid">
      <div 
        v-for="member in members" 
        :key="member.name" 
        class="team-card"
      >
        <div class="card-header">
          <h3 class="member-name">{{ member.name }}</h3>
          <span class="member-role">{{ member.role }}</span>
        </div>
        
        <div class="member-image-container">
          <img :src="member.imageUrl" :alt="'Foto de ' + member.name" class="member-image">
        </div>
        
        <div class="card-footer">
          <p class="member-description">{{ member.description }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.team-section {
  padding: 100px 8%;
  max-width: 1400px;
  margin: 0 auto;
}

.team-header {
  display: flex;
  align-items: center;
  gap: 32px;
  margin-bottom: 60px;
}

.team-badge {
  background-color: #0071EB;
  color: white;
  font-family: "Mona Sans", sans-serif;
  font-size: 28px;
  font-weight: 700;
  padding: 8px 24px;
  border-radius: 12px;
  margin: 0;
  white-space: nowrap;
}

.team-subtitle {
  font-family: "Arimo", sans-serif;
  font-size: 18px;
  color: #757575;
  margin: 0;
}

.team-grid {
  display: flex;
  flex-wrap: wrap;
  gap: 32px;
  justify-content: center;
}

.team-card {
  flex: 0 1 calc(33.333% - 22px);
  min-width: 320px;
  background-color: white;
  border: 1.5px solid #212121;
  border-radius: 16px;
  padding: 24px;
  box-shadow: 4px 6px #212121;
  display: flex;
  flex-direction: column;
}

.card-header {
  margin-bottom: 16px;
}

.member-name {
  font-family: "Mona Sans", sans-serif;
  font-size: 16px;
  font-weight: 700;
  color: #212121;
  margin: 0 0 4px 0;
}

.member-role {
  font-family: "Arimo", sans-serif;
  font-size: 14px;
  color: #9e9e9e;
  display: block;
}

.member-image-container {
  width: 100%;
  aspect-ratio: 4 / 3;
  background-color: transparent;
  border-radius: 12px;
  overflow: hidden;
  margin-bottom: 20px;
}

.member-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}

.card-footer {
  flex-grow: 1;
}

.member-description {
  font-family: "Arimo", sans-serif;
  font-size: 13px;
  line-height: 1.5;
  color: #757575;
  margin: 0;
}

@media (max-width: 1100px) {
  .team-card {
    flex: 0 1 calc(50% - 16px);
  }
}

@media (max-width: 768px) {
  .team-header {
    flex-direction: column;
    align-items: flex-start;
    gap: 16px;
  }
  
  .team-card {
    flex: 1 1 100%;
  }
}
</style>
