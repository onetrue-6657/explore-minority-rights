<script setup>
import { ref, nextTick } from 'vue'

const references = ref({
  5: "5.	“Asian American and Pacific Islander Records.” <i>National Archives</i>, <a href='https://www.archives.gov/research/aapi' target='_blank'>https://www.archives.gov/research/aapi</a>. Accessed 14 Nov. 2024.",
  6: "6.	“Hispanic Heritage Records.” <i>National Archives</i>, <a href='https://www.archives.gov/research/hispanic' target='_blank'>https://www.archives.gov/research/hispanic</a>. Accessed 14 Nov. 2024.",
  7: "7.	“African American Records.” <i>National Archives</i>, <a href='https://www.archives.gov/research/african-americans' target='_blank'>https://www.archives.gov/research/african-americans</a>. Accessed 14 Nov. 2024.",
  8: "8.	“The American Jewish Archives Mission.” <i>American Jewish Archives</i>, <a href='https://www.americanjewisharchives.org/about/aja-mission/' target='_blank'>https://www.americanjewisharchives.org/about/aja-mission/</a>. Accessed 14 Nov. 2024.",
  9: "9.	Watson, Marcus D. “White Supremacy’s Horcrux and Why the Black Power Movement Almost Destroyed It.” <i>Journal of African American Studies</i>, vol. 26, no. 2, June 2022, pp. 221–47. EBSCOhost, <a href='https://doi-org.proxy.lib.ohio-state.edu/10.1007/s12111-022-09585-3' target='_blank'>https://doi-org.proxy.lib.ohio-state.edu/10.1007/s12111-022-09585-3</a>.",
  10: "10.	Ben L. Martin, “From Negro to Black to African American: The Power of Names and Naming.”, <i>Political Science Quarterly</i>, Volume 106, Issue 1, Spring 1991, Pages 83–107, <a href='https://doi.org/10.2307/2152175' target='_blank'>https://doi.org/10.2307/2152175</a>.",
  11: "11.	Warren, Calvin L. “Ontological Terror: Blackness, Nihilism, and Emancipation.”, <i>Duke University Press</i>, 2018. <a href='https://library.oapen.org/bitstream/handle/20.500.12657/30152/1/649831.pdf' target='_blank'>https://library.oapen.org/bitstream/handle/20.500.12657/30152/1/649831.pdf</a>.",
  12: "12.	Yasui Estacio, Adam Minoru. “The ‘Newest “Yellow Peril”’: How American Legal History Shaped the Rise in Asian American Hate Crimes in the Covid-19 Pandemic.” <i>Denver Law Review</i>, vol. 100, no. 1, Oct. 2022, pp. 305–23. <i>EBSCOhost</i>, <a href='https://proxy.lib.ohio-state.edu/login?url=https://search.ebscohost.com/login.aspx?direct=true&db=a9h&AN=161944556&site=ehost-live' target='_blank'>https://proxy.lib.ohio-state.edu/login?url=https://search.ebscohost.com/login.aspx?direct=true&db=a9h&AN=161944556&site=ehost-live</a>.",
  13: "13.	Sekhon, Vijay. “The Civil Rights of ‘Others’: Antiterrorism, The Patriot Act, and Arab and South Asian American Rights in Post-9/11 American Society.” <i>Texas Journal on Civil Liberties & Civil Rights</i>, vol. 8, no. 1, Spring 2003, p. 117. <i>EBSCOhost</i>, <a href='https://proxy.lib.ohio-state.edu/login?url=https://search.ebscohost.com/login.aspx?direct=true&db=a9h&AN=10969062&site=ehost-live' target='_blank'>https://proxy.lib.ohio-state.edu/login?url=https://search.ebscohost.com/login.aspx?direct=true&db=a9h&AN=10969062&site=ehost-live</a>.",
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

const images = ref([
  {
    src: new URL('../assets/pic/gw-1.png', import.meta.url).href,
    alt: 'Gallery Wall 1',
    href: 'https://www.crmvet.org/info/seglaws.htm',
    target: '_blank',
    caption: 'Birmingham Public Accommodation Segregation Laws',
  },
  {
    src: new URL('../assets/pic/gw-2.png', import.meta.url).href,
    alt: 'Gallery Wall 2',
    href: 'https://www.crmvet.org/info/seglaws.htm',
    target: '_blank',
    caption: 'Montgomery Bus Segregation Laws',
  },
  {
    src: new URL('../assets/pic/gw-3.png', import.meta.url).href,
    alt: 'Gallery Wall 3',
    href: 'https://www.crmvet.org/lets/halstead.htm',
    target: '_blank',
    caption: "Fred Halstead's Report On The Montgomery Bus Boycott",
  },
  {
    src: new URL('../assets/pic/gw-4.jpg', import.meta.url).href,
    alt: 'Gallery Wall 4',
    href: 'https://www.crmvet.org/images/imgstrug.htm',
    target: '_blank',
    caption: '"Don\'t Buy Segragation"',
  },
  {
    src: new URL('../assets/pic/gw-5.png', import.meta.url).href,
    alt: 'Gallery Wall 5',
    href: 'https://www.crmvet.org/docs/cra64.htm',
    target: '_blank',
    caption: 'Civil Rights Act of 1964',
  },
])

const currentIndex = ref(0)

const prevImage = () => {
  currentIndex.value = (currentIndex.value - 1 + images.value.length) % images.value.length
}

const nextImage = () => {
  currentIndex.value = (currentIndex.value + 1) % images.value.length
}
</script>

<template>
  <div>
    <div class="list">
      <h1 class="green">List of Sources & Annotations</h1>
      <div class="paragraph">
        For this part of the list and annotation of important ideas and sources, I will cover some
        significant materials that would be helpful for the research on this topic. This part will
        be divided into two sections. The first are archives that contain rich, valuable, and
        massive primary sources, which will be very important and useful for research. The second
        part will be articles, especially scholarly research articles, on this topic. The
        perspectives of different scholars will give us a new and different opinion, which may give
        us new inspiration.
      </div>
      <div class="image-carousel">
        <button @click="prevImage" class="carousel-button prev-button">‹</button>
        <div class="carousel-image-container">
          <div
            class="carousel-images"
            :style="{ transform: `translateX(-${currentIndex * 100}%)` }"
          >
            <a
              v-for="(image, index) in images"
              :key="index"
              :href="image.href"
              :target="image.target"
              class="carousel-image-link"
            >
              <img :src="image.src" :alt="image.alt" class="carousel-image" />
            </a>
          </div>
        </div>
        <button @click="nextImage" class="carousel-button next-button">›</button>
      </div>
      <div class="image-caption">
        {{ images[currentIndex].caption }}
      </div>
      <div class="paragraph">
        My research on ethnic minority group rights began from
        <b>the civil rights movement archive</b>,
        <a href="https://www.crmvet.org/">https://www.crmvet.org/</a>. This archive includes a huge
        amount of primary and secondary sources of this remarkable movement. It was created and
        maintained by a group of civil rights movement veterans, ensuring that these materials are
        relatively reliable and valuable. The archive includes four general categories: movement,
        activists, video/audio, and resources. And within these general categories, photo albums,
        videos, audio, reports, articles, letters, etc. are provided.
      </div>
      <div class="paragraph">
        To create a gallery wall focusing on the civil rights movement, I selected two law bills, a
        photo, and a primary report, focusing on the protest of racial segregation. Among these, the
        most important and direct is the photo, which shows a black girl marching with other people
        with the sentence <b>“Do not buy segregation”</b>, when protesting a racist local company.
        The visual impact that such a picture with large characters can be huge. The two law bills
        include <b>the South segregation laws</b> (also known as
        <a href="https://www.history.com/topics/early-20th-century-us/jim-crow-laws" target="_blank"
          >Jim Crow Laws</a
        >) and <b>the Civil Rights Act of 1964</b>. The former was the trigger of the civil rights
        movement, while the latter was the result of the movement. The report came from a leader of
        the workers’ organization Fred Halstead, who recorded the bus boycott in Montgomery in 1956.
        This is a very useful primary source to get to know what happened during the movement.
      </div>
      <div class="paragraph">
        From this, we can find more archives on the Internet to support our arguments further. These
        archives can focus on different ethnic minority groups and their experiences fighting for
        their rights. The most significant one is the U.S. National Archives, an independent agency
        of the U.S. government focusing on the preservation and documentation of government and
        historical records. When I searched the keyword “Asian American archives” on <b>Google</b>,
        I found that the <b>National Archives</b> has a special records archive of
        <b>Asian American and Pacific Islander Records</b>
        <span class="reference" @click="handleReferenceClick(5, $event)">[5]</span>. A visitor can
        research by topic, go over featured records, and explore further blogs, articles, and
        scholarly papers. Similarly, there are <b>African American Heritage</b>
        <span class="reference" @click="handleReferenceClick(6, $event)">[6]</span>,
        <b>Hispanic / Latino Heritage</b>
        <span class="reference" @click="handleReferenceClick(7, $event)">[7]</span>, etc.
      </div>
      <div class="paragraph">
        Individual archives are also good references and sources helpful to our research. For
        example, the <b>American Jewish Archives</b
        ><span class="reference" @click="handleReferenceClick(8, $event)">[8]</span>
        is a very well-organized archive page with a similar structure to the
        https://www.crmvet.org/. The Jewish Archives collect, preserve, and make available for
        research, materials on the history of Jews and Jewish communities in the Western Hemisphere
        (primarily focusing on America) including data of a political, economic, social, cultural,
        and religious nature. Such an archive provides materials covering widely the topic and can
        be helpful to research.
      </div>
      <figure class="float-right worknet-pic">
        <img src="../assets/pic/Worknet.png" alt="worknet-pic" />
        <figcaption>Worknet Created Based On Focal Article</figcaption>
      </figure>
      <div class="paragraph">
        Another important category of research sources comes from scholarly papers. I will begin
        with my focal article and its worknet. The focal article
        <b
          ><i>“White Supremacy’s Horcrux and Why the Black Power Movement Almost Destroyed It”</i>,
          by Dr. Marcus D. Watson</b
        >
        <span class="reference" @click="handleReferenceClick(9, $event)">[9]</span>, focuses on the
        topic of black power and ethnic identities, especially after the Black Powers Movement in
        the 1960s. It also tries to discuss why the Black Powers Movement almost destroyed the White
        Supremacy but at last failed. I found this peer-reviewed focal article on Academic Search
        Complete, specifically the EBSCOhost website.
      </div>
      <div class="paragraph">
        Meanwhile, the reference papers that the focal article refers to are also worth mentioning.
        One of the significant references Dr. Watson used to support his argument was
        <b><i>“From Negro to Black to African American”</i> by B. L. Martin</b>, published in 1991.
        <span class="reference" @click="handleReferenceClick(10, $event)">[10]</span> B. Martin
        developed the argument that the transition of African Americans calling themselves, “negro”
        to “black” and “African American”, was more likely to be supported and motivated by the
        Black Powers Movement. The core opinion is that it was the Black Powers Movement instead of
        the Civil Rights Movement that led to this transition and promoted black identity and
        cohesion and that such a self-identity would greatly improve African Americans’ ethnic
        self-confidence.
      </div>
      <figure class="float-left crmvet-pic">
        <a href="https://crmvet.org" target="_blank">
          <img src="../assets/pic/crmvet.png" alt="crmvet-pic" />
        </a>
        <figcaption>Civil Rights Movement Archive</figcaption>
      </figure>
      <div class="paragraph">
        The paper
        <b><i>“Ontological Terror: Blackness, Nihilism, and Emancipation.”</i> by C. Warren</b>,
        published in 2018
        <span class="reference" @click="handleReferenceClick(11, $event)">[11]</span>, intervenes in
        Afro-pessimism, Heideggerian metaphysics, and black humanist philosophy by positing that the
        “Negro question” is intimately imbricated with questions of Being. Antiblackness had become
        an essential part in white supremacy, and it gave white supremacists the precondition to
        ground and affirm themselves. Dr. Watson cites this paper to support his argument that white
        supremacists need to derogate and oppose black people for their self-proud whiteness
        identities is a part of the foundation ideas of white supremacy, and that is why black
        people must and almost destroy it. It is the same today for other minority groups,
        especially Asian Americans. White supremacists were not only towards black people but also
        any ethnic groups but white people themselves. The racism from white supremacists against
        minority groups can be a very valuable focus of this topic.
      </div>
      <div class="paragraph">
        Such analysis can be done for many papers, and
        <b
          >using such analysis and papers as references can make the research more reliable and
          highly qualified.</b
        >
        And, do not limit yourself to some specified articles. A very important step in doing great
        research is to widely search for sources to support the arguments. For this topic focusing
        on ethnic minority groups in U.S. society, we can do further research on, for example, Asian
        Americans and their civil rights.
      </div>
      <div class="paragraph">
        I found this article when searching the keyword “Asian American Rights” on the EBSCOhost.
        <b
          ><i
            >“The ‘Newest ‘Yellow Peril’’: How American Legal History Shaped The Rise In Asian
            American Hate Crimes In The COVID-19 Pandemic”</i
          >, by Adam Minoru Yasui Estacio</b
        >
        <span class="reference" @click="handleReferenceClick(12, $event)">[12]</span>. This article
        tries to analyze and explain why Asian immigrants exclusive stereotypes in other Americans’
        minds, how American legal history and law bills have excluded Asian Americans, and why and
        how American society must dismantle the pillars of the perpetual foreigner stereotype by
        undergoing substantial political, societal, and legal change.
      </div>
      <div class="paragraph">
        Another article focuses more on these “foreigners” or “others’” status and lives in society,
        especially after some big societal incidents.
        <b
          ><i
            >“The Civil Rights of "Others": Antiterrorism, The Patriot Act, and Arab and South Asian
            American Rights in Post-9/11 American Society.”</i
          >, by Vijay Sekhon</b
        >
        <span class="reference" @click="handleReferenceClick(13, $event)">[13]</span>, focuses on
        South Asian Americans and Arab Americans’ lives and hate crimes towards them after 9/11
        terrorism attack. More seriously, the Bush Administration undermined these ethnicities’
        freedoms by inserting sections into the Patriot Act.
      </div>
      <div class="paragraph">
        These lists and annotations of research sources and ideas are only a small part of the big
        research area. However, although the topic is large, we can focus on some core ideas and
        arguments based on our research target.
      </div>
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
  </div>
</template>

<style scoped>
.image-carousel {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 20px 0;
  overflow: hidden;
  width: 100%;
}

.carousel-image-container {
  overflow: hidden;
  width: 80%;
  display: flex;
  justify-content: center;
}

.carousel-images {
  display: flex;
  transition: transform 0.5s ease-in-out;
}

.carousel-image-link {
  display: flex;
  justify-content: center;
  align-items: center;
  min-width: 100%;
}

.carousel-image {
  min-width: 100%;
  max-height: 400px;
  border-radius: 10px;
  object-fit: contain;
}

.carousel-button {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  background-color: rgba(0, 0, 0, 0.5);
  color: white;
  border: none;
  padding: 10px;
  cursor: pointer;
  border-radius: 50%;
  font-size: 24px;
  z-index: 1;
}

.prev-button {
  left: 10px;
}

.next-button {
  right: 10px;
}

.carousel-button:hover {
  background-color: rgba(0, 0, 0, 0.8);
}

.list {
  margin-left: 8vw;
  margin-right: 8vw;
  width: 84vw;
  text-align: justify;
  font-size: 20px;
  overflow-y: hidden;
  overflow-x: hidden;
}

.image-caption {
  font-size: 20px;
  font-weight: 600;
  text-align: center;
  margin-bottom: 2%;
}

.paragraph {
  margin-bottom: 1%;
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

.object-pic img,
.crmvet-pic img {
  width: 30vw;
}

.worknet-pic img {
  height: 45vh;
}

h1 {
  font-weight: 800;
  font-size: 2.6rem;
  top: 10px;
  text-align: center;
  margin-bottom: 3%;
}

a,
b {
  color: hsla(160, 100%, 37%, 1);
  font-weight: 600;
}

a {
  text-decoration: underline;
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
  name: 'ListComponent',
}
</script>
