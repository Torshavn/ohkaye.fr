<script setup lang="ts">
import { projects } from "@/content/projects"

const selected = ref<string|null>(null)

const normalizedProjects = projects.map((project) => ({
  ...project,
  images: project.images.map((image) => ({
    ...image,
    orientation: (image.orientation === "v" ? ("v" as const) : ("h" as const)),
  })),
}))
</script>

<template>
  <div class="projects">

    <section v-for="project in normalizedProjects" :key="project.title">
      <NuxtLink :to="`/projects/${project.title.toLowerCase()}`">
  <h2>{{ project.title }}</h2>
    </NuxtLink>

      <GalleryGrid
        :images="project.images"
        @open="selected = $event"
      />
    </section>

    <Lightbox :src="selected" @close="selected=null"/>

  </div>
</template>