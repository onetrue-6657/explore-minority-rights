<script setup>
</script>

<template>
  <div class="greetings">
    <h1 class="green" >A Research Guide Into <br> Ethnic Minority Groups</h1>
    <h3>By Zheng Ni</h3>
    <button>Introduction -></button>
  </div>
</template> 

<style scoped>
.greetings {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  height: 100vh;
}

h1 {
  font-weight: 800;
  font-size: 2.6rem;
  top: 10px;
}

button {
  color: hsla(160, 100%, 37%, 1);
  font-weight: 700;
  font-size: 2rem;
  margin-top: 2%;
  background: none;
  border: none;
  cursor: pointer;
  padding-bottom: 8px;
  position: relative;
}

button::after {
  content: '';
  position: absolute;
  left: 0;
  bottom: 0;
  width: 0;
  height: 6px;
  
  background-color: hsla(160, 100%, 37%, 1); 
  transition: width 1.2s ease; 
}

button:hover::after {
  width: 100%;
}

h3 {
  font-weight: 600;
  font-size: 1.5rem;
  margin-top: 1%;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: center;
  }
}
</style>

<script>
export default {
  name: 'GreetingsComponent'
}
</script>