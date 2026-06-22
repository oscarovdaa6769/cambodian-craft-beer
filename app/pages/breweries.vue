<script setup>
import { ref } from 'vue'

const brewery = ref(
  Array(9).fill(null).map((_, index) => ({
    id: index + 1,
    name: 'SAK PUB',
    since: 'SINCE 2021',
    description: 'Serving handcrafted small batch beers in a welcoming atmosphere since 2021',
    logo: '/assets/images/sakpub.png', 
    facebookUrl: 'https://facebook.com',
    mapUrl: 'https://maps.google.com'
  }))
)

const breweries = ref([
  {
    logo: '/assets/images/sakpub.png',
    name: 'SAK PUB',
    since: 'SINCE 2021',
    description: 'Serving handcrafted small batch beers in a welcoming atmosphere since 2021',
    facebookUrl: 'https://www.facebook.com/SakPubCraftBeerBites',
  },
  {
    logo: '/assets/images/sakpub.png',
    name: 'SAK PUB',
    since: 'SINCE 2021',
    description: 'Serving handcrafted small batch beers in a welcoming atmosphere since 2021',
    facebookUrl: 'https://www.facebook.com/SakPubCraftBeerBites',
  },
  {
    logo: '/assets/images/sakpub.png',
    name: 'SAK PUB',
    since: 'SINCE 2021',
    description: 'Serving handcrafted small batch beers in a welcoming atmosphere since 2021',
    facebookUrl: 'https://www.facebook.com/SakPubCraftBeerBites',
  },
  {
    logo: '/assets/images/sakpub.png',
    name: 'SAK PUB',
    since: 'SINCE 2021',
    description: 'Serving handcrafted small batch beers in a welcoming atmosphere since 2021',
    facebookUrl: 'https://www.facebook.com/SakPubCraftBeerBites',
  },
  {
    logo: '/assets/images/sakpub.png',
    name: 'SAK PUB',
    since: 'SINCE 2021',
    description: 'Serving handcrafted small batch beers in a welcoming atmosphere since 2021',
    facebookUrl: 'https://www.facebook.com/SakPubCraftBeerBites',
  },
  {
    logo: '/assets/images/sakpub.png',
    name: 'SAK PUB',
    since: 'SINCE 2021',
    description: 'Serving handcrafted small batch beers in a welcoming atmosphere since 2021',
    facebookUrl: 'https://www.facebook.com/SakPubCraftBeerBites',
  },
  {
    logo: '/assets/images/sakpub.png',
    name: 'SAK PUB',
    since: 'SINCE 2021',
    description: 'Serving handcrafted small batch beers in a welcoming atmosphere since 2021',
    facebookUrl: 'https://www.facebook.com/SakPubCraftBeerBites',
  },
  {
    logo: '/assets/images/sakpub.png',
    name: 'SAK PUB',
    since: 'SINCE 2021',
    description: 'Serving handcrafted small batch beers in a welcoming atmosphere since 2021',
    facebookUrl: 'https://www.facebook.com/SakPubCraftBeerBites',
  },
  {
    logo: '/assets/images/sakpub.png',
    name: 'SAK PUB',
    since: 'SINCE 2021',
    description: 'Serving handcrafted small batch beers in a welcoming atmosphere since 2021',
    facebookUrl: 'https://www.facebook.com/SakPubCraftBeerBites',
  },
])
</script>

<template>
  <div class="bg-background min-h-screen flex flex-col justify-between">
    <main class="mx-auto w-full my-10 flex-grow px-4 lg:px-[60px]">
      
      <div class="text-center mb-10">
        <h1 class="font-header text-primary text-4xl uppercase tracking-wider mb-2">
          Breweries
        </h1>
        <p class="font-primary text-context text-sm max-w-2xl mx-auto">
          Discover the best craft breweries in Cambodia.
        </p>
      </div>

      <div class="breweries-grid">
        
        <div 
          v-for="pub in breweries"  
          class="bg-card rounded-xl p-5 flex flex-col justify-between gap-5"
        >
          <div class="flex gap-4 items-start">
            <div class="w-[40%] flex items-center justify-start bg-background p-[10px] rounded-[10px]">
              <img :src="pub.logo" :alt="pub.name" class="max-h-full max-w-full object-contain" />
            </div>

            <div class="flex flex-col gap-[7px] text-left w-[100%]">
              <h2 class="font-header text-primary text-[25px] uppercase tracking-wide">
                {{ pub.name }}
              </h2>
              
              <div class="flex items-center gap-[15px] bg-white border border-gray-200 text-header font-header text-[11px] p-[7px] rounded-[10px] self-start">
                <Icon name="solar:calendar-minimalistic-bold-duotone" size="25px" class="text-primary" />
                <span>{{ pub.since }}</span>
              </div>

              <p class="font-primary text-context text-[15px] leading-relaxed mt-1">
                {{ pub.description }}
              </p>
            </div>
          </div>

          <div class="buttons-grid font-header text-[11px] tracking-wide">
            <a 
              :href="pub.facebookUrl" 
              target="_blank" 
              class="bg-white hover:bg-neutral-50 border border-gray-100 text-header rounded-lg p-[7px] flex items-center justify-center gap-1.5 transition-colors"
            >
              <Icon name="solar:link-circle-bold-duotone" size="25px" class="text-primary" />
              <span>Facebook</span>
            </a>
            
            <a 
              :href="pub.mapUrl" 
              target="_blank" 
              class="bg-white hover:bg-neutral-50 border border-gray-100 text-header rounded-lg p-[7px] flex items-center justify-center gap-1.5 transition-colors"
            >
              <Icon name="solar:map-point-bold-duotone" size="25px" class="text-primary" />
              <span>Map</span>
            </a>
          </div>

        </div>

      </div>
    </main>

    <footer class="bg-primary text-text-accent text-center py-4 text-xs md:text-sm font-primary w-full">
      © CBAC — Cambodian Craft Beer Association • Event: 16 August 2025 • Botanico Craft Beer Garden
    </footer>
  </div>
</template>

<style scoped>
/* Fallback standard CSS styles to bypass compilation limits */
.breweries-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 24px;
  width: 100%;
}

@media (min-width: 768px) {
  .breweries-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 1280px) {
  .breweries-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}

.buttons-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 12px;
}
</style>