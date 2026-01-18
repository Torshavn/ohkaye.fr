<script setup>
useHead({
  title: 'About - ohkaye.fr',
  meta: [
    { name: 'description', content: 'Learn more about the photographer behind ohkaye.fr' }
  ]
})
</script>

<template>
  <div class="about-page">
    <div class="about-header">
      <h1>About</h1>
    </div>

    <div class="about-content">
      <div class="about-section">
        <h2>Welcome to ohkaye.fr</h2>
        <p>
          This is a professional photo portfolio showcasing a collection of stunning 
          landscapes, travel photography, and natural beauty from around the world.
        </p>
        <p>
          Each photograph tells a story, capturing moments in time and the raw beauty 
          of our planet. From mountain peaks to ocean shores, from deserts to forests, 
          this portfolio represents a journey through diverse landscapes and cultures.
        </p>
      </div>

      <div class="about-section">
        <h2>Photography Style</h2>
        <p>
          The focus is on natural light photography, emphasizing the authentic beauty 
          of each location. Whether it's the golden hour glow on mountain peaks or the 
          mystical morning mist in ancient forests, each image aims to transport viewers 
          to that moment and place.
        </p>
      </div>

      <div class="about-section">
        <h2>Technical Approach</h2>
        <p>
          Using professional camera equipment from Canon, Sony, Nikon, and Fujifilm, 
          combined with high-quality lenses, each shot is carefully composed and 
          executed. Post-processing enhances the natural beauty while maintaining 
          authenticity.
        </p>
      </div>

      <div class="about-section">
        <h2>Get in Touch</h2>
        <p>
          Interested in prints, licensing, or collaboration? Feel free to reach out 
          through the contact information below.
        </p>
        <div class="contact-info">
          <p><strong>Email:</strong> contact@ohkaye.fr</p>
          <p><strong>Location:</strong> Based in France</p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.about-page {
  max-width: 800px;
  margin: 0 auto;
}

.about-header {
  margin-bottom: 3rem;
}

.about-header h1 {
  font-size: 3rem;
  color: #222;
  font-weight: 700;
}

.about-content {
  line-height: 1.8;
}

.about-section {
  margin-bottom: 3rem;
}

.about-section h2 {
  font-size: 1.8rem;
  color: #333;
  margin-bottom: 1rem;
  font-weight: 600;
}

.about-section p {
  color: #555;
  margin-bottom: 1rem;
  font-size: 1.1rem;
}

.contact-info {
  background: #f9f9f9;
  padding: 1.5rem;
  border-radius: 8px;
  margin-top: 1rem;
}

.contact-info p {
  margin-bottom: 0.5rem;
}

.contact-info p:last-child {
  margin-bottom: 0;
}

.contact-info strong {
  color: #333;
}

@media (max-width: 768px) {
  .about-header h1 {
    font-size: 2rem;
  }

  .about-section h2 {
    font-size: 1.5rem;
  }

  .about-section p {
    font-size: 1rem;
  }
}
</style>
