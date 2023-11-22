<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <main>
    <p>{{ labelVisual }}</p>
    <h1>{{ amountCurrency }}</h1>
    <div class="graphic">
      <slot name="graphic"></slot>
    </div>
    <div class="action">
      <slot name="action"></slot>
    </div>
  </main>
</template>

<script>
//codigo para formatear un numero al formato de la moneda elegida.
const currencyFormatter = new Intl.NumberFormat("es-ES", {
  style: "currency",
  currency: "EUR",
});

export default {
  props: {
    label: {
      type: String,
    },
    labelDefault: {
      type: String,
    },
    totalAmount: {
      type: Number,
    },
    amount: {
      type: Number,
      default: null,
    },
  },
  computed: {
    amountVisual() {
      //si amount NO es null devuelve amount. Si amount es null devuelve totalAmount.
      return this.amount !== null ? this.amount : this.totalAmount;
    },
    labelVisual() {
      return this.label !== null ? this.label : this.labelDefault;
    },
    amountCurrency() {
      return currencyFormatter.format(this.amountVisual);
    },
  },
};
</script>

<style scoped>
main {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  width: 100%;
}
h1,
p {
  margin: 0;
  text-align: center;
}
h1 {
  margin-top: 14px;
  color: var(--brand-green);
}
.graphic {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  padding: 48px 24px;
  box-sizing: border-box;
}
</style>
