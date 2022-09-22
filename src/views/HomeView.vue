<script setup>
import { ref } from '@vue/reactivity'

// containers
import projectsContainer from '../components/containers/projectsContainer.vue'
import eduContainer from '../components/containers/eduContainer.vue'
import certsContainer from '../components/containers/certsContainer.vue'

// footer
import contactFooter from '../components/footer/contactFooter.vue'
const gmail = ref('trisdo687@gmail.com')
const heading = ref('Contact')
</script>

<template>
  <!-- Header & nav bar -->
  <div class="header">
    <div>
      tristan.
    </div>
    <!-- Links -->
    <div class="links">
      <div class="nav-item">
        <a href="" target="_blank" rel="noopener noreferrer">
          github.
        </a>
      </div>
      <div class="nav-item">
        <a href="" target="_blank" rel="noopener noreferrer">
          behance.
        </a>
      </div>
      <div class="nav-item">
        <a href="" target="_blank" rel="noopener noreferrer">
          contact.
        </a>
      </div>
    </div>
  </div>

  <!-- Top section: info about me & portrait -->
  <div class="main">

    <!-- Bio -->
    <div class="bio">
      <div class="name">
        Tristan Shawn den Ouden
      </div>
      <div class="subtitle">
        aspiring software engineer based in Flevoland, Netherlands.
      </div>
      <div class="aboutme">
        Currently an A levels student at LearnNow Distance Learning College. 
        I'm interested in web technologies, app development, science, music, 
        UI/UX & developer tools. I aim to deepen my understanding in various 
        areas of technology & product development.
      </div>
      <div class="proj_button">
        <a href="" class="projs" target="_blank" rel="noopener noreferrer">Projects</a>
      </div>
    </div>

    <!-- Image -->
    <div class="portrait">
      <img src="" class="portrait_photo" alt="">
    </div>
  </div>

  <div class="projects">
    <h1>Projects.</h1>
    <projectsContainer />
  </div>

  <div class="edu">
    <eduContainer />
    <certsContainer />
  </div>

  <div>
    <contactFooter :heading="heading" :email="gmail" />
  </div>

</template>