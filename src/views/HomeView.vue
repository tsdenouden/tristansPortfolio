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
  <div class="sticky-header">
    <div class="header-wrapper">
      <div class="header-name">
        tristan.
      </div>
      <!-- Links -->
      <div class="header-links">
        <div class="link-item">
          <a href="https://github.com/tsdenouden" target="_blank" rel="noopener noreferrer">
            github.
          </a>
        </div>
        <div class="link-item">
          <a href="https://www.behance.net/tristandenouden" target="_blank" rel="noopener noreferrer">
            behance.
          </a>
        </div>
        <div class="link-item">
          <a href="https://www.youtube.com/channel/UCFtJ-g7eYrA9LUcaSOiBBBA" target="_blank" rel="noopener noreferrer">
            youtube.
          </a>
        </div>
        <div class="link-item">
          <a href="#contact-footer">
            contact.
          </a>
        </div>
      </div>
    </div>
  </div>

  <!-- Top section: info about me & portrait -->
  <div class="info-wrapper">

    <!-- Bio -->
    <div class="bio-wrapper">
      <div class="bio-name">
        Tristan Shawn den Ouden
      </div>
      <div class="bio-subtitle">
        aspiring software engineer based in Flevoland, Netherlands.
      </div>
      <div class="bio-about">
        Currently an A levels student at LearnNow Distance Learning College. 
        I'm interested in web technologies, app development, science, music, 
        UI/UX & developer tools. I aim to deepen my understanding in various 
        areas of technology & product development.
      </div>
      <div class="projects-button-wrapper">
        <a href="#projects-wrapper" class="projects-button">Projects</a>
      </div>
    </div>

    <!-- Image -->
    <div class="info-portrait">
      <img src="../assets/pic/tristan.png" class="portrait-img" alt="">
    </div>
  </div>

  <div id="projects-wrapper">
    <h1>Projects.</h1>
    <div id="projects-list">
      <projectsContainer />
    </div>
  </div>

  <div class="edu-section">
    <div class="edu-list">
      <span class="edu-title">Education.</span>
      <eduContainer />
      <span class="edu-hr">Certificate courses.</span>
      <certsContainer />
    </div>
    <div class="edu-img">
      <img src="../assets/pic/compimg.jpg" alt="Me sitting at the computer.">
    </div>
  </div>

  <div id="contact-footer">
    <contactFooter :heading="heading" :email="gmail" />
  </div>

</template>

<style scoped>
/* Header/navbar */
/* Make header sticky */
.sticky-header {
  position: fixed;
  top: 0;
  width: 100%;
  z-index: 1;
}

.header-wrapper {
  display: flex;
  justify-content: space-between;
  background-color: rgba(255, 255, 255, 0.9);
  backdrop-filter: blur(2px);
  padding: 20px;
}

.header-name {
  font-size: 20px;
  font-weight: bold;
  margin-left: 20px;
}

.header-links {
  display: flex;
}

.header-links > .link-item > a {
  color: darkcyan;
  font-weight: bold;
  text-decoration: none;
  margin-inline: 20px;
}

@media all and (max-width: 1200px) {
  .sticky-header {
    display: none;
  }
}


/* Main top section including bio & portrait photo */
.info-wrapper {
  display: flex;
  width: 100%;
  height: 100vh;
  background-image: linear-gradient(to right, white, lightblue);
}

.info-portrait {
  transform: translate(0, 15vh);
}

.info-portrait > img {
  width: 100%;
  height: auto;
}

@media all and (max-width: 1800px) {
  .info-portrait {
    transform: translate(0, 25vh);
  }
}

@media all and (max-width: 1200px) {
  .info-wrapper {
    flex-direction: column;
    justify-content: center;
    height: 100%;
    padding-top: 60px;
  }

  .info-portrait {
    transform: translate(0, 0);
  }
}


/* Bio, info & link to projects */
.bio-wrapper {
  display: flex;
  flex-direction: column;
  transform: translate(0, 50vh);
  margin-left: 100px;
}

.bio-name {
  font-size: 3vw;
  font-weight: bold;
}

.bio-subtitle {
  font-size: 1.75vw;
  font-weight: bold;
  color: darkcyan;
  margin-bottom: 10px;
}

.bio-about {
  font-size: 1vw;
  color: darkslategray;
}

.bio-wrapper > .projects-button-wrapper {
  margin: 5px;
  margin-top: 30px;
}

@media all and (max-width: 1800px) {
  .bio-wrapper {
    transform: translate(0, 35vh);
  }

  .bio-name {
    font-size: 4vw;
  }

  .bio-subtitle {
    font-size: 2vw;
    margin-bottom: 10px;
  }

  .bio-about {
    font-size: 1.5vw;
  }
}

@media all and (max-width: 1200px) {
  .bio-wrapper {
    margin-inline: 40px;
    transform: translate(0, 0);
  }
  
  .bio-name {
    font-size: 50px;
  }

  .bio-subtitle {
    font-size: 25px;
    margin-bottom: 10px;
  }

  .bio-about {
    font-size: 18px;
  }

  .bio-wrapper > .projects-button-wrapper {
    text-align: center;
  }
}

/* Projects button */
.projects-button-wrapper > .projects-button {
  color: darkslategray;
  font-size: 1.5vw;
  font-weight: bold;
  text-decoration: none;
  background-color: lightcyan;
  border: 3px solid cyan;
  border-radius: 15px 50px;
  padding: 8px 20px 8px 20px;
  transition-duration: 300ms;
  transition-timing-function: ease-in-out;
}

.projects-button-wrapper > .projects-button:hover {
  background-color: cyan;
  border: 3px solid lightcyan;
}

@media all and (max-width: 1200px) {
  .projects-button-wrapper > .projects-button {
    font-size: 30px;
  }
}


/* Projects section */
#projects-wrapper > h1 {
  font-size: 50px;
  margin-left: 30px;
  padding-top: 125px;
}

#projects-wrapper > #projects-list {
  margin-inline: 40px;
}

@media all and (max-width: 1200px) {
  #projects-wrapper > h1 {
    font-size: 40px;
    padding-top: 30px;
  }

  #projects-wrapper > #projects-list {
    margin-inline: 10px;
  }
}


/* Education */
.edu-section {
  display: flex;
  align-items: center;
}

.edu-list {
  display: flex;
  flex-direction: column;
  width: 40%;
  padding-left: 50px;
  padding-right: 30px;
}

.edu-list > .edu-title {
  font-size: 50px;
  font-weight: bold;
  padding-top: 20px;
  margin-bottom: 50px;
}

.edu-hr {
  font-size: 25px;
  font-weight: bold;
  text-decoration: underline;
  margin-top: 15px;
  margin-bottom: 30px;
}

.edu-img {
  width: 100%;
  height:100%;
  object-fit: cover;
  overflow: hidden;
}

.edu-img > img {
  width: 100%;
  height: auto;
}

@media all and (max-width: 1800px) {
  .edu-img {
    width: 50%;
  }
}

@media all and (max-width: 1200px) {
  .edu-img {
    display: none;
  }

  .edu-list {
    width: 90%;
    margin-left: 20px;
    padding-right: 0px;
  }

  .edu-list > .edu-title {
    font-size: 50px;
    padding-top: 10px;
  }

  .edu-hr {
    font-size: 30px;
  }
}


/* Footer */
#contact-footer {
  margin-top: 50px;
  margin-inline: 40px;
}

@media all and (max-height: 800px) {
  #contact-footer {
    margin-top: 100px;
    margin-inline: 40px;
  }
}

@media all and (max-height: 600px) {
  #contact-footer {
    margin-top: 200px;
    margin-inline: 40px;
  }
}
</style>