<template>
  <nav class="navbar">
    <div class="navbar-container">
      <div class="navbar-brand">
        <h2 class="brand-text">Route-Link</h2>
      </div>
      
      <div class="navbar-menu">
        <router-link to="/beranda" class="nav-link" active-class="active">
          Beranda
        </router-link>
        
        <router-link to="/profil-sekolah" class="nav-link" active-class="active">
          ProfilSekolah
        </router-link>
        
      </div>
      
      <div class="navbar-toggle" @click="toggleMenu">
        <span class="hamburger"></span>
        <span class="hamburger"></span>
        <span class="hamburger"></span>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'Navbar',
  data() {
    return {
      isMenuOpen: false
    }
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen
      const menu = document.querySelector('.navbar-menu')
      if (this.isMenuOpen) {
        menu.classList.add('active')
      } else {
        menu.classList.remove('active')
      }
    }
  }
}
</script>

<style scoped>
.navbar {
  background: #ffffff;
  border-bottom: 1px solid #e5e5e5;
  position: sticky;
  top: 0;
  z-index: 1000;
}

.navbar-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 60px;
}

.navbar-brand {
  display: flex;
  align-items: center;
}

.brand-text {
  color: #333333;
  font-size: 1.5rem;
  font-weight: 600;
  margin: 0;
}

.navbar-menu {
  display: flex;
  align-items: center;
  gap: 30px;
}

.nav-link {
  color: #666666;
  text-decoration: none;
  font-weight: 500;
  font-size: 0.95rem;
  padding: 8px 12px;
  border-radius: 4px;
  transition: all 0.2s ease;
}

.nav-link:hover {
  color: #333333;
  background: #f5f5f5;
}

.nav-link.active {
  color: #333333;
  background: #f0f0f0;
  font-weight: 600;
}

.navbar-toggle {
  display: none;
  flex-direction: column;
  cursor: pointer;
  padding: 8px;
}

.hamburger {
  width: 20px;
  height: 2px;
  background: #333333;
  margin: 2px 0;
  border-radius: 1px;
  transition: 0.2s ease;
}

/* Responsive Design */
@media (max-width: 768px) {
  .navbar-menu {
    position: fixed;
    top: 60px;
    left: -100%;
    width: 100%;
    height: calc(100vh - 60px);
    background: #ffffff;
    flex-direction: column;
    justify-content: flex-start;
    padding-top: 20px;
    gap: 0;
    transition: left 0.3s ease;
    border-top: 1px solid #e5e5e5;
  }
  
  .navbar-menu.active {
    left: 0;
  }
  
  .navbar-toggle {
    display: flex;
  }
  
  .nav-link {
    font-size: 1rem;
    padding: 15px 20px;
    width: 100%;
    border-bottom: 1px solid #f0f0f0;
    border-radius: 0;
  }
  
  .nav-link:hover {
    background: #f8f8f8;
  }
  
  .nav-link.active {
    background: #f0f0f0;
    border-left: 3px solid #333333;
  }
}

@media (max-width: 480px) {
  .navbar-container {
    padding: 0 15px;
  }
  
  .brand-text {
    font-size: 1.3rem;
  }
}
</style>