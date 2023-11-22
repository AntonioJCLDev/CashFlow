<template>
  <Suspense>
    <template #default>
      <Home />
    </template>
    <template #fallback>
      <splashscreen />
    </template>
  </Suspense>
</template>

<script>
import splashscreen from "@/components/SplashScreen.vue";
import { defineAsyncComponent } from "vue";
// eslint-disable-next-line no-unused-vars
import Home from "@/components/HomePage.vue";

export default {
  components: {
    splashscreen,
    Home: defineAsyncComponent(
      () =>
        new Promise((resolve) => {
          setTimeout(() => {
            resolve(import("@/components/HomePage.vue"));
          }, 2500);
        })
    ),
  },
};
</script>

<style>
html,
body,
.app {
  min-height: 100vh;
  margin: 0;
  font-family: Arial, Helvetica, sans-serif;
}

* {
  --brand-green: #04b500;
  --brand-blue: #0689b0;
}
</style>
