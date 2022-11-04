<script>
import LayOut from "./LayOut.vue";
import HeaderV from "./HeaderFlow.vue";
import Resume from "./Resume/IndexResume.vue";
import Movements from "./Movements/IndexMovement.vue";

export default {
  components: {
    LayOut,
    HeaderV,
    Resume,
    Movements,
  },
  data() {
    return {
      amount: null,
      label: null,
      movements: [
        {
          id: 0,
          title: "Movimiento 1",
          description: "Lorem ipsum dolor sit mou",
          amount: 10000,
        },
        {
          id: 1,
          title: "Movimiento 2",
          description: "Lorem ipsum dolor sit mou",
          amount: -10000,
        },
        {
          id: 2,
          title: "Movimiento 3",
          description: "Lorem ipsum dolor sit mou",
          amount: 10000,
        },
        {
          id: 3,
          title: "Movimiento 4",
          description: "Lorem ipsum dolor sit mou",
          amount: 10000,
        },
        {
          id: 4,
          title: "Movimiento 5",
          description: "Lorem ipsum dolor sit mou",
          amount: -10000,
        },
        {
          id: 5,
          title: "Movimiento 6",
          description: "Lorem ipsum dolor sit mou",
          amount: 10000,
        },
        {
          id: 6,
          title: "Movimiento 7",
          description: "Lorem ipsum dolor sit mou",
          amount: 10000,
        },
        {
          id: 7,
          title: "Movimiento 8",
          description: "Lorem ipsum dolor sit mou",
          amount: 10000,
        },
        {
          id: 8,
          title: "Movimiento 9",
          description: "Lorem ipsum dolor sit mou",
          amount: 10000,
        },
        {
          id: 9,
          title: "Movimiento 10",
          description: "Lorem ipsum dolor sit mou",
          amount: 10000,
        },
        {
          id: 10,
          title: "Movimiento 11",
          description: "Lorem ipsum dolor sit mou",
          amount: 10000,
        },
        {
          id: 11,
          title: "Movimiento 12",
          description: "Lorem ipsum dolor sit mou",
          amount: 10000,
        },
      ],
    };
  },
};
</script>

<template>
  <LayOut>
    <template #header>
      <HeaderV></HeaderV>
    </template>
    <template #resume>
      <Resume
        :total-label="'Ahorro total'"
        :label="label"
        :total-amount="1000000"
        :amount="amount"
      >
        <template #graphic> graphic </template>
        <template #action> action </template>
      </Resume>
    </template>
    <template #movements>
      <Movements :movements="movements" />
    </template>
  </LayOut>
</template>

<style></style>
