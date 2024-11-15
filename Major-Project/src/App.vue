<script setup>
import { ref } from 'vue';
import Greetings from './components/Greetings.vue';
import Introduction from './components/Introduction.vue';

const showIntro = ref(false);

const handleMouseEnter = () => {
  showIntro.value = true;
};

</script>

<template>
  <div class="intro-page">
      <div @mouseclick = "handleMouseEnter" class="greet">
        <Greetings />
      </div>
      <div class="intro" :class="{ 'intro-visible': showIntro}">
        <Introduction />
      </div> 
  </div>
</template>

<style scoped>
.intro-page {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 200%;
  height: 100vh;
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
  max-height: 100vh;
  transition: flex 2.0s ease, max-height 3.0s ease;
}

.intro-visible {
  flex: 1.3;
  max-height: 80vh;
  opacity: 1;
  overflow-y: auto;
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
