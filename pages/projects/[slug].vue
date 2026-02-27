<script setup lang="ts">
import { projects } from "@/content/projects"

const route = useRoute()
const selected = ref<{ src: string; orientation: "h" | "v" } | null>(null)

const project = projects.find(
  p => p.title.toLowerCase() === route.params.slug
)
</script>

<template>
  <div v-if="project">
    <h1>{{ project.title }}</h1>
    <GalleryGrid :images="project.images as { src: string; orientation: 'h' | 'v' }[]" @open="selected = $event"/>
  </div>

  <div v-else>
    Not found
  </div>
</template>