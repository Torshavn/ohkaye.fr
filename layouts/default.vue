<template>
  <div class="layout">
    <header class="header">
      <nav class="nav">
        <NuxtLink to="/" class="logo">ohkaye.fr</NuxtLink>
        <div class="nav-links">
          <NuxtLink to="/">Gallery</NuxtLink>
          <NuxtLink to="/about">About</NuxtLink>
        </div>
      </nav>
    </header>

    <main class="main">
      <slot />
    </main>

    <footer class="footer">
      <p>&copy; 2026 ohkaye.fr - Photo Portfolio</p>
    </footer>
  </div>
</template>

<style scoped>
.layout {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

.header {
  background: #fff;
  border-bottom: 1px solid #e5e5e5;
  position: sticky;
  top: 0;
  z-index: 100;
}

.nav {
  max-width: 1200px;
  margin: 0 auto;
  padding: 1.5rem 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  font-size: 1.5rem;
  font-weight: bold;
  color: #333;
  text-decoration: none;
  transition: color 0.2s;
}

.logo:hover {
  color: #666;
}

.nav-links {
  display: flex;
  gap: 2rem;
}

.nav-links a {
  color: #666;
  text-decoration: none;
  transition: color 0.2s;
  font-weight: 500;
}

.nav-links a:hover,
.nav-links a.router-link-active {
  color: #333;
}

.main {
  flex: 1;
  max-width: 1200px;
  margin: 0 auto;
  padding: 2rem;
  width: 100%;
}

.footer {
  background: #f9f9f9;
  padding: 2rem;
  text-align: center;
  color: #666;
  border-top: 1px solid #e5e5e5;
}

@media (max-width: 768px) {
  .nav {
    flex-direction: column;
    gap: 1rem;
  }

  .nav-links {
    gap: 1rem;
  }

  .main {
    padding: 1rem;
  }
}
</style>
