<script setup></script>

<template>
  <div class="reflection">
    <h1 class="green">Reflection</h1>
    <div class="paragraph">
      Although racial equality is now seen as some left-wing political correctness in American
      society, overt or covert racial discrimination has still not been reduced a lot. Reversely,
      following the right-wing Donald J. Trump’s re-election assisted by the white populist tide
      <a href="https://en.wikipedia.org/wiki/Make_America_Great_Again" target="_blank"
        >(Click for further information about "MAGA" movement)</a
      >, such a situation may become a bigger problem in the next three or five years, assisted by
      the potential
      <a href="https://en.wikipedia.org/wiki/Project_2025" target="_blank">"Project 2025"</a>. The
      government and society may make larger-scale and more systematic discriminations based on
      ethnicities on some specific ethnic minority groups (such as strictly restricting visa and
      legal immigrants, especially those from China and India).
    </div>
    <figure class="float-left trumpvance-pic">
      <img src="../assets/pic/trumpvance.jpg" alt="Trump and Vance" />
      <figcaption>Elected President Donald J. Trump and VP J. D. Vance</figcaption>
    </figure>
    <div class="paragraph">
      <h2>What do I hope readers learn from my Guide?</h2>
      This project was designed to be a resource that guides readers step-by-step in understanding
      and analyzing the civil rights of minority groups, from African Americans to Asian and Latino
      communities. I created this guide so that readers can learn the process of researching a topic
      closely related to ethnic minority groups and their social status. As members living in the
      United States, <b>no one can ignore this social problem</b>, especially when you are one
      individual among these minority groups.
    </div>
    <br />
    <div class="paragraph">
      <h2>What did I find challenging about composing in my chosen medium?</h2>
      Writing this guide as a digital guide, or resource, had its own challenges. Translating
      complex historical and social issues into the guide took filter-like selection and
      organization of content. One of the biggest challenges was presenting the information in a way
      that was <b>both thorough and engaging without overwhelming the reader</b>. I needed to
      balance the depth and clarity, especially when telling the readers how to find useful
      resources.
    </div>
    <br />
    <div class="paragraph">
      <h2>What new rhetorical or technological skills have I learned from this process?</h2>
      Throughout this development process, rhetorically, I learned how to adapt a scholarly approach
      into a more accessible format while maintaining somewhat academic rigor. I also became more
      familiar with digital tools and resources for academic research, such as archives and online
      databases, in the process of writing the guide.
    </div>
    <br />
    <div class="paragraph">
      <h2>How did I decide to create my Asset?</h2>
      When creating my original asset, a <b>“how-to” tutorial</b>, I reduced my topic covered from a
      comprehensive research process to some simple source selection steps. The process of deciding
      what to write and what to get rid of made the guide more readable and clear in content.
    </div>
    <br />
    <div class="paragraph">
      <h2>Why did I choose this Creative Commons license?</h2>
      I selected the Creative Commons BY-NC 4.0 license to ensure that this guide remains freely
      accessible for educational and non-commercial use while protecting the integrity of the
      content. Others can share, use, or even adapt and improve the guide based on current, but they
      cannot use it commercially. I believe this approach preserves the guide’s original message and
      academic rigor.
    </div>
  </div>
</template>

<style scoped>
.reflection {
  height: 100vh;
  margin-left: 8vw;
  margin-right: 8vw;
  text-align: justify;
}

h1 {
  font-weight: 800;
  font-size: 2.6rem;
  top: 10px;
  text-align: center;
  margin-bottom: 3%;
}

h2 {
  font-weight: 700;
  font-size: 22px;
  color: hsla(160, 100%, 37%, 1);
}

figcaption {
  font-size: 20px;
  font-weight: 600;
  text-align: center;
}

.float-left {
  float: left;
  margin: 3%;
  margin-left: 0;
}

.float-right {
  float: right;
  margin: 3%;
  margin-right: 0;
}

.trumpvance-pic img {
  width: 30vw;
}

a,
b {
  color: hsla(160, 100%, 37%, 1);
  font-weight: 600;
}

a {
  text-decoration: underline;
}

.paragraph {
  font-size: 20px;
  margin-bottom: 1%;
}

.reference {
  color: hsla(160, 100%, 37%, 1);
  cursor: pointer;
  text-decoration: underline;
}

.reference-popup {
  position: absolute;
  color: hsla(160, 100%, 37%, 1);
  transform: translate(-50%, -50%);
  background-color: rgba(0, 0, 0, 0.788);
  border: 1px solid #ccc;
  padding: 20px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  z-index: 1000;
  max-width: 40vw;
  max-height: 80vh;
  overflow-y: auto;
}

.reference-popup button {
  display: block;
  margin-left: auto;
  margin-bottom: 10px;
  background-color: hsla(160, 100%, 37%, 1);
  color: white;
  border: none;
  padding: 5px 10px;
  cursor: pointer;
}

.reference-content {
  font-size: 1rem;
  line-height: 1.5;
}

.reference-content a {
  color: #1e90ff;
  text-decoration: underline;
}
</style>

<script>
export default {
  name: 'reflectionComponent',
}
</script>
