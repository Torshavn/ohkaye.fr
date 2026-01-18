<script setup>
useHead({
  title: 'Photo Portfolio - ohkaye.fr',
  meta: [
    { name: 'description', content: 'Professional photo portfolio showcasing stunning landscapes and travel photography' }
  ]
})
</script>

<template>
  <div>
    <div class="hero">
      <h1 class="hero-title">Photo Portfolio</h1>
      <p class="hero-subtitle">Capturing moments, telling stories</p>
    </div>
    
    <PhotoGallery />
  </div>
</template>

<style scoped>
.hero {
  text-align: center;
  padding: 3rem 0;
  margin-bottom: 2rem;
}

.hero-title {
  font-size: 3rem;
  font-weight: 700;
  margin-bottom: 0.5rem;
  color: #222;
}

.hero-subtitle {
  font-size: 1.25rem;
  color: #666;
  font-weight: 300;
}

@media (max-width: 768px) {
  .hero {
    padding: 2rem 0;
  }

  .hero-title {
    font-size: 2rem;
  }

  .hero-subtitle {
    font-size: 1rem;
  }
}
</style>
