<script setup lang="ts">
defineProps<{
  images: { src: string; orientation: "v" | "h" }[]
}>()
</script>

<template>
  <div class="masonry">
    <div
      v-for="(img,i) in images"
      :key="i"
      class="item"
      :class="img.orientation"
      @click="$emit('open', img)"
    >
      <img :src="img.src"
  loading="lazy"
  decoding="async"
  class="photo" />
    </div>
  </div>
</template>

<style scoped>
.masonry{
  column-count:3;
  column-gap:12px;
}

@media (max-width:900px){
  .masonry{ column-count:2; }
}
@media (max-width:600px){
  .masonry{ column-count:1; }
}

.item{
  break-inside:avoid;
  margin-bottom:12px;
  cursor:pointer;
}

.item img{
  width:100%;
  display:block;
  border-radius:10px;
}
.photo{
  width:100%;
  display:block;
  border-radius:10px;
  filter:blur(8px);
  transform:scale(1.02);
  transition:.6s ease;
}
.photo[src]{
  filter:blur(0);
  transform:scale(1);
}
</style>