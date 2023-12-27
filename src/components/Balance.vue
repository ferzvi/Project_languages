<template>
  <h4>Итоговая сумма</h4>
  <h1 id="balance">${{ total }}</h1>
</template>

<script setup>

//импортируем defineProps из vue, чтобы мы могли сделать константные реквизиты

import { defineProps } from 'vue';

//Здесь создаю переменную, которая будет транслировать текущий баланс пользователя

const props = defineProps({
  total: {
    type: Number,
    required: true,
  },
});
</script>