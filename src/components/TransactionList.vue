<template>
  <h3>История покупок</h3>
  <ul id="list" class="list">
    <li
      v-for="transaction in transactions"
      :key="transaction.id"
      :class="transaction.amount < 0 ? 'minus' : 'plus'"
    >
      {{ transaction.text }} <span>${{ transaction.amount }}</span
      ><button class="delete-btn" @click="deleteTransaction(transaction.id)">
        x
      </button>
    </li>
  </ul>
</template>

<script setup>

//импортируем defineProps из vue, чтобы мы могли сделать константные реквизиты

import { defineProps } from 'vue';

//определяем реквизит, передаём объект и добавляем к нему тип, чтобы тип был массивом, также говорим чтобы он был обязательным с помощью required: true

const props = defineProps({
  transactions: {
    type: Array,
    required: true,
  },
});

const emit = defineEmits(['transactionDeleted']);

const deleteTransaction = (id) => {
  emit('transactionDeleted', id);
};
</script>