<script setup>
// Sample photo data - in a real app, this would come from an API or CMS
const photos = [
  {
    id: 1,
    title: 'Mountain Landscape',
    description: 'A beautiful view of mountain peaks during sunset',
    thumbnail: 'https://images.unsplash.com/photo-1506905925346-21bda4d32df4?w=400&h=300&fit=crop',
    full: 'https://images.unsplash.com/photo-1506905925346-21bda4d32df4?w=1200&h=800&fit=crop',
  },
  {
    id: 2,
    title: 'Ocean Waves',
    description: 'Capturing the power and beauty of the ocean',
    thumbnail: 'https://images.unsplash.com/photo-1505142468610-359e7d316be0?w=400&h=300&fit=crop',
    full: 'https://images.unsplash.com/photo-1505142468610-359e7d316be0?w=1200&h=800&fit=crop',
  },
  {
    id: 3,
    title: 'Forest Path',
    description: 'A serene path through an ancient forest',
    thumbnail: 'https://images.unsplash.com/photo-1441974231531-c6227db76b6e?w=400&h=300&fit=crop',
    full: 'https://images.unsplash.com/photo-1441974231531-c6227db76b6e?w=1200&h=800&fit=crop',
  },
  {
    id: 4,
    title: 'City Lights',
    description: 'Urban photography capturing the night life',
    thumbnail: 'https://images.unsplash.com/photo-1514565131-fce0801e5785?w=400&h=300&fit=crop',
    full: 'https://images.unsplash.com/photo-1514565131-fce0801e5785?w=1200&h=800&fit=crop',
  },
  {
    id: 5,
    title: 'Desert Dunes',
    description: 'Golden sand dunes under clear blue skies',
    thumbnail: 'https://images.unsplash.com/photo-1509316785289-025f5b846b35?w=400&h=300&fit=crop',
    full: 'https://images.unsplash.com/photo-1509316785289-025f5b846b35?w=1200&h=800&fit=crop',
  },
  {
    id: 6,
    title: 'Aurora Borealis',
    description: 'The magical northern lights dancing in the sky',
    thumbnail: 'https://images.unsplash.com/photo-1531366936337-7c912a4589a7?w=400&h=300&fit=crop',
    full: 'https://images.unsplash.com/photo-1531366936337-7c912a4589a7?w=1200&h=800&fit=crop',
  },
];
</script>

<template>
  <div class="gallery">
    <NuxtLink
      v-for="photo in photos"
      :key="photo.id"
      :to="`/photo/${photo.id}`"
      class="gallery-item"
    >
      <img :src="photo.thumbnail" :alt="photo.title" class="gallery-image" />
      <div class="gallery-overlay">
        <h3>{{ photo.title }}</h3>
      </div>
    </NuxtLink>
  </div>
</template>

<style scoped>
.gallery {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 2rem;
  padding: 1rem 0;
}

.gallery-item {
  position: relative;
  aspect-ratio: 4 / 3;
  overflow: hidden;
  border-radius: 8px;
  cursor: pointer;
  text-decoration: none;
  transition: transform 0.3s ease;
}

.gallery-item:hover {
  transform: translateY(-4px);
}

.gallery-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.gallery-item:hover .gallery-image {
  transform: scale(1.05);
}

.gallery-overlay {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  background: linear-gradient(to top, rgba(0, 0, 0, 0.8), transparent);
  color: white;
  padding: 1.5rem 1rem 1rem;
  opacity: 0;
  transition: opacity 0.3s ease;
}

.gallery-item:hover .gallery-overlay {
  opacity: 1;
}

.gallery-overlay h3 {
  margin: 0;
  font-size: 1.2rem;
  font-weight: 600;
}

@media (max-width: 768px) {
  .gallery {
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    gap: 1rem;
  }
}

@media (max-width: 480px) {
  .gallery {
    grid-template-columns: 1fr;
  }
}
</style>
