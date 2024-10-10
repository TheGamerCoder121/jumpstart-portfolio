<script setup lang="ts">
import { Vue3Lottie } from 'vue3-lottie'
import { ref } from 'vue';

interface SocialMediaProfile {
  name: string;
  icon: string;
  url: string;
}

const socialMediaProfiles = ref<SocialMediaProfile[]>([
  {
    name: 'GitHub',
    icon: 'cib:github',
    url: 'https://github.com/TheGamerCoder121',
  },
  {
    name: 'LinkedIn',
    icon: 'cib:linkedin',
    url: 'https://www.linkedin.com/in/nicklaus-vega',
  },
  // Add more profiles as needed
]);
</script>

<template>
  <!-- Hero Start -->
  <div class="container mx-auto text-white p-4 md:p-10">
    <NuxtImg src="/jumpstart-logo-white.png" />
    <!-- Hero Text section -->
    <div class="flex flex-col md:flex-row mt-40 sm:mt-0">
      <!-- Left Column: Text -->
      <div class="flex-1 flex flex-col items-center md:items-start justify-center md:justify-center">
        <div class="text-center md:text-left">
          <h1 class="text-4xl md:text-7xl font-bold">Nicklaus Vega</h1>
          <p class="text-lg md:text-xl mt-4">
            I'm a <span class="font-bold">passionate computer science student.</span>
          </p>
          <div class="mt-4 flex justify-center md:justify-start space-x-4">
            <a v-for="profile in socialMediaProfiles" :key="profile.name" :href="profile.url" target="_blank"
              rel="noopener noreferrer">
              <Icon :size="40" :name="profile.icon" />
            </a>
          </div>
        </div>
      </div>
      <!-- Right Column: Lottie Animation -->
      <div class="hidden md:flex items-end justify-center">
        <client-only>
          <Vue3Lottie animationLink="https://lottie.host/26a6d4fe-e84a-4b70-bc88-dc291abdc279/H5MxkJu7qy.json"
            :height="600" :width="600" />
        </client-only>
      </div>
    </div>
  </div>
  <!-- Hero End -->
</template>