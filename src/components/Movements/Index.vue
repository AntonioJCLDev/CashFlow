<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="movements">
    <h2 class="title">Historial</h2>
    <div class="content">
      <!-- Recorre la lista movements y por cada uno de ellos muestra el titulo -->
      <Movement
        v-for="{ id, title, description, amount } in movements"
        :key="id"
        :id="id"
        :title="title"
        :description="description"
        :amount="amount"
        @remove="remove"
      />
    </div>
  </div>
</template>

<script setup>
/* En este caso vamos a usar COMPOSITION API
Importamos toRefs para convertir objetos en reactivos y 
defineProps para definir los props necesarios en el componente */
import { toRefs, defineProps } from "vue";
import Movement from "./Movement.vue";
//Definimos los props
const props = defineProps({
  movements: {
    type: Array,
    default: () => [],
  },
});
//Convertimos los props en reactivos y los guardamos en movements
const { movements } = toRefs(props);

const remove = (id) => {
  console.log("remove", id);
};
</script>

<style scoped>
.movements {
  max-height: 100%;
  padding: 0 8px;
  margin-bottom: 14px;
}
.title {
  margin: 8px 16px 24px 16px;
  color: var(--brand-blue);
}
.content {
  max-height: 68vh;
  display: flex;
  flex-direction: column;
  gap: 8px;
  overflow-y: scroll;
}
</style>
