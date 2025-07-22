<template>
    <header>
        <nav class="bg-white shadow-sm border-b border-gray-100 px-6 py-4">
          <div class="flex items-center justify-between max-w-7xl mx-auto">
            <!-- Left side - Logo and Navigation -->
            <div class="flex items-center space-x-8">
              <NavbarLogo />
              
              <!-- Desktop Navigation -->
              <div class="hidden lg:flex items-center space-x-6">
                <NuxtLink 
                  to="/" 
                  :class="[
                    'text-sm font-medium transition-colors hover:text-red-600',
                    isActiveRoute('/') ? 'text-red-600' : 'text-gray-700'
                  ]"
                >
                  Home
                </NuxtLink>
                
                <NuxtLink 
                  to="/mixtape" 
                  :class="[
                    'text-sm font-medium transition-colors hover:text-red-600',
                    isActiveRoute('/mixtape') ? 'text-red-600' : 'text-gray-700'
                  ]"
                >
                  Mixtape
                </NuxtLink>
                
                <NuxtLink 
                  to="/album" 
                  :class="[
                    'text-sm font-medium transition-colors hover:text-red-600',
                    isActiveRoute('/album') ? 'text-red-600' : 'text-gray-700'
                  ]"
                >
                  Album
                </NuxtLink>
                
                <NuxtLink 
                  to="/artist" 
                  :class="[
                    'text-sm font-medium transition-colors hover:text-red-600',
                    isActiveRoute('/artist') ? 'text-red-600' : 'text-gray-700'
                  ]"
                >
                  Artist
                </NuxtLink>
                
                <NuxtLink 
                  to="/about" 
                  :class="[
                    'text-sm font-medium transition-colors hover:text-red-600',
                    isActiveRoute('/about') ? 'text-red-600' : 'text-gray-700'
                  ]"
                >
                  About
                </NuxtLink>
              </div>
            </div>
            
            <!-- Right side - Desktop Icons and Mobile Burger -->
            <div class="hidden lg:flex items-center space-x-4">
              <NavbarChart />
              <NavbarNotif />
              <NavbarProfileDropdown />
            </div>
            
            <!-- Mobile Burger Menu Button -->
            <button 
              @click="toggleMobileMenu"
              class="lg:hidden flex items-center justify-center w-8 h-8"
            >
              <div class="space-y-1">
                <span 
                  :class="[
                    'block w-5 h-0.5 bg-gray-700 transition-all duration-300 ease-in-out',
                    isMobileMenuOpen ? 'rotate-45 translate-y-1.5' : ''
                  ]"
                ></span>
                <span 
                  :class="[
                    'block w-5 h-0.5 bg-gray-700 transition-all duration-300 ease-in-out',
                    isMobileMenuOpen ? 'opacity-0' : ''
                  ]"
                ></span>
                <span 
                  :class="[
                    'block w-5 h-0.5 bg-gray-700 transition-all duration-300 ease-in-out',
                    isMobileMenuOpen ? '-rotate-45 -translate-y-1.5' : ''
                  ]"
                ></span>
              </div>
            </button>
          </div>
          
          <!-- Mobile Menu -->
          <div 
            :class="[
              'lg:hidden overflow-hidden transition-all duration-300 ease-in-out',
              isMobileMenuOpen ? 'max-h-96 opacity-100' : 'max-h-0 opacity-0'
            ]"
          >
            <div class="pt-4 pb-2 space-y-3">
              <!-- Mobile Navigation Links -->
              <NuxtLink 
                to="/" 
                @click="closeMobileMenu"
                :class="[
                  'block px-4 py-2 text-sm font-medium transition-colors hover:text-red-600',
                  isActiveRoute('/') ? 'text-red-600' : 'text-gray-700'
                ]"
              >
                Home
              </NuxtLink>
              
              <NuxtLink 
                to="/mixtape" 
                @click="closeMobileMenu"
                :class="[
                  'block px-4 py-2 text-sm font-medium transition-colors hover:text-red-600',
                  isActiveRoute('/mixtape') ? 'text-red-600' : 'text-gray-700'
                ]"
              >
                Mixtape
              </NuxtLink>
              
              <NuxtLink 
                to="/album" 
                @click="closeMobileMenu"
                :class="[
                  'block px-4 py-2 text-sm font-medium transition-colors hover:text-red-600',
                  isActiveRoute('/album') ? 'text-red-600' : 'text-gray-700'
                ]"
              >
                Album
              </NuxtLink>
              
              <NuxtLink 
                to="/artist" 
                @click="closeMobileMenu"
                :class="[
                  'block px-4 py-2 text-sm font-medium transition-colors hover:text-red-600',
                  isActiveRoute('/artist') ? 'text-red-600' : 'text-gray-700'
                ]"
              >
                Artist
              </NuxtLink>
              
              <NuxtLink 
                to="/about" 
                @click="closeMobileMenu"
                :class="[
                  'block px-4 py-2 text-sm font-medium transition-colors hover:text-red-600',
                  isActiveRoute('/about') ? 'text-red-600' : 'text-gray-700'
                ]"
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
     <div>
        <slot />
     </div>
</template>

<script setup>
import { ref } from 'vue'

const route = useRoute()
const isMobileMenuOpen = ref(false)

const isActiveRoute = (path) => {
  if (path === '/') {
    return route.path === '/'
  }
  return route.path.startsWith(path)
}

const toggleMobileMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value
}

const closeMobileMenu = () => {
  isMobileMenuOpen.value = false
}
</script>

<style scoped>

</style>