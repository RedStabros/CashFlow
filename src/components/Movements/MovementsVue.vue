<template>
  <div class="movement">
    <div class="content">
      <h4>{{ title }}</h4>
      <p>{{ description }}</p>
    </div>
    <div class="action">
      <img class="img" @click="remove" src="@/assets/trash.svg" alt="borrar" />
      <p :class="{ red: isNegative, green: !isNegative }">
        {{ amountCurrency }}
      </p>
    </div>
  </div>
</template>

<script setup>
import { defineProps, toRefs, computed, defineEmits } from "vue";

const emit = defineEmits(["remove"]);

const isNegative = computed(() => amount.value < 0);

const currencyFormatter = new Intl.NumberFormat("es-CO", {
  style: "currency",
  currency: "COP",
});

const props = defineProps({
  id: {
    type: Number,
  },
  title: {
    type: String,
  },
  description: {
    type: String,
  },
  amount: {
    type: Number,
  },
});

const { id, title, description, amount } = toRefs(props);

const remove = () => {
  emit("remove", id.value);
};

const amountCurrency = computed(() => currencyFormatter.format(amount.value));
</script>

<style scoped>
.img {
  width: 20px;
  height: auto;
  color: black;
}

.movement {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  padding: 16px;
  background-color: #cbceee;
  border-radius: 8px;
  box-sizing: border-box;
}
.movement .content {
  width: 100%;
}
.movement .action {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  flex-direction: column;
}
h4,
p {
  margin: 0;
  padding: 0;
  color: black;
}
h4 {
  margin-bottom: 8px;
}
.movement .action img {
  margin-bottom: 16px;
}
.red {
  color: red;
}
.green {
  color: green;
}
</style>
