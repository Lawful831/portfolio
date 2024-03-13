<script setup lang="ts">
import { onMounted, ref } from 'vue';
const about_show = ref(false)
const projects_show = ref(false)
const display_about = ()=>{
  about_show.value = true
  projects_show.value = false
}
const display_projects = ()=>{
  about_show.value = false
  projects_show.value = true
}

const type_div = (id) => {
  let div = document.getElementById(id);
  div.classList.remove("hidden")
  let text_holder = div.innerHTML;
  let text_fill = "";

  // Clear the existing content before typing
  div.innerHTML = "";

  // Loop through each character and add a delay for the effect
  for (let i = 0; i < text_holder?.length; i++) {
    setTimeout(() => {
      text_fill += text_holder[i];
      div.innerHTML = text_fill; // Update the content with each character
    }, i * 50); // Adjust the delay (50ms here) for typing speed
  }
};



onMounted(()=>{
})
</script>

<template>
<div class="text-center text-5xl mt-4 typed">Project █████████</div>
<div class="text-center text-xl mt-3 typed"> A.K.A Andre's Portfolio </div>
<div class="text-sm text-center typed"><span class="bg-yellow-400">Disclaimer</span>: This website employs a <span class="bg-yellow-400">fictionalized</span> research study format for entertainment purposes only.<br> The information presented does not reflect any actual research or classified documents.<br>Although it does show the work I done, in a fun way.</div>
<div class="flex flex-row">
    <div class="container ml-4 w-fit basis-1/2">
        <div class="text-4xl mt-20 typed cursor-pointer hover:underline hover:font-bold " @click="display_about" >About</div>
        <div class="text-4xl mt-4 typed cursor-pointer hover:underline" @click="display_projects">Projects</div>
    </div>
    <div class="basis-1/2 mt-8 border-2 border-black mr-[25rem] h-fit p-4"  v-motion-slide-visible-once-bottom v-show="about_show">
        <h1 class="text-3xl text-center mt-2 w-[50rem] mb-2 hover:underline cursor-pointer" @click="()=>{type_div('about')}" >About</h1>
        <p class="text-center hidden" id="about">
          Despite his relatively brief engagement with programming, Andre exhibits a remarkable grasp of core programming concepts. His skillset encompasses:<br>
          Website Development: Andre possesses the ability to design and develop functional websites, potentially utilizing frameworks or libraries to expedite the process.
          <br>Artificial Intelligence: Andre's interest in AI suggests an aptitude for complex algorithms and the ability to translate theoretical concepts into practical applications. Here, early explorations involved ██████████, demonstrating a grasp of ███████████.
          <br>Automation: Andre's proficiency in automation indicates a keen understanding of streamlining tasks and optimizing processes. Notably, he has successfully implemented automation solutions for ████████ ███████, resulting in significant efficiency gains.
        </p>
    </div>
    <div class="basis-1/2 mt-8 border-2 border-black mr-[25rem] h-fit p-4" id="projects"  v-motion-slide-visible-once-bottom v-show="projects_show">
      <h1 class="text-3xl text-center mt-2 w-[50rem] mb-2" >Projects</h1>
      <div class="project-item mt-4">
        <h2 class="text-2xl mb-2 hover:underline cursor-pointer" @click="()=>{type_div('3a2e')}">Case 3a2e: Pet's Paradiso Website</h2>
        <div id="3a2e" class="hidden">
        <p>This project involved the creation of a functional website for a small business, presumably in the pet care industry. While details remain classified, the utilization of React indicates an understanding of component-based development and potentially the implementation of interactive features for the website's users.</p>
        <p>The exact date is unknown, but we have determined it was created during the year 2021. Through further investigation, we have seen bits of other projects, one standed out as a really █████████ ██████ website, that proclaimed to █████████. We have yet to investigate the veracity of it.</p>
        <br>Attached Evidence File: https://www.petsparadiso.com

        </div>
      </div>

      <div class="project-item mt-4">
        <h2 class="text-2xl mb-2 hover:underline cursor-pointer" @click="()=>{type_div('1kee')}">Case 1kee: Quizbot</h2>
        <div id="1kee" class="hidden">
        <p>
          Deciphering another project designated "Project Echo", reveals the development of a software utility termed "Quizbot".  Initial analysis suggests "Quizbot" utilizes the Python programming language and focuses on automating functionalities associated with the online ███████ platform called ███████.
        </p>
        <br>Attached Evidence File: https://github.com/Lawful831/quizbot-cli

      </div>
      </div>

      <div class="project-item mt-4">
        <h2 class="text-2xl mb-2 hover:underline cursor-pointer" @click="()=>{type_div('g2f4')}">Case g2f4: Project Apollo</h2>
        <div id="g2f4" class="hidden">
        <p>
        The most unknown project, at the date, from the fragments we have got to extract, might indicate some influence from concepts of ███, and inspiration from media like █████████ █████████, or ████████████.
        </p>
        <br>Attached Evidence File: [Error 404]
      </div>
      </div>

      <div class="project-item mt-4">
        <h2 class="text-2xl mb-2 hover:underline cursor-pointer" @click="()=>{type_div('notes')}">Additional Notes:</h2>
        <div id="notes" class="hidden">
        <p>
          
        </p>
        <br>Unreviewed Attached Files:
        
        
      </div>
      </div>
    </div>
    </div>

</template>

<style>

.typed {
    width: 0;
    overflow: hidden; /* Ensure the text is not visible until the typewriter effect*/
    white-space: nowrap; /* Keeps the text on a single line */

    animation: typing 2s steps(20) forwards;
  }

/* The typing animation */
@keyframes typing {
  from { width: 0 }
  to { width: 100% }
}

@keyframes blink {
  0%, 45% {
    border-color: transparent;
  }
  50% {
    border-color: black;
  }

  100%{
    border-color: transparent;
  }
}
</style>
