<template>
    <div class="container-fluid h-100">
      <div class="row h-100">
        <!-- Panel Izquierdo: Visualización del Coche -->
        <div class="col-md-6 car-display d-flex flex-column justify-content-center align-items-center">
          <div class="car-info mb-4">
            <saludo nombre="Anto"></saludo>
            <h1>Toyota 86</h1>
          </div>
          <div class="car-features d-flex justify-content-around flex-wrap">
            <!-- Tarjetas de características aquí -->
            <div class="feature card" v-for="feature in features" :key="feature.name">
              <div class="card-body d-flex align-items-center">
                <i :class="`fas ${feature.icon} feature-icon`"></i>
                <div>
                  <h5 class="card-title">{{ feature.name }}</h5>
                  <p class="card-text">{{ feature.value }}</p>
                </div>
              </div>
            </div>
          </div>
        </div>
  
        <!-- Panel Derecho: Mapa y Llamada -->
        <div class="col-md-6 map-and-call d-flex flex-column justify-content-between">
          <div class="status-bar d-flex justify-content-between align-items-center">
            <div class="battery-status">
              <i class="fa fa-car-battery"></i>
              <span>100%</span>
            </div>
            <div class="weather-status">
              <!-- Iconos del clima y velocidad del viento aquí -->
              <i class="fas fa-cloud-rain"></i>
              <span>24.0°C</span>
              <i class="fas fa-wind"></i>
              <span>25km/h</span>
            </div>
          </div>
          <div class="map-display">
            <!-- Componente de mapa aquí -->
          </div>
          <div class="call-display">
            <div class="caller-info">
              <h2>Braian Maciel</h2>
              <p>Llamando...</p>
            </div>
          </div>
        </div>
      </div>
    </div>
</template>
  
<script>
import saludo from "../components/Saludo.vue"

export default {
    name: 'CarInterface',
    components: {
      saludo
    },
    data() {
        return {
            features: [
                { name: 'Poder', value: '189 hp', icon: 'fa-horse' },
                { name: 'Consumo', value: '5.2 litros', icon: 'fa-gas-pump' },
                { name: 'Velocidad', value: '150 km', icon: 'fa-tachometer-alt' },
                { name: 'Aceleracion', value: '12.0 sec', icon: 'fa-stopwatch' },
                // Agrega aquí más características según sea necesario
            ],
            // Otros datos como el estado de la llamada
        };
    },
    
    // ... métodos, etc.
};
</script>