<script setup>
const route = useRoute()
const router = useRouter()
const photoId = parseInt(route.params.id)

// Sample photo data - should match the gallery
const photos = [
  {
    id: 1,
    title: 'Mountain Landscape',
    description: 'A beautiful view of mountain peaks during sunset',
    thumbnail: 'https://images.unsplash.com/photo-1506905925346-21bda4d32df4?w=400&h=300&fit=crop',
    full: 'https://images.unsplash.com/photo-1506905925346-21bda4d32df4?w=1200&h=800&fit=crop',
    details: 'Taken at the Swiss Alps during a summer hiking trip. The golden hour light created perfect conditions for this shot.',
    camera: 'Canon EOS R5',
    lens: 'RF 24-70mm f/2.8',
    settings: 'f/8, 1/250s, ISO 100',
  },
  {
    id: 2,
    title: 'Ocean Waves',
    description: 'Capturing the power and beauty of the ocean',
    thumbnail: 'https://images.unsplash.com/photo-1505142468610-359e7d316be0?w=400&h=300&fit=crop',
    full: 'https://images.unsplash.com/photo-1505142468610-359e7d316be0?w=1200&h=800&fit=crop',
    details: 'Shot on the coast of Portugal, this image captures the raw power of the Atlantic Ocean.',
    camera: 'Sony A7IV',
    lens: '70-200mm f/2.8',
    settings: 'f/11, 1/1000s, ISO 400',
  },
  {
    id: 3,
    title: 'Forest Path',
    description: 'A serene path through an ancient forest',
    thumbnail: 'https://images.unsplash.com/photo-1441974231531-c6227db76b6e?w=400&h=300&fit=crop',
    full: 'https://images.unsplash.com/photo-1441974231531-c6227db76b6e?w=1200&h=800&fit=crop',
    details: 'Morning mist creates a mystical atmosphere in this ancient forest path.',
    camera: 'Nikon Z7',
    lens: '24-120mm f/4',
    settings: 'f/5.6, 1/60s, ISO 800',
  },
  {
    id: 4,
    title: 'City Lights',
    description: 'Urban photography capturing the night life',
    thumbnail: 'https://images.unsplash.com/photo-1514565131-fce0801e5785?w=400&h=300&fit=crop',
    full: 'https://images.unsplash.com/photo-1514565131-fce0801e5785?w=1200&h=800&fit=crop',
    details: 'Long exposure shot of city lights creating light trails and urban energy.',
    camera: 'Fujifilm X-T4',
    lens: '16-55mm f/2.8',
    settings: 'f/16, 30s, ISO 100',
  },
  {
    id: 5,
    title: 'Desert Dunes',
    description: 'Golden sand dunes under clear blue skies',
    thumbnail: 'https://images.unsplash.com/photo-1509316785289-025f5b846b35?w=400&h=300&fit=crop',
    full: 'https://images.unsplash.com/photo-1509316785289-025f5b846b35?w=1200&h=800&fit=crop',
    details: 'The Sahara Desert at its most beautiful, with perfect light and dramatic shadows.',
    camera: 'Canon EOS R6',
    lens: 'RF 15-35mm f/2.8',
    settings: 'f/11, 1/320s, ISO 200',
  },
  {
    id: 6,
    title: 'Aurora Borealis',
    description: 'The magical northern lights dancing in the sky',
    thumbnail: 'https://images.unsplash.com/photo-1531366936337-7c912a4589a7?w=400&h=300&fit=crop',
    full: 'https://images.unsplash.com/photo-1531366936337-7c912a4589a7?w=1200&h=800&fit=crop',
    details: 'Captured in Iceland during a solar storm, creating incredible displays of auroras.',
    camera: 'Sony A7S III',
    lens: '14mm f/1.8',
    settings: 'f/2.8, 15s, ISO 3200',
  },
];

const photo = photos.find(p => p.id === photoId)

if (!photo) {
  throw createError({
    statusCode: 404,
    message: 'Photo not found'
  })
}

useHead({
  title: `${photo.title} - ohkaye.fr`,
  meta: [
    { name: 'description', content: photo.description }
  ]
})

const navigateToNext = () => {
  const currentIndex = photos.findIndex(p => p.id === photoId)
  const nextIndex = (currentIndex + 1) % photos.length
  router.push(`/photo/${photos[nextIndex].id}`)
}

const navigateToPrev = () => {
  const currentIndex = photos.findIndex(p => p.id === photoId)
  const prevIndex = currentIndex === 0 ? photos.length - 1 : currentIndex - 1
  router.push(`/photo/${photos[prevIndex].id}`)
}
</script>

<template>
  <div class="photo-page">
    <div class="photo-header">
      <NuxtLink to="/" class="back-link">← Back to Gallery</NuxtLink>
      <h1 class="photo-title">{{ photo.title }}</h1>
      <p class="photo-description">{{ photo.description }}</p>
    </div>

    <div class="photo-container">
      <img :src="photo.full" :alt="photo.title" class="photo-image" />
    </div>

    <div class="photo-details">
      <div class="detail-section">
        <h2>About this Photo</h2>
        <p>{{ photo.details }}</p>
      </div>

      <div class="detail-section technical">
        <h3>Technical Details</h3>
        <div class="tech-grid">
          <div class="tech-item">
            <strong>Camera:</strong>
            <span>{{ photo.camera }}</span>
          </div>
          <div class="tech-item">
            <strong>Lens:</strong>
            <span>{{ photo.lens }}</span>
          </div>
          <div class="tech-item">
            <strong>Settings:</strong>
            <span>{{ photo.settings }}</span>
          </div>
        </div>
      </div>
    </div>

    <div class="photo-navigation">
      <button @click="navigateToPrev" class="nav-button">← Previous</button>
      <button @click="navigateToNext" class="nav-button">Next →</button>
    </div>
  </div>
</template>

<style scoped>
.photo-page {
  max-width: 1000px;
  margin: 0 auto;
}

.photo-header {
  margin-bottom: 2rem;
}

.back-link {
  display: inline-block;
  color: #666;
  text-decoration: none;
  margin-bottom: 1rem;
  transition: color 0.2s;
}

.back-link:hover {
  color: #333;
}

.photo-title {
  font-size: 2.5rem;
  margin-bottom: 0.5rem;
  color: #222;
}

.photo-description {
  font-size: 1.2rem;
  color: #666;
}

.photo-container {
  margin-bottom: 2rem;
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
}

.photo-image {
  width: 100%;
  height: auto;
  display: block;
}

.photo-details {
  background: #f9f9f9;
  padding: 2rem;
  border-radius: 8px;
  margin-bottom: 2rem;
}

.detail-section {
  margin-bottom: 1.5rem;
}

.detail-section:last-child {
  margin-bottom: 0;
}

.detail-section h2 {
  font-size: 1.5rem;
  margin-bottom: 0.75rem;
  color: #222;
}

.detail-section h3 {
  font-size: 1.2rem;
  margin-bottom: 0.75rem;
  color: #333;
}

.detail-section p {
  color: #555;
  line-height: 1.8;
}

.tech-grid {
  display: grid;
  gap: 1rem;
}

.tech-item {
  display: flex;
  gap: 0.5rem;
}

.tech-item strong {
  color: #333;
  min-width: 80px;
}

.tech-item span {
  color: #666;
}

.photo-navigation {
  display: flex;
  justify-content: space-between;
  gap: 1rem;
  margin-top: 2rem;
}

.nav-button {
  flex: 1;
  padding: 1rem 2rem;
  background: #fff;
  border: 2px solid #e5e5e5;
  border-radius: 8px;
  cursor: pointer;
  font-size: 1rem;
  font-weight: 600;
  color: #333;
  transition: all 0.2s;
}

.nav-button:hover {
  background: #333;
  color: #fff;
  border-color: #333;
}

@media (max-width: 768px) {
  .photo-title {
    font-size: 2rem;
  }

  .photo-description {
    font-size: 1rem;
  }

  .photo-details {
    padding: 1.5rem;
  }

  .photo-navigation {
    flex-direction: column;
  }

  .nav-button {
    width: 100%;
  }
}
</style>
