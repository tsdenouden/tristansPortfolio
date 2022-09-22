<script setup>
import { ref } from '@vue/reactivity'

document.title = "Tristan's Portfolio"

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
  <div class="sticky_header">
    <div class="header">
      <div class="name">
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
          <a href="#contact">
            contact.
          </a>
        </div>
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
        <a href="#projects" class="projs">Projects</a>
      </div>
    </div>

    <!-- Image -->
    <div class="portrait">
      <img src="" class="portrait_photo" alt="">
    </div>
  </div>

  <div id="projects">
    <h1>Projects.</h1>
    <div id="projects_container">
      <projectsContainer />
    </div>
  </div>

  <div class="edu">
    <eduContainer />
    <certsContainer />
  </div>

  <div id="contact">
    <contactFooter :heading="heading" :email="gmail" />
  </div>

</template>

<style scoped>
/* Header/navbar */
/* Make header sticky */
.sticky_header {
  position: fixed;
  top: 0;
  width: 100%;
  z-index: 1;
}

.header {
  display: flex;
  justify-content: space-between;
  background-color: rgba(255, 255, 255, 0.9);
  backdrop-filter: blur(2px);
  padding: 20px;
}

.header > .name {
  font-size: 20px;
  font-weight: bold;
}

.header > .links {
  display: flex;
}

.links > .nav-item > a {
  color: darkcyan;
  font-weight: bold;
  text-decoration: none;
  margin-left: 20px;
}


/* Main top section including bio & portrait photo */
.main {
  display: flex;
  flex-direction: row;
  align-items: end;
  justify-content: between;
  width: 100%;
  height: 100vh;
  background-image: linear-gradient(to right, white, lightcyan);
}


/* Bio, info & link to projects */
.bio {
  display: flex;
  flex-direction: column;
  width: 50vw;
  height: 40vh;
  margin-inline: 30px;
}

.bio > .name {
  font-size: 40px;
  font-weight: bold;
}

.bio > .subtitle {
  font-size: 20px;
  font-weight: bold;
  color: darkcyan;
  margin-bottom: 10px;
}

.bio > .aboutme {
  color: darkslategray;
  overflow: auto;
}

.bio > .proj_button {
  margin: 5px;
  margin-top: 30px;
}

/* Project button */
.proj_button > .projs {
  color: darkslategray;
  font-size: 20px;
  font-weight: bold;
  text-decoration: none;
  background-color: lightcyan;
  border: 3px solid cyan;
  border-radius: 15px 50px;
  padding: 8px 20px 8px 20px;
  transition-duration: 300ms;
  transition-timing-function: ease-in-out;
}

.proj_button > .projs:hover {
  background-color: cyan;
  border: 3px solid lightcyan;
}

/* Projects section */
#projects > h1 {
  font-size: 50px;
  margin-left: 30px;
  padding-top: 125px;
}

#projects > #projects_container {
  margin-inline: 40px;
}
</style>