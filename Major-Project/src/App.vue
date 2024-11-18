<script setup>
import { ref } from 'vue';
import Greetings from './components/Greetings.vue';
import Introduction from './components/Introduction.vue';
import List from './components/List.vue';

const showIntro = ref(false);

const handleShowIntro = () => {
  showIntro.value = true;
};
</script>

<template>
    <div id="container">
      <div class="section intro-page">
        <div class="greet">
          <Greetings @show-intro="handleShowIntro" />
        </div>
        <div class="intro" :class="{ 'intro-visible': showIntro }">
          <Introduction />
        </div> 
      </div>
      <div class="section list">
        <List />
      </div>
    </div>
</template>

<style scoped>
#container {
  transition: transform 0.8s ease-in-out;
}

.section {
  width: 200%;
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: transform 1.5s ease;
}

.intro-page {
  display: flex;
  width: 200%;
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
  transition: flex 2.0s ease;
}

.intro {
  flex: 0;
  overflow: hidden;
  width: 100%;
  padding: 10px;
  height: 100vh;
  transition: flex 2.0s ease, max-height 3.0s ease;
}

.intro-visible {
  flex: 1.3;
  max-height: 80vh;
  opacity: 1;
  overflow-y: auto;
}

.list {
  height: 80%;
  overflow-y: auto;
  margin-bottom: 10%;
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
