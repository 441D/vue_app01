<script setup>
  const props = defineProps({ color: String });
  const emit = defineEmits([ 'on-click' ]);
  const onClick = () => {
    emit('on-click');
  };
</script>

<template>
  <button class="btn" :class="props.color" @click="onClick"><slot /></button>
</template>

<style scoped>
  .btn {
    padding: 8px;
    background-image: linear-gradient(-20deg, #616161 0%, #9bc5c3 100%);
    border-radius: 6px;
    color: #fff;
    text-align: center;
    font-size: 14px;
  }
  .blue {
    background: #00A7E1;
  }
  .red {
    background: #EF6461;
  }
</style>