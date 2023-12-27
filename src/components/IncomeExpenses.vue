<template>
  <div class="inc-exp-container">
    <div>
      <h4>общая цена</h4>
      <p id="money-plus" class="money plus">+${{ income }}</p>
    </div>
    <div>
      <h4>скидки</h4>
      <p id="money-minus" class="money minus">-${{ expenses }}</p>
    </div>
  </div>
</template>

<script setup>

//импортируем defineProps из vue, чтобы мы могли сделать константные реквизиты

import { defineProps } from 'vue';

const props = defineProps({
  income: {
    type: Number,
    required: true,
  },
  expenses: {
    type: Number,
    required: true,
  },
});
</script>