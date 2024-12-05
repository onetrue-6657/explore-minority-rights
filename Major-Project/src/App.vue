<script setup>
import { ref } from 'vue'
import Greetings from './components/Greetings.vue'
import Introduction from './components/Introduction.vue'
import List from './components/List.vue'
import Tutorial from './components/Tutorial.vue'
import Reflection from './components/Reflection.vue'
import Footer from './components/Footer.vue'

const showIntro = ref(false)
const showLicense = ref(false)

const handleShowIntro = () => {
  showIntro.value = true
}

const scrollToSection = (sectionId) => {
  const section = document.getElementById(sectionId)
  if (section) {
    section.scrollIntoView({ behavior: 'smooth' })
    router.push(`/${sectionId}`)
  }
}

const handleShowLicense = () => {
  showLicense.value = !showLicense.value
}
</script>

<template>
  <div id="container">
    <section id="intro-page" class="intro-page">
      <div class="greet">
        <Greetings @show-intro="handleShowIntro" />
      </div>
      <div class="intro" :class="{ 'intro-visible': showIntro }">
        <Introduction />
      </div>
    </section>
    <section id="list" class="list">
      <List />
    </section>
    <section id="tutorial" class="tutorial">
      <Tutorial />
    </section>
    <section id="reflection" class="reflection">
      <Reflection />
    </section>
    <div class="nav-buttons">
      <button @click="scrollToSection('intro-page')">Intro</button>
      <button @click="scrollToSection('list')">List</button>
      <button @click="scrollToSection('tutorial')">Tutorial</button>
      <button @click="scrollToSection('reflection')">Reflection</button>
      <button
        id="showLicenseButton"
        @click="handleShowLicense()"
        :class="{ expanded: showLicense }"
      >
        CC License
      </button>
    </div>
    <div class="license" :class="{ 'license-visible': showLicense }">
      <Footer />
    </div>
  </div>
</template>

<style scoped>
#container {
  transition: transform 0.8s ease-in-out;
  display: flex;
  flex-direction: column;
  gap: 1;
}

section {
  width: 100%;
  align-items: center;
  justify-content: center;
  transition: transform 1.5s ease;
  margin-bottom: 10%;
}

.list {
  height: 200%;
  width: 80vw;
}

.tutorial {
  height: 150%;
  width: 80vw;
}

.reflection {
  height: 100%;
  width: 80vw;
}

.intro-page {
  display: flex;
  width: 120%;
  align-items: center;
  justify-content: space-between;
  height: 100vh;
  transition: transform 1.5s ease;
}

.greet {
  flex: 1;
  width: 100%;
  padding: 10px;
  align-items: center;
  justify-content: center;
  transition: flex 2s ease;
}

.intro {
  flex: 0;
  overflow: hidden;
  width: 100%;
  padding: 10px;
  height: auto;
  transition:
    flex 2s ease,
    height 3s ease;
}

.intro-visible {
  flex: 1.3;
  max-height: 80vh;
  opacity: 1;
  overflow-y: auto;
}

.license {
  position: fixed;
  bottom: 20px;
  right: -300%;
  text-align: center;
  font-size: 0.8rem;
  transform: translateX(-50%);
  width: 70%;
  background-color: rgba(0, 0, 0, 0.8);
  color: white;
  padding: 10px;
  border-radius: 5px;
  transition: transform 1.2s ease;
}

.license-visible {
  transform: translateX(-450%);
}

.nav-buttons {
  position: fixed;
  bottom: 20px;
  right: 20px;
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.nav-buttons button {
  font-size: 0.85rem;
  background-color: #ba0c2f;
  color: white;
  border: none;
  padding: 10px 20px;
  cursor: pointer;
  border-radius: 5px;
  transition:
    background-color 0.5s ease,
    transform 0.5s ease;
}

.nav-buttons button:hover {
  background-color: #c61f40;
  transform: scale(1.05);
}

/* @media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
} */
</style>
