<template>
  <Layout>
    <template #header>
      <Header></Header>
    </template>
    <template #resume>
      <!-- label,totalAmount... son props que se recogen desde los datos del componente al importarlo.
      En el componente defines su estructura y aquí su valor, bien sea escribiendolo directamente o a través
      de variables en la sección data() [options API] -->
      <Resume
        :label="label"
        :labelDefault="'Ahorro Total'"
        :totalAmount="1000000"
        :amount="amount"
      >
        <template #graphic> graphic </template>
        <template #action>
          <Action />
        </template>
      </Resume>
    </template>
    <template #movements>
      <Movements :movements="movements" />
    </template>
  </Layout>
</template>

<script>
import Layout from "./Layout.vue";
import Header from "./Header.vue";
import Resume from "./Resume/Index.vue";
import Movements from "./Movements/Index.vue";
import Action from "./Action.vue";

export default {
  components: {
    Layout,
    Header,
    Resume,
    Movements,
    Action,
  },
  data() {
    return {
      amount: null,
      label: null,
      movements: [
        {
          id: 0,
          title: "Movimiento 1",
          description: "Lorem ipsum dolor",
          amount: -1000,
        },
        {
          id: 1,
          title: "Movimiento 2",
          description: "Lorem ipsum dolor",
          amount: 1000,
        },
        {
          id: 2,
          title: "Movimiento 3",
          description: "Lorem ipsum dolor",
          amount: 1000,
        },
        {
          id: 3,
          title: "Movimiento 4",
          description: "Lorem ipsum dolor",
          amount: -1000,
        },
        {
          id: 4,
          title: "Movimiento 5",
          description: "Lorem ipsum dolor",
          amount: 1000,
        },
        {
          id: 5,
          title: "Movimiento 6",
          description: "Lorem ipsum dolor",
          amount: 1000,
        },
        {
          id: 6,
          title: "Movimiento 7",
          description: "Lorem ipsum dolor",
          amount: 1000,
        },
        {
          id: 7,
          title: "Movimiento 8",
          description: "Lorem ipsum dolor",
          amount: 1000,
        },
      ],
    };
  },
};
</script>
