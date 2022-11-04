<template>
  <header>
    <img @click="reload" src="@/assets/cashflow-icon.svg" alt="Logo" />
    <h1><span>Cash</span>Flow</h1>
    <span></span>
  </header>
</template>

<script>
export default {
  methods: {
    reload() {
      location.reload();
    },
  },
};
</script>

<style scoped>
header {
  display: flex;
  justify-content: space-around;
  align-items: center;
  width: 100vh;
}
img,
span {
  width: 50px;
  cursor: pointer;
}
h1 {
  font-size: 1.4rem;
  color: var(--brand-blue);
  font-weight: bold;
}
h1 span {
  color: var(--brand-green);
}
</style>
