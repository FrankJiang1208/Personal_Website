<template>
  <div class="bg-black h-screen px-6 py-12">
    <h2
      class="text-white font-exo text-5xl opacity-0"
      ref="title"
      style="transform: translateY(30px)"
    >
      ABOUT ME
    </h2>

    <div class="flex space-x-4">
      <div ref="projects" v-for='project in projects' class="w-full opacity-0" style="transform: translateX(30px)">
          <a :href="project.link.url">
          <img
            :src="project.image.url"
            alt="iPhone"
            style="height: 70vh;"
            class="object-cover"
          />
          </a>
          <p class="text-white font-mono text-sm">{{ project.title }}</p>
      </div>
    </div>
  </div>
</template>

<script>
import gsap from 'gsap'
import iphoneImg from '~/assets/code.jpg'
import laptopImg from '~/assets/geo.jpg'
import personImg from '~/assets/mac.jpg'
export default {
  data() {
    return {
      projects: [
        {
          link:{url: 'http://project3-us-job-market-analysis.azurewebsites.net/'},
          image: {
            url: iphoneImg
          },
          title: 'Projects'
        },
        {
          link:{url: 'https://github.com/FrankJiang1208'},
         
          image: {
            url: laptopImg
          },
          title: 'Experience'
        },
        {
          
          link:{url: 'https://www.linkedin.com/in/shan-jiang-3a221313a'},
          image: {
            url: personImg
          },
          title: 'About Me'
        },
      ]
    }
  },
  mounted() {
    gsap.to(this.$refs.title, {
      opacity: 1,
      duration: 1.5,
      y: 0,
      ease: 'expo'
    })

    gsap.to(this.$refs.projects, {
      opacity: 1,
      duration: 1.5,
      stagger: 0.1,
      x: 0,
      ease: 'expo',
      delay: 0.2
    })
  }
}
</script>
