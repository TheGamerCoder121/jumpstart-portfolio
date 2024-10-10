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
  <div>
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
              I&apos;m a <span class="font-bold">passionate computer science student.</span>
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

    <!-- About Me Start -->
    <div class="max-w-[85rem] px-4 py-4 mx-auto sm:px-6 lg:px-8 my-10">
        <div class="grid grid-cols-1 md:grid-cols-2 gap-10">
          <!-- {/* Console */} -->
          <div class="terminal p-6 rounded-lg w-full max-w-4xl mx-auto my-4">
            <div class="flex space-x-2 mb-4">
              <div class="w-3 h-3 rounded-full bg-red-500" />
              <div class="w-3 h-3 rounded-full bg-yellow-400" />
              <div class="w-3 h-3 rounded-full bg-green-500" />
            </div>
            <div class="">
              <p class="text-green-400">
                Last login: {formatUTCDate(new Date()).toString()} on ttys000
              </p>
              <p class="text-white">
                hello@floskhosting ~ % ssh user@example-dedicated-server.com
              </p>
              <p class="text-gray-400">
                Welcome to Ubuntu 20.04.1 LTS (GNU/Linux 5.4.0-42-generic
                x86_64)
              </p>
              <p class="text-gray-400">
                {" "}
                * Documentation: https://help.ubuntu.com
              </p>
              <p class="text-gray-400">
                {" "}
                * Management: https://landscape.canonical.com
              </p>
              <p class="text-gray-400">
                {" "}
                * Support: https://ubuntu.com/advantage
              </p>
              <p class="text-gray-400">
                System information as of {formatUTCDate(new Date()).toString()}
                <br />
                System load: 0.0 Processes: 123
                <br />
                Usage of /: 13.5% of 29.76GB Users logged in: 1<br />
                Memory usage: 35% IP address for eth0: 192.168.1.10
                <br />
                Swap usage: 0%
              </p>
              <p class="text-white">
                Last login: Mon Mar 25 09:01:15 2024 from 192.168.1.20
              </p>
              <p class="text-white">
                user@example-dedicated-server:~$ uptime
              </p>
              <p class="text-gray-200">
                {" "}
                09:16:01 up 1:10, 2 users, load average: 0.00, 0.01, 0.05
              </p>
              <p class="text-white">
                user@example-dedicated-server:~$ logout
              </p>
              <p class="text-green-400">
                Connection to example-dedicated-server.com closed.
              </p>
              <p class="text-green-400">hello@floskhosting ~ %</p>
            </div>
          </div>

          <!-- {/* Features */} -->
          <div class="flex items-center justify-center flex-col">
            <p class="font-normal mt-5 text-4xl text-stone-50">
              I&apos;m Nicklaus Vega, an aspiring entrepreneur and computer science student with over 5 years of experience in the tech world. With a passion for machine learning, frontend/backend development, and graphic design, I&apos;m committed to learning, growing, and applying my skills to impactful projects.
            </p>
          </div>
        </div>
      </div>
  </div>
</template>