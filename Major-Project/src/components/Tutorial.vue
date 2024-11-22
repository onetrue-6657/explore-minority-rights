<script setup>
import { ref, nextTick } from 'vue'
const references = ref({
  4: "4.  Hate Crime Statistics. <i>U.S. Department of Justice</i>, <a href='https://www.justice.gov/hatecrimes/hate-crime-statistics/' target='_blank'>https://www.justice.gov/hatecrimes/hate-crime-statistics/</a>. Accessed 14 Nov. 2024.",
  14: "14.	“Asian Americans.” <i>Wikipedia</i>, <a href='https://en.wikipedia.org/wiki/Asian_Americans' target='_blank'>https://en.wikipedia.org/wiki/Asian_Americans/</a>. Accessed 14 Nov. 2024.",
  15: "15.	“Immigration Records Related to Asian American and Pacific Islander History.” <i>National Archives</i>, <a href='https://www.archives.gov/research/aapi/immigration/' target='_blank'>https://www.archives.gov/research/aapi/immigration/</a>. Accessed 14 Nov. 2024.",
  16: "16.	“Chinese Exclusion Act.” <i>National Archives</i>, <a href='https://www.archives.gov/milestone-documents/chinese-exclusion-act' target='_blank'>https://www.archives.gov/milestone-documents/chinese-exclusion-act</a>. Accessed 14 Nov. 2024.",
  17: "17.	Dancis, Danielle. “Bringing the Past to Light through the Chinese Exclusion Act Case Files.” <i>The Text Message: The Blog of the National Archives</i>, 13 May 2021, <a href='https://text-message.blogs.archives.gov/2021/05/13/bringing-the-past-to-light-through-the-chinese-exclusion-act-case-files/' target='_blank'>https://text-message.blogs.archives.gov/2021/05/13/bringing-the-past-to-light-through-the-chinese-exclusion-act-case-files/</a>. Accessed 14 Nov. 2024.",
  18: "18.	“EBSCOhost Advanced Search.” <i>EBSCOhost</i>, <a href='https://web-p-ebscohost-com.proxy.lib.ohio-state.edu/ehost/search/advanced?vid=0&sid=94d5b24b-2e73-4a52-8cfa-f8bb435cb0b5%40redis' target='_blank'>https://web-p-ebscohost-com.proxy.lib.ohio-state.edu/ehost/search/advanced?vid=0&sid=94d5b24b-2e73-4a52-8cfa-f8bb435cb0b5%40redis</a>. Accessed 14 Nov. 2024. (This is a link based on college service)",
  19: "19.	Walker, Denetra, and Allison Daniel Anders. “‘China Virus’ and ‘Kung-Flu’: A Critical Race Case Study of Asian American Journalists’ Experiences During COVID-19.” <i>Cultural Studies/Critical Methodologies</i>, vol. 22, no. 1, Feb. 2022, pp. 76–88. <i>EBSCOhost</i>, <a href='https://doi-org.proxy.lib.ohio-state.edu/10.1177/15327086211055157' target='_blank'>https://doi-org.proxy.lib.ohio-state.edu/10.1177/15327086211055157</a>. Accessed 14 Nov. 2024.",
  20: "20.	Council of Economic Advisers. “Racial Discrimination in Contemporary America.” <i>The White House,/i>, 3 July 2024, <a href='https://www.whitehouse.gov/cea/written-materials/2024/07/03/racial-discrimination-in-contemporary-america/' target='_blank'>https://www.whitehouse.gov/cea/written-materials/2024/07/03/racial-discrimination-in-contemporary-america/</a>. Accessed 14 Nov. 2024.",
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
  <div class="tutorial">
    <h1 class="green">So...How To Start A Research?</h1>
    <div class="paragraph">
      It’s not hard to begin researching ethnic minority group rights in U.S. society. We can divide
      our research into several parts.
    </div>
    <div class="paragraph">
      Let’s start with what you want to do, or,
      <b>which specific area you want your research to be on</b>. Take the topic discussed here as
      an example, you can first choose <b>which ethnic minority group you want to focus on</b>. Do
      not just limit the vision to groups such as African Americans and Native Americans, the
      immigrants that have continuously migrated to the U.S. throughout the past few hundred years
      can also be worth researching. Asian Americans, Jews, and Hispanos are the most significant
      groups. And among these groups, we can even get more detailed divisions such as Chinese
      Americans, Japanese Americans, Vietnamese Americans, Indian Americans, etc. Even those who
      were but are no longer, such as Irish Immigrant Americans and Italian Immigrant Americans in
      the 19th and 20th centuries can be researched. In this example, I am going to take East Asian
      Americans’ civil rights and social status as a whole as the research focus.
    </div>
    <figure class="float-left tut1-pic">
      <a
        href="https://www.google.com/search?client=firefox-b-1-d&q=wikipedia+asian+american"
        target="_blank"
      >
        <img src="../assets/pic/tut1.png" alt="Tutorial Picture 1" />
      </a>
      <figcaption>Google Search Result Showing Wikipedia</figcaption>
    </figure>
    <div class="paragraph">
      A very essential part of research is to <b>read materials widely</b>. This will help
      efficiently get inspiration for ideas and sources that can be referred to. You will want to
      start from a relatively general page that will lead to other different and more detailed
      materials.
      <b
        ><a href="https://www.wikipedia.org/" target="_blank">Wikipedia</a> is a good starting
        point</b
      >, as it provides a comprehensive description of the history and current situation of the area
      you are going to research. For example, I just need to <b>google</b> “Asian American
      Wikipedia” or “Asian American rights Wikipedia”, and relative pages will show in the results.
      You may use your language to search for the page, but English Wikipedia is the most
      comprehensive and most content-rich.
    </div>

    <div class="paragraph">
      The “Asian Americans” Wikipedia page
      <span class="reference" @click="handleReferenceClick(14, $event)">[14]</span> is divided into
      multiple parts, and we need to <b>find the parts that are the most useful to us</b>. It is
      like how a filter works, we filter the terminology section and look for the parts we are
      interested in and those really matter to our research. Among these sections, I think the
      history section is the most important one when researching minority groups, and their past of
      racial discrimination should not be ignored or forgotten. So we switch to the “Exclusive Era”
      in the History section, and we find that the “restrictive legislation” interests me. We then
      further go into the Chinese Exclusion Act page to research the history of Asian Americans,
      specifically Chinese immigrants, being excluded and discriminated against in federal legal
      aspects. Similarly, we can also learn and refer to the history of the internment of Japanese
      Americans during World War II and federal cases such as United States v. Wong Kim Ark (1898).
      We can also go over other important sections such as “Social and political issues” and go
      through them to learn what happened to Asian Americans’ social status in the past and now.
    </div>
    <div class="double-pic-container">
      <figure class="tut2-pic">
        <a href="https://en.wikipedia.org/wiki/Asian_Americans#History" target="_blank"
          ><img src="../assets/pic/tut2.png" alt="Tutorial Picture 2"
        /></a>
        <figcaption>Wikipedia Page Focusing on History</figcaption>
      </figure>
      <figure class="tut3-pic">
        <a href="https://en.wikipedia.org/wiki/Chinese_Exclusion_Act" target="_blank"
          ><img src="../assets/pic/tut3.png" alt="Tutorial Picture 3"
        /></a>
        <figcaption>Wikipedia Page "Chinese Exclusion Act"</figcaption>
      </figure>
    </div>
    <div class="paragraph">
      However, Wikipedia cannot serve as a very scholarly reliable source. Since it is open and
      editable to everyone, there can be misleading and biased edits and texts. I prefer to use it
      more like a <b>navigation</b> that tells you which ways you can go, and for the next step you
      go yourselves in specific paths researching more detailed things. <b>The archives</b>, such as
      <a href="https://www.archives.gov/" target="_blank">the National Archives</a> I have
      introduced above a reliable and widely covered archive that provides a large amount of
      sources. Very clearly, exclusion is a very hot topic in the archive. We can click on the
      <b>“Enforcing Immigration and Exclusion” topic</b> and take a look at the systematic exclusion
      of Asian Americans (and Pacific Islanders) from the 1870s to the 1950s.<span
        class="reference"
        @click="handleReferenceClick(15, $event)"
        >[15]</span
      >
    </div>
    <div class="double-pic-container">
      <figure class="tut4-pic">
        <a href="https://www.archives.gov/research/aapi/immigration" target="_blank"
          ><img src="../assets/pic/tut4.png" alt="Tutorial Picture 4"
        /></a>
        <figcaption>National Archives Page of Restricting Immigrations of AAs and PIs</figcaption>
      </figure>
      <figure class="tut5-pic">
        <a href="https://www.archives.gov/research/aapi" target="_blank"
          ><img src="../assets/pic/tut5.png" alt="Tutorial Picture 5"
        /></a>
        <figcaption>National Archives Page of AAs and PIs</figcaption>
      </figure>
    </div>
    <div class="paragraph">
      From here, we can look at the <b>detailed transcripts</b> of the bills such as the Chinese
      Exclusion Act of 1882.<span class="reference" @click="handleReferenceClick(16, $event)"
        >[16]</span
      >
      The National Archives provides the transcript and an electrical copy of the original
      manuscript. Similarly, we can search for <b>blogs and articles</b> that can support our
      arguments and research. The article “Bringing the Past to Light through the Chinese Exclusion
      Act Case File” by Ddancis posted in Asian Pacific American Heritage
      <span class="reference" @click="handleReferenceClick(17, $event)">[17]</span> gives an
      analysis and the history of Chinese immigrants being excluded. Such an article gives real
      materials and experiences to describe what happened during that time. When writing a paper, we
      can cite and refer to these materials and articles to support our arguments.
    </div>
    <div class="double-pic-container">
      <figure class="tut6-pic">
        <a href="https://www.archives.gov/research/aapi/immigration" target="_blank"
          ><img src="../assets/pic/tut6.png" alt="Tutorial Picture 6"
        /></a>
        <figcaption>National Archives Page Showing Law Bills Restricting Immigrations</figcaption>
      </figure>
      <figure class="tut7-pic">
        <a href="https://www.archives.gov/research/aapi/immigration" target="_blank"
          ><img src="../assets/pic/tut7.png" alt="Tutorial Picture 7"
        /></a>
        <figcaption>National Archives Page Blogs And Articles Section</figcaption>
      </figure>
    </div>
    <figure class="float-right tut8-pic">
      <a
        href="https://web-p-ebscohost-com.proxy.lib.ohio-state.edu/ehost/search/advanced?vid=0&sid=99f52262-1ede-475d-a0af-589219ce56b6%40redis"
        target="_blank"
      >
        <img src="../assets/pic/tut8.png" alt="Tutorial Picture 8" />
      </a>
      <figcaption>EBSCOhost Academic Search Complete Main Page (Via OSU)</figcaption>
    </figure>
    <figure class="float-left tut9-pic">
      <a
        href="https://web-p-ebscohost-com.proxy.lib.ohio-state.edu/ehost/search/advanced?vid=0&sid=99f52262-1ede-475d-a0af-589219ce56b6%40redis"
        target="_blank"
      >
        <img src="../assets/pic/tut9.png" alt="Tutorial Picture 9" />
      </a>
      <figcaption>Search Databases Filters</figcaption>
    </figure>
    <div class="paragraph">
      <b>Scholarly papers</b> are also important and reliable to use when writing papers. We can
      find all kinds of papers on platforms such as
      <a
        href="https://www.ebsco.com/products/research-databases/academic-search-complete"
        target="_blank"
        >EBSCOhost Academic Search Complete</a
      >
      <span class="reference" @click="handleReferenceClick(18, $event)">[18]</span> if your
      university supports this service.
      <a href="https://scholar.google.com/" target="_blank">Google Scholar</a> is also a useful tool
      that covers a wide range of papers, and it directs you to the sources where you can read some
      of the papers for free. Entering the EBSCOhost, we can search what we want using key words or
      phrases. Smartly using <b>databases filters</b> such as “Full Text” and “Peer Reviewed” can
      improve the overall quality of your research results. If you have not come out with an idea of
      what keywords you want to do, it provides you with databases to choose, from based on topics.
    </div>
    <div class="paragraph">
      For example, we type in the keywords “Asian American discrimination” which is closely related
      to our topic. You do not need to really type in some very specific keywords for what you want
      – some general keywords are also good for this search engine. Now we choose the article<b>
        <i
          >“‘China Virus’ and ‘Kung-Flu’: A Critical Race Case Study of Asian American Journalists'
          Experiences During COVID-19.”</i
        >
        by Denetra Walker and Allison Daniel Anders.</b
      ><span class="reference" @click="handleReferenceClick(19, $event)">[19]</span>
      Published in 2022, this paper focuses on racial discrimination towards Asian Americans during
      COVID-19. Such articles are very helpful sources for our research. Specifically in this
      article, the authors provided examples and data of Asian Americans being targets of hate
      crimes during the epidemic. They also tried to analyze this inequality both from social, press
      (journalism) and historical aspects.
    </div>
    <div class="double-pic-container">
      <figure class="tut10-pic">
        <a
          href="https://web-p-ebscohost-com.proxy.lib.ohio-state.edu/ehost/resultsadvanced?vid=2&sid=99f52262-1ede-475d-a0af-589219ce56b6%40redis&bquery=asian+american+discrimination&bdata=JmRiPWE5aCZ0eXBlPTEmc2VhcmNoTW9kZT1BbmQmc2l0ZT1laG9zdC1saXZl"
          target="_blank"
          ><img src="../assets/pic/tut10.png" alt="Tutorial Picture 10"
        /></a>
        <figcaption>Search Results of "asian american discrimination"</figcaption>
      </figure>
      <figure class="tut11-pic">
        <a
          href="https://journals-sagepub-com.proxy.lib.ohio-state.edu/doi/10.1177/15327086211055157"
          target="_blank"
          ><img src="../assets/pic/tut11.png" alt="Tutorial Picture 11"
        /></a>
        <figcaption>
          <i>"“China Virus” and “Kung-Flu”: ..."</i> By Walker and Daniel Anders
        </figcaption>
      </figure>
    </div>
    <div class="paragraph">
      Besides texts and pictures, <b>statistics</b> are direct and clear as well. According to the
      <a href="https://www.justice.gov/hatecrimes/hate-crime-statistics/" target="_blank"
        >U.S. Department of Justice statistics</a
      >, 52.5% of hate crime incidents in 2023 are based upon “Race/Ethnicity/Ancestry”<span
        class="reference"
        @click="handleReferenceClick(4, $event)"
        >[4]</span
      >. A report on
      <a
        href="https://www.whitehouse.gov/cea/written-materials/2024/07/03/racial-discrimination-in-contemporary-america/"
        target="_blank"
        ><i>“Racial Discrimination in Contemporary America”</i></a
      >
      on the White House website also provides wide statistics of racial bias and discrimination in
      all aspects of society based on different categories.<span
        class="reference"
        @click="handleReferenceClick(20, $event)"
        >[20]</span
      >
      Providing such data in papers can greatly improve the reliability of the article and make the
      current situation of Asian Americans – in this example – clear and readable to the readers.
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
</template>

<style scoped>
.tutorial {
  height: 100vh;
  margin-left: 8vw;
  margin-right: 8vw;
  text-align: justify;
  font-size: 20px;
  overflow-x: hidden;
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

.paragraph {
  margin-bottom: 1%;
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

.tut1-pic img {
  width: 30vw;
}

.tut9-pic img {
  width: 15vw;
}

.tut8-pic img {
  width: 32vw;
}

.double-pic-container {
  margin: 3% 0;
  display: flex;
  justify-content: space-between;
  gap: 2%;
}

.tut2-pic,
.tut3-pic,
.tut4-pic,
.tut5-pic,
.tut10-pic,
.tut11-pic {
  flex: 1;
}

.double-pic-container img {
  width: 100%;
  height: auto;
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
  name: 'tutorialComponent',
}
</script>
