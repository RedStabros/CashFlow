<template>
  <button @click="showModal = true">Agregar Movimiento</button>
  <Teleport to="#app">
    <Modal v-show="showModal" @close="showModal = false">
      <form @submit.prevent="submit">
        <div class="field">
          <label for="">Título</label>
          <input type="text" v-model="title" />
        </div>
        <div class="field">
          <label for="">Monto</label>
          <input type="number" v-model="amount" />
        </div>
        <div class="field">
          <label for="">Description</label>
          <textarea rows="4" v-model="description"></textarea>
        </div>
        <div class="field">
          <label class="radio-label" for="">
            <input type="radio" v-model="movementType" value="Ingreso" />
            <span>Ingreso</span>
          </label>
          <label class="radio-label" for="">
            <input type="radio" v-model="movementType" value="Gasto" />
            <span>Gasto</span>
          </label>
          <div class="action">
            <button>Agregar Movimiento</button>
          </div>
        </div>
      </form>
    </Modal>
  </Teleport>
</template>

<script setup>
import { ref } from "vue";
import Modal from "./ModalCash.vue";

const showModal = ref(false);
const title = ref("");
const amount = ref(0);
const description = ref("");
const movementType = ref("Ingreso");

const submit = () => {
  showModal.value = !showModal.value;
};
</script>

<style scoped>
button {
  color: white;
  font-size: 1.25rem;
  background-color: var(--brand-blue);
  border: none;
  width: 100%;
  padding: 24px 60px;
  border-radius: 60px;
  box-sizing: border-box;
}

form {
  font-size: 1.24rem;
  width: 100%;
}

form .action {
  padding: 0 24px;
}

.field {
  display: flex;
  justify-content: space-between;
  flex-direction: column;
  padding: 16px 24px;
}

label {
  margin-bottom: 8px;
  font-weight: 700;
}

input,
textarea {
  font-size: 1.24rem;
  border: 2px solid var(--brand-blue);
  border-radius: 8px;
  padding: 8px;
}

input[type="number"] {
  text-align: right;
}

.radio-label {
  display: flex;
  align-items: center;
  margin-top: 8px;
}

.radio-label span {
  margin-top: 4px;
  margin-left: 8px;
}

input[type="radio"] {
  appearance: none;
  width: 1.24rem;
  height: 1.24rem;
  color: var(--brand-blue);
  border: 2px solid var(--brand-blue);
  border-radius: 50%;
}

input[type="radio"]:checked {
  background-color: var(--brand-blue);
}
button {
  margin-top: 2rem;
}
title {
  font-weight: 700;
}
</style>
