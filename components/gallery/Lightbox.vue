<script setup lang="ts">
const props = defineProps<{ src:string|null }>()
const emit = defineEmits(["close"])
</script>

<template>
  <div v-if="src" class="overlay" @click="emit('close')">
    <img :src="src" class="image"/>
  </div>
</template>

<style scoped>
.overlay{
  position:fixed;
  inset:0;
  background:rgba(0,0,0,.9);
  display:flex;
  justify-content:center;
  align-items:center;
  z-index:999;
}

.image{
  max-width:90%;
  max-height:90%;
}
</style>