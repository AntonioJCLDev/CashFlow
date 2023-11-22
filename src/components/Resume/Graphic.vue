<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div>
    <!-- Las características dentro de "view-box" representan donde comienza [x = 0 / y = 0]
     y donde terminan [x = 300 / y = 200] para definir el tamaño del lienzo. -->
    <svg view-box="0 0 300 150">
      <!-- Stroke define el color de la línea y x1,y1... las coordenadas dentro del lienzo -->
      <line stroke="#c4c4c4" stroke-width="2" x1="0" y1="75" x2="300" y2="75" />
      <polyline
        fill="none"
        stroke="#0689b0"
        stroke-width="2"
        points="0,0 100,75 200,75 250,50 300,150"
      />
      <line
        stroke="#04b500"
        stroke-width="2"
        x1="200"
        y1="0"
        x2="200"
        y2="200"
      />
    </svg>
    <p>Últimos 30 días</p>
  </div>
</template>

<style scoped>
svg {
  width: 100%;
}
p {
  text-align: center;
}
</style>
