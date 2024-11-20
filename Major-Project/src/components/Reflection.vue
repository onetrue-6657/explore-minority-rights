<script setup></script>

<template>
  <div class="reflection">
    <h1 class="green">Reflection</h1>
    <div class="paragraph">
      Although racial equality is now seen as some left-wing political correctness in American
      society, overt or covert racial discrimination has still not been reduced a lot. Reversely,
      following the right-wing Donald J. Trump’s re-election assisted by the white populist tide,
      such a situation may become a bigger problem in the next three or five years. The government
      and society may make larger-scale and more systematic discriminations based on ethnicities on
      some specific ethnic minority groups.
    </div>
    <br />
    <div class="paragraph">
      This project was designed to be a resource that guides readers step-by-step in understanding
      and analyzing the civil rights of minority groups, from African Americans to Asian and Latino
      communities. I created this guide so that readers can learn the process of researching a topic
      closely related to ethnic minority groups and their social status. As members living in the
      United States, no one can ignore this social problem, especially when you are one individual
      among these minority groups.
    </div>
    <br />
    <div class="paragraph">
      Writing this guide as a digital guide, or resource, had its own challenges. Translating
      complex historical and social issues into the guide took filter-like selection and
      organization of content. One of the biggest challenges was presenting the information in a way
      that was both thorough and engaging without overwhelming the reader. I needed to balance the
      depth and clarity, especially when telling the readers how to find useful resources.
    </div>
    <br />
    <div class="paragraph">
      Throughout this development process, rhetorically, I learned how to adapt a scholarly approach
      into a more accessible format while maintaining somewhat academic rigor. I also became more
      familiar with digital tools and resources for academic research, such as archives and online
      databases, in the process of writing the guide.
    </div>
    <br />
    <div class="paragraph">
      When creating my original asset, a “how-to” tutorial, I reduced my topic covered from a
      comprehensive research process to some simple source selection steps. The process of deciding
      what to write and what to get rid of made the guide more readable and clear in content.
    </div>
    <br />
    <div class="paragraph">
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
}

h1 {
  font-weight: 800;
  font-size: 2.6rem;
  top: 10px;
  text-align: center;
  margin-bottom: 3%;
}

.paragraph {
  word-wrap: break-word;
  font-size: 20px;
  overflow-y: auto;
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
