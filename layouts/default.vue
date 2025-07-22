<template>
  <header>
    <nav class="fixed top-0 left-0 w-full z-50 bg-white shadow-sm border-b border-gray-100 px-6 py-4">
      <div class="flex items-center justify-between max-w-7xl mx-auto">
        <!-- Left side - Logo and Navigation -->
        <div class="flex items-center space-x-8">
          <NavbarLogo />

          <!-- Desktop Navigation -->
          <div class="hidden lg:flex items-center space-x-6">
            <!-- Ubah NuxtLink Home menjadi anchor dengan scroll -->
            <a href="#home" @click.prevent="scrollToSection('home')" class="text-sm font-medium transition-colors hover:text-red-600">
              Home
            </a>

            <!-- Scroll ke Mixtape -->
            <a href="#mixtape" @click.prevent="scrollToSection('mixtape')" class="text-sm font-medium transition-colors hover:text-red-600">
              Mixtape
            </a>

            <!-- Scroll ke Album -->
            <a href="#album" @click.prevent="scrollToSection('album')" class="text-sm font-medium transition-colors hover:text-red-600">
              Album
            </a>

            <!-- Scroll ke Artist -->
            <a href="#artist" @click.prevent="scrollToSection('artist')" class="text-sm font-medium transition-colors hover:text-red-600">
              Artist
            </a>

            <!-- About tetap NuxtLink -->
            <NuxtLink 
              to="/"
            >
              About
            </NuxtLink>
          </div>
        </div>

        <!-- Right side -->
        <div class="hidden lg:flex items-center space-x-4">
          <NavbarChart />
          <NavbarNotif />
          <NavbarProfileDropdown />
        </div>

        <!-- Mobile Burger -->
        <button 
          @click="toggleMobileMenu"
          class="lg:hidden flex items-center justify-center w-8 h-8"
        >
          <div class="space-y-1">
            <span :class="['block w-5 h-0.5 bg-gray-700 transition-all', isMobileMenuOpen ? 'rotate-45 translate-y-1.5' : '']" />
            <span :class="['block w-5 h-0.5 bg-gray-700 transition-all', isMobileMenuOpen ? 'opacity-0' : '']" />
            <span :class="['block w-5 h-0.5 bg-gray-700 transition-all', isMobileMenuOpen ? '-rotate-45 -translate-y-1.5' : '']" />
          </div>
        </button>
      </div>

      <!-- Mobile Menu -->
      <div :class="['lg:hidden overflow-hidden transition-all duration-300 ease-in-out', isMobileMenuOpen ? 'max-h-96 opacity-100' : 'max-h-0 opacity-0']">
        <div class="pt-4 pb-2 space-y-3">
          <!-- Mobile Home -->
          <a href="#home" @click.prevent="scrollToMobile('home')" class="block px-4 py-2 text-sm font-medium transition-colors hover:text-red-600">
            Home
          </a>

          <!-- Mobile Mixtape -->
          <a href="#mixtape" @click.prevent="scrollToMobile('mixtape')" class="block px-4 py-2 text-sm font-medium transition-colors hover:text-red-600">
            Mixtape
          </a>

          <!-- Mobile Album -->
          <a href="#album" @click.prevent="scrollToMobile('album')" class="block px-4 py-2 text-sm font-medium transition-colors hover:text-red-600">
            Album
          </a>

          <!-- Mobile Artist -->
          <a href="#artist" @click.prevent="scrollToMobile('artist')" class="block px-4 py-2 text-sm font-medium transition-colors hover:text-red-600">
            Artist
          </a>

          <!-- About -->
          <NuxtLink 
            to="/"
            @click="closeMobileMenu"
          >
            About
          </NuxtLink>

          <!-- Mobile Icons -->
          <div class="flex items-center space-x-4 px-4 pt-3 border-t border-gray-200">
            <NavbarChart />
            <NavbarNotif />
            <NavbarProfileDropdown />
          </div>
        </div>
      </div>
    </nav>
  </header>

  <!-- output page content -->
  <div class="pt-20">
    <slot />
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { useRouter, useRoute } from 'vue-router'

const isMobileMenuOpen = ref(false)
const route = useRoute()
const router = useRouter()

const toggleMobileMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value
}
const closeMobileMenu = () => {
  isMobileMenuOpen.value = false
}

const linkClass = (path) => {
  return [
    'text-sm font-medium transition-colors hover:text-red-600',
    route.path === path ? 'text-red-600' : 'text-gray-700'
  ]
}

// Scroll handler (desktop)
const scrollToSection = async (id) => {
  if (route.path !== '/') {
    await router.push('/')
    setTimeout(() => {
      const el = document.getElementById(id)
      if (el) el.scrollIntoView({ behavior: 'smooth' })
    }, 500)
  } else {
    const el = document.getElementById(id)
    if (el) el.scrollIntoView({ behavior: 'smooth' })
  }
}

// Scroll handler (mobile)
const scrollToMobile = async (id) => {
  closeMobileMenu()
  await scrollToSection(id)
}
</script>

<style scoped>
/* optional */
html {
  scroll-behavior: smooth;
}
</style>
