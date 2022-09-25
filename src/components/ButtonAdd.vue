<script setup>
import BaseButton from './BaseButton.vue';
const emit = defineEmits([ 'add-click' ]);
</script>

<template>
  <BaseButton @on-click="emit('add-click')">追加</BaseButton>
</template>