<script setup>
import HelloWorld from './components/HelloWorld.vue'
import Introduction from './components/Introduction.vue';
</script>

<template>
  <div class="intro-page">
      <div class="wrapper">
        <HelloWorld />
      </div>
      <div class="intro">
        <Introduction />
      </div> 
  </div>
</template>

<style scoped>
.intro-page {
  display: flex;
  justify-content: space-between;
  width: 200%;
}

.wrapper {
  flex: 1;
  padding: 10px;
}

.intro {
  flex: 1;
  padding: 10px;
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
