<script setup>
import { ref, nextTick } from 'vue'
const references = ref({
  1: "1.	“Mapping Police Violence” <i>Mapping Police Violence.</i> <a href='https://mappingpoliceviolence.org/' target='_blank'>https://mappingpoliceviolence.org/</a>. Accessed 14 Nov. 2024.",
  2: "2.	“Hate Crime Data: The Value of Expanding Our Sources.” <i>USA Facts</i>, <a href='https://usafacts.org/articles/hate-crime-data-value-expanding-our-sources/' target='_blank'>https://usafacts.org/articles/hate-crime-data-value-expanding-our-sources/</a>. Accessed 14 Nov. 2024.",
  3: "3.	2022 Hate Crime Statistics. <i>U.S. Department of Justice</i>, <a href='https://www.justice.gov/crs/highlights/2022-hate-crime-statistics/' target='_blank'>https://www.justice.gov/crs/highlights/2022-hate-crime-statistics/</a>. Accessed 14 Nov. 2024.",
  4: "4.  Hate Crime Statistics. <i>U.S. Department of Justice</i>, <a href='https://www.justice.gov/hatecrimes/hate-crime-statistics/' target='_blank'>https://www.justice.gov/hatecrimes/hate-crime-statistics/</a>. Accessed 14 Nov. 2024.",
})

const showReference = ref(null)
const referencePosition = ref({ top: 0, left: 0 })

const handleReferenceClick = (id, event) => {
  showReference.value = id
  nextTick(() => {
    const spanRect = event.target.getBoundingClientRect()
    referencePosition.value = {
      top: spanRect.top + window.scrollY - 10,
      left: spanRect.left + window.scrollX,
    }
  })
}

const closeReference = () => {
  showReference.value = null
}
</script>

<template>
  <div class="intro">
    <p>
      Welcome to the research community focusing on minority group civil rights in U.S. society!
      This digital research website will introduce you the different resources, ideas, and a
      tutorial on this attractive research topic.
    </p>
    <br />
    <p>
      This guide is based on my own experience with this topic in previous research. In my previous
      two research, I focused on the civil rights movement and the black powers movement. Both
      movements were milestones in the history of black people in the U.S., which gave them civil
      rig hts and helped them establish a collective self-identity as an ethnic minority group.
    </p>
    <br />
    <p>
      As a result, this website will be a guide or tutorial-oriented resource for the research
      community of those who are interested in researching American minority groups. It is not
      enough to only focus on black people nowadays. After hundreds of years of migration, the
      diversity of American ethnicities has been up to a height that it has never been. East Asians,
      Mideast people, Indians, and Hispanos, have become more and more significant powers that
      cannot be ignored in American society.
    </p>
    <br />
    <p>
      However, even 160 years after the Civil War, 60 years after the civil rights movement, racism
      and discrimination still widely exist here in the U.S. People are still often discriminated
      against or abused only because of their ethnicity. Violence is still one of the largest
      problems here. White supremacy, extended to ethnic supremacy, still exists and is hard to get
      rid of from society due to its deep historical roots in this nation. This can be observed from
      the social incidents and political events during these years. Black people, the second largest
      ethnic group in the U.S., are the most likely to die due to police violence.<span
        class="reference"
        @click="handleReferenceClick(1, $event)"
        >[1]</span
      >
      They have far higher data recorded as a ratio to be killed than other ethnicities. Among all
      hate crimes in the U.S., which reached a new peak in 2023, 52% percent were due to race and
      ethnicity.<span class="reference" @click="handleReferenceClick(2, $event)">[2]</span
      ><span class="reference" @click="handleReferenceClick(3, $event)">[3]</span
      ><span class="reference" @click="handleReferenceClick(4, $event)">[4]</span>
    </p>
    <br />
    <p>
      Ethnicity minority groups have already broken some of the chains from a general and law aspect
      in the society, and now it is a huge topic to practice them in actions. This is what this
      tutorial wants to do – research the past and current situation, giving advice for a better
      future of ethnic equity in the melting pot of U.S. society.
    </p>
    <div
      v-if="showReference"
      class="reference-popup"
      :style="{
        top: `${referencePosition.top - 50}px`,
        left: `${referencePosition.left}px`,
      }"
    >
      <div class="reference-content">
        <p v-html="references[showReference]"></p>
        <button @click="closeReference">Close</button>
      </div>
    </div>
  </div>
</template>

<style scoped>
p {
  font-size: 20px;
}

.reference {
  color: #ba0c2f;
  cursor: pointer;
  text-decoration: underline;
}

.reference-popup {
  position: absolute;
  color: #ba0c2f;
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
  background-color: #ba0c2f;
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
  name: 'IntroductionComponent',
}
</script>
