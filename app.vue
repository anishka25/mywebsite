<script setup lang="js">
const menuSelected = ref(null)
function changeSelected(x) {
  menuSelected.value = x
}
onMounted(() => {
  menuSelected.value = "about"

})
const profileOpen=ref(false)
function changeProfileSize(){
  profileOpen.value=!profileOpen.value
}
const data= reactive([{
  title:'Mediviser',
  description:'Healthcare chatbot that can answer medical queries',
  imageURL:'/medi.jpg',
  link:'/medi.pdf'
},
{
  title:'Dermascan',
  description:'Application that scans and detects the skin disease',
  imageURL:'/derma.jpg',
  link:'https://youtu.be/FDJFvh7Zai0'

},
{
  title:'Butterfly Segmentation',
  description:'Creating segmentation mask on butterfly images using Segment Anything model(SAM)',
  imageURL:'/sam.jpg',
  link:'https://github.com/anishka25/butterflysam'
},
{
  title:'LoServ UI DESIGN',
  description:'Created UI design of a website for a marketing agency',
  imageURL:'/lo.jpg',
  link:'/lo.pdf'
},
{
  title:'Mediviser UI',
  description:'UI Design',
  imageURL:'/mediv.jpg',
  link:'/medi.pdf'
},
{
  title:'Dermascan UI ',
  description:'UI Design',
  imageURL:'/derm.jpg',
  link:'/dermascan.pdf'
},
{
  title:'Logo DESIGN',
  description:'A logo that promotes sustainable gaming',
  imageURL:'/best.png',
  link:'/'
}
])

const options = {
  fullScreen: {
    enable: true,
    zIndex: -1
  },
  fpsLimit: 60,
  particles: {
    number: {
      value: 80,
      density: {
        enable: true,
        value_area: 800
      }
    },
    color: {
      value: "#ffffff"
    },
    shape: {
      type: "circle",
      stroke: {
        width: 0,
        color: "#000000"
      },
      polygon: {
        nb_sides: 5
      },
      image: {
        src: "images/github.svg",
        width: 100,
        height: 100
      }
    },
    opacity: {
      value: 1,
      random: false,
      anim: {
        enable: false,
        speed: 1,
        opacity_min: 0.1,
        sync: false
      }
    },
    size: {
      value: 10,
      random: true,
      anim: {
        enable: false,
        speed: 40,
        size_min: 0.1,
        sync: false
      }
    },
    line_linked: {
      enable: true,
      distance: 150,
      color: "#ffffff",
      opacity: 1,
      width: 1
    },
    move: {
      enable: true,
      speed: 2,
      direction: "none",
      random: false,
      straight: false,
      out_mode: "out",
      attract: {
        enable: false,
        rotateX: 600,
        rotateY: 1200
      }
    }
  },
  interactivity: {
    detect_on: "canvas",
    events: {
      onHover: {
        enable: true,
        mode: "bubble",
        parallax: {
          enable: false,
          force: 20,
          smooth: 10
        }
      },
      onClick: {
        enable: true,
        mode: "push"
      },
      resize: true
    },
    modes: {
      grab: {
        distance: 400,
        lineLinked: {
          opacity: 1
        }
      },
      bubble: {
        distance: 400,
        size: 20,
        duration: 2,
        opacity: 1,
        speed: 3
      },
      repulse: {
        distance: 200
      },
      push: {
        particles_nb: 4
      },
      remove: {
        particles_nb: 2
      }
    }
  },
  backgroundMask: {
    enable: true,
    cover: {
      value: {
        r: 0,
        g: 0,
        b: 0
      }
    }
  },
  retina_detect: true,
  background: {
    image: "url('https://particles.js.org/images/background3.jpg')",
    position:"cover"
}

}

</script>

<template>
  <div>
    <NuxtParticles
    id="tsparticles"
    :options="options"
  >
</NuxtParticles>
<div class="xl:min-h-screen lg:px-20 lg:py-20 px-5 py-5">
  <div class="text-white grid xl:grid-cols-8 gap-x-5 gap-y-10 xl:gap-y-0">
    <div
      class="border-2 xl:sticky top-2 xl:h-[45rem] transition-all border-gray-600 xl:col-span-2 relative rounded-xl p-5 bg-gray-300/30 backdrop-blur-xl xl:self-start hover:border-cyan-600">
      <div class="absolute w-fit top-0 right-0">
        
        <button class="p-4 xl:hidden hidden md:block hover:border-2 hover:border-cyan-600 text-white lg:text-xl text-sm bg-black/30 rounded-bl-xl rounded-tr-xl h-14 shadow-[4.0px_8.0px_8.0px_rgba(103,232,249,0.38)]" @click="changeProfileSize">Show Profile</button>
        <button class="p-4 md:hidden text-white hover:border-2 hover:border-cyan-600 lg:text-xl text-sm bg-black/30 rounded-bl-xl rounded-tr-xl h-14 shadow-[4.0px_8.0px_8.0px_rgba(103,232,249,0.38)]" @click="changeProfileSize">↓</button>
      </div>
      <img src="/anishka_circle.png" class="lg:w-[150px] sm:w-[100px] w-[120px] mx-auto xl:block xl:mx-auto  mb-5 md:mb-0 rounded-full md:inline" />
      <div class="md:inline-block md:ml-8 mx-auto xl:block xl:ml-0"><h1 class="xl:mt-5 text-center font-semibold font-mono lg:text-3xl md:text-2xl text-xl">ANISHKA GUPTA</h1>
      <h2 class="text-gray-50 bg-black/30 p-2 text-center mt-3 rounded-xl lg:text-sm w-fit mx-auto text-xs ">FullStack AI Developer | UI Designer</h2></div>
      
      <div class="hidden xl:block transition-all" :class="{'!block': profileOpen}">
        <hr class="my-3 mx-2 border-1 border-gray-600 rounded-xl ">

      <div class="flex mt-2">
        <div class="p-4 mr-7  bg-black/30 w-fit rounded-2xl shadow-[4.0px_8.0px_8.0px_rgba(103,232,249,0.38)]">
          <Icon name="ic:twotone-email" class="size-6" color="#D7DBDD" />
        </div>
        <div class=" text-md grow pt-3">
          <a class="text-xl" href="mailto:anishkagupta25@gmail.com">Email</a>        
        </div>
      </div>

      <div class="flex my-5">
        <div class="p-4 mr-7 bg-black/30 w-fit rounded-2xl shadow-[4.0px_8.0px_8.0px_rgba(103,232,249,0.38)]">
          <Icon name="ant-design:linkedin-filled" class="size-6" color="#D7DBDD" />
        </div>
        <div class=" text-md grow pt-3">
          <a class="mt-2 text-xl" href="https://www.linkedin.com/in/anishka-gupta-1490b9251/">LinkedIn</a>
        </div>
      </div>

      <div class="flex">
        <div class="p-4 mr-7  bg-black/30 w-fit rounded-2xl shadow-[4.0px_8.0px_8.0px_rgba(103,232,249,0.38)]">
          <Icon name="fa6-brands:square-x-twitter" class="size-6" color="#D7DBDD" />
        </div>
        <div class=" text-xl grow pt-3">
          <a class="mt-2 " href="https://twitter.com/anishka_25">Twitter</a>
        </div>
      </div>

      <div class="flex mt-5">
        <div class="p-4 mr-7  bg-black/30 w-fit rounded-2xl shadow-[4.0px_8.0px_8.0px_rgba(103,232,249,0.38)]">
          <Icon name="icon-park-outline:github" class="size-6" color="#D7DBDD" />
        </div>
        <div class=" text-md grow pt-3">
          <a class="mt-2 text-xl" href="https://github.com/anishka25">Github</a>
        </div>
      </div>
      </div>
      
    </div>
    <div
      class="xl:col-span-6 border-[3px] border-gray-600 rounded-xl md:p-5 p-2 relative bg-gray-300/30 backdrop-blur  hover:border-cyan-600">
      <div class="w-fit absolute hidden right-0 p-4 px-10 lg:grid grid-cols-4 top-0 rounded-tr-lg rounded-bl-3xl bg-gray-300/20">
        <h1 @click="changeSelected('about')"
          :class="{ 'text-cyan-300': (menuSelected == 'about'), 'hover:!text-cyan-300': (menuSelected == 'about') }"
          class="px-4 text-xl text-center cursor-pointer hover:text-gray-200">About Me</h1>
        <h1 @click="changeSelected('resume')"
          :class="{ 'text-cyan-300': (menuSelected == 'resume'), 'hover:!text-cyan-300': (menuSelected == 'resume') }"
          class="px-4 text-xl text-center cursor-pointer hover:text-gray-200">Resume</h1>
        <h1 @click="changeSelected('portfolio')"
          :class="{ 'text-cyan-300': (menuSelected == 'portfolio'), 'hover:!text-cyan-300': (menuSelected == 'portfolio') }"
          class="px-4 text-xl text-center cursor-pointer hover:text-gray-200">Portfolio</h1>
        <h1 @click="changeSelected('contact')"
          :class="{ 'text-cyan-300': (menuSelected == 'contact'), 'hover:!text-cyan-300': (menuSelected == 'contact') }"
          class="px-4 text-xl text-center cursor-pointer hover:text-gray-200">Contacts</h1>
      </div>
      <div v-if="menuSelected == 'about'">
        <h1 class="text-3xl p-2 libre font-bold ">About Me</h1>
        <hr class="w-24 ml-2 border-b-4 border-cyan-300 rounded-xl mt-1">
        <p class="px-2 pt-4 text-lg">
          Passionate about leveraging cutting-edge technologies to unravel complex challenges. My recent endeavors have
          been centered around the field of computer vision, particularly in butterfly segmentation using the Segment
          Anything Model (SAM) and contributing to the mediviser project by harnessing visual question answering
          techniques to enhance medical diagnostics.</p><br>
        <p class="px-2 text-lg">Additionally, my journey encompasses a robust foundation in UI/UX design, where I've
          showcased my prowess in
          seamlessly blending aesthetic appeal with functional excellence.I've impactful UI designs for a marketing
          agency and demonstrated the ability to harmonize user-centric experiences with visually captivating
          interfaces.</p><br>
        <p class="px-2 text-lg"> Eager to contribute to groundbreaking projects, I bring a unique blend of skills that
          seamlessly integrates
          computer vision expertise with a keen eye for UI/UX design. I am excited about collaborating with like-minded
          professionals!
        </p><br>

        <div>
          <h1 class="text-2xl p-2 libre font-bold ">My Current Work</h1>

          <div class="lg:flex mt-5 gap-8">
            <div class="p-4 mb-7 lg:mb-0 bg-black/30 lg:w-fit rounded-2xl shadow-[4.0px_8.0px_8.0px_rgba(0,0,0,0.38)] lg:max-w-[50%] w-full">
              <Icon name="eos-icons:ai" class="size-[50px]" color="#67e8f9" />
              <span class="mt-2 text-xl  font-semibold p-2"> AI -Computer Vision</span>
              <h2 class="ml-[3.75rem]">The most modern and high-quality design made at a professional level.</h2>
            </div>
            <div class="p-4  bg-black/30 lg:w-fit rounded-2xl shadow-[4.0px_8.0px_8.0px_rgba(0,0,0,0.38)] ;g:max-w-[50%] w-full">
              <Icon name="ri:javascript-fill" class="size-[45px]" color="#67e8f9" />
              <span class="mt-2 text-xl  hidden md:inline font-semibold p-2"> FullStack Web Development</span>
              <span class="mt-2 text-xl  md:hidden font-semibold p-2"> FullStack Web Dev</span>
              <h2 class="ml-14">The most modern and high-quality design made at a professional level.</h2>
            </div>
          </div>

          <div class="lg:flex mt-8 gap-8 mb-5">
            <div class="p-4 mb-7 lg:mb-0 bg-black/30 lg:w-fit rounded-2xl shadow-[4.0px_8.0px_8.0px_rgba(0,0,0,0.38)] lg:max-w-[50%] w-full">
              <Icon name="iconoir:design-pencil" class="size-[43px]" color="#67e8f9" />
              <span class="mt-2 text-xl font-semibold p-2"> UI/UX Design</span>
              <h2 class="ml-14">The most modern and high-quality design made at a professional level.</h2>
            </div>
            <div class="p-4  bg-black/30 lg:w-fit rounded-2xl shadow-[4.0px_8.0px_8.0px_rgba(0,0,0,0.38)] lg:max-w-[50%] w-full">
              <Icon name="codicon:azure" class="size-[40px]" color="#67e8f9" />
              <span class="mt-2 text-xl hidden md:inline font-semibold p-2"> Microsoft Learn Student Ambassador</span>
              <span class="mt-2 text-xl md:hidden font-semibold p-2"> MLSA</span>
              <h2 class="ml-14">The most modern and high-quality design made at a professional level.</h2>
            </div>
          </div>
        </div>

      </div>
      <div v-if="menuSelected == 'resume'">
        <h1 class="text-3xl p-2 libre font-bold ">Resume</h1>
        <hr class="w-24 ml-2 border-b-4 border-cyan-300 rounded-xl mt-1">
        <div class="flex mt-5">
          <div class="p-4 mr-7 ml-2 bg-black/30 w-fit rounded-2xl shadow-[4.0px_8.0px_8.0px_rgba(0,0,0,0.38)]">
            <Icon name="fluent-mdl2:education" class="size-6" color="#67e8f9" />
          </div>
          <div class=" text-base grow pt-2">
            <h1 class="mt-2 text-2xl font-semibold">EDUCATION</h1>
          </div>
        </div>
        <div class="sm:border-l-[3px] h-[12rem] relative ml-[2.25rem] border-black/30 lg:mb-40 mb-72">
          <ul class="absolute sm:top-2 top-5 left-[0.82rem]">
            <li class="text-xl pl-[2.6rem] mb-10">Vivekananda Institute of Professional Studies
              <div class="text-lg">Bachelors in Computer Science </div>
              <div class="text-xl font-semibold text-cyan-300">2022-2026</div>
              <div class="pt-4">First year GPA: 8.98 </div>
            </li>
            <li class="text-xl pl-[2.6rem] mb-10">Shaheed Rajpal DAV Public School - India
              <div class="text-lg">
                12th Science, PCM with Computer Science </div>
              <div class="text-xl font-semibold text-cyan-300">2006-2021</div>
              <div class="pt-4">Class 12th Science Score: 96% </div>
            </li>
          </ul>
        </div>



        <div class="flex mt-5">
          <div class="p-2 mr-7 ml-2 bg-black/30 w-fit rounded-2xl shadow-[4.0px_8.0px_8.0px_rgba(0,0,0,0.38)]">
            <Icon name="arcticons:adobe-experience-manager" class="size-10" color="#67e8f9" />
          </div>
          <div class=" text-base grow pt-2">
            <h1 class="mt-2 text-2xl font-semibold">EXPERIENCE</h1>
          </div>
        </div>
        <div class="sm:border-l-[3px] h-[13.5rem] relative ml-[2.25rem] border-black/30 sm:mb-56 mb-[38rem]">
          <ul class="absolute sm:top-2 top-5 left-[0.82rem]">
            <li class="text-xl pl-[2.6rem] mb-10">Butterfly Technology
              <div class="text-lg">Internship </div>
              <div class="text-xl font-semibold text-cyan-300">July'23- Sep'23</div>
              <div class="pt-4 w-60 sm:w-full">I've impactful UI designs for a marketing agency and demonstrated the ability to harmonize user-centric experiences with visually captivating interfaces. </div>
            </li>
            <li class="text-xl pl-[2.6rem] mb-10">Microsoft Learn Student Ambassador
              <div class="text-lg">
                <h1 class="hidden sm:block">anishka.gupta@studentambassadors.com</h1><h1 class="block sm:hidden"><a href="mailto:anishka.Gupta@studentambassadors.com">Email</a></h1> </div>
              <div class="text-xl font-semibold text-cyan-300">Nov'23-Current</div>
              <div class="pt-4 mr-5">Student Ambassadors are a global group of campus leaders who are eager to help fellow students, create robust tech communities and develop technical and career skills for the future. </div>
            </li>
          </ul>
        </div>
        <div >
          <h1 class="mt-2 text-3xl font-semibold pl-5 ">My Skills</h1>
          <div class=" mt-5 ml-5 text-xl p-5 rounded-2xl bg-black/40 mr-5">
             Python (PyTorch)
            <div class=" mt-3 mb-7 bg-black/30 rounded-xl">
              <div class="bg-cyan-300 w-3/4 h-3 rounded-xl"></div>
            </div>

             JavaScript (Nuxt, Node.js, Vue)
            <div class=" mt-3 mb-7  bg-black/30 rounded-xl">
              <div class="bg-cyan-300 w-5/6 h-3 rounded-xl"></div>
            </div>

            Java
            <div class=" mt-3 mb-7  bg-black/30 rounded-xl">
              <div class="bg-cyan-300 w-5/6 h-3 rounded-xl"></div>
            </div>

            UI/UX Design
            <div class=" mt-3 mb-7  bg-black/30 rounded-xl">
              <div class="bg-cyan-300 w-6/7 h-3 rounded-xl"></div>
            </div>

            DataBase (MongoDB, SQL)
            <div class=" mt-3 mb-7  bg-black/30 rounded-xl">
              <div class="bg-cyan-300 w-5/6 h-3 rounded-xl"></div>
            </div>

            Logo Designing
            <div class=" mt-3 mb-7  bg-black/30 rounded-xl">
              <div class="bg-cyan-300 w-6/7 h-3 rounded-xl"></div>
            </div>
          </div>
        </div>
      </div>

      <div v-if="menuSelected == 'portfolio'">
        <h1 class="text-3xl p-2 libre font-bold ">Portfolio</h1>
        <hr class="w-24 ml-2 border-b-4 border-cyan-300 rounded-xl mt-1">
        <div class="grid lg:grid-cols-3 md:grid-cols-2 gap-x-3 mt-7 gap-y-7 pl-5">
          <template v-for="d in data">
            <div class="relative" >
              <img :src="d.imageURL" class="w-full h-52 rounded-xl border-4 border-black/30" />
              <a class="absolute block w-full h-52 py-10 bg-black opacity-0 hover:opacity-60 duration-300 rounded-xl cursor-pointer top-0 transition-all" :href="d.link">
                <div class="w-fit mx-auto pt-11">
                  <Icon name="lets-icons:view-alt-fill" class="size-6" color="#67e8f9" ></Icon>
                </div>
              </a>
              <h1 class="text-xl font-semibold text-center pt-2">
              {{ d.title }}
            </h1 >
            <p class="pt-1 text-center">{{ d.description }}</p>
          </div>
        </template>
        </div>
              
      
      
      </div>
      <div v-if="menuSelected == 'contact'">
        <h1 class="text-3xl p-2 libre font-bold ">Contact
        </h1>
        <hr class="w-24 ml-2 border-b-4 border-cyan-300 rounded-xl mt-1">
        <h1 class="ml-2 text-2xl libre mt-10 mb-5">Contact Form</h1>
        <form action="https://formsubmit.co/5d41d56b8e6d39b657eab6ec019ecb15" class="mx-2" method="POST">
          
          <div class="grid grid-cols-2 gap-4">
            <input type="text" class="  p-5 rounded-xl text-xl bg-black/30 border-2 border-black/55  h-14 text-white hover:border-cyan-200 focus:border-blue-300 focus:outline-none" placeholder="Full Name"  name="name" required>
            <input type="email" class="text-white p-5 text-xl rounded-xl bg-black/30 border-2 border-black/55 h-14 hover:border-cyan-200 focus:border-blue-300 focus:outline-none" placeholder="Email Address" name="email" required>
            <textarea class=" col-span-2 p-5 rounded-xl text-xl bg-black/30 border-2 border-black/55 w-full h-80 text-white hover:border-cyan-200 focus:border-blue-300 focus:outline-none" placeholder="Message"  name="message" required rows="35" ></textarea>
  
          </div>
        <button type="submit" class="p-4 mt-4 border-4 border-black/15 text-cyan-200 bg-black/30 w-fit rounded-2xl shadow-[4.0px_8.0px_8.0px_rgba(103,232,249,0.38)] ml-auto block ">Send Message</button>
        </form>
      </div>
    </div>
  </div>

</div>
<div class=" lg:hidden fixed bottom-0 p-4 md:px-10 grid grid-cols-4 w-full bg-gray-300/50 backdrop-blur">
        <h1 @click="changeSelected('about')"
          :class="{ 'text-cyan-300': (menuSelected == 'about'), 'hover:!text-cyan-300': (menuSelected == 'about') }"
          class="md:px-4 px-2 md:text-xl sm:text-base text-sm  text-center cursor-pointer hover:text-gray-200">About Me</h1>
        <h1 @click="changeSelected('resume')"
          :class="{ 'text-cyan-300': (menuSelected == 'resume'), 'hover:!text-cyan-300': (menuSelected == 'resume') }"
          class="md:px-4 px-2 md:text-xl sm:text-base text-sm  text-center cursor-pointer hover:text-gray-200">Resume</h1>
        <h1 @click="changeSelected('portfolio')"
          :class="{ 'text-cyan-300': (menuSelected == 'portfolio'), 'hover:!text-cyan-300': (menuSelected == 'portfolio') }"
          class="md:px-4 px-2 md:text-xl sm:text-base text-sm  text-center cursor-pointer hover:text-gray-200">Portfolio</h1>
        <h1 @click="changeSelected('contact')"
          :class="{ 'text-cyan-300': (menuSelected == 'contact'), 'hover:!text-cyan-300': (menuSelected == 'contact') }"
          class="md:px-4 px-2 md:text-xl sm:text-base text-sm  text-center cursor-pointer hover:text-gray-200">Contacts</h1>
      </div>
  </div>

</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Libre+Franklin&display=swap');

.bgcolor {
  background-color: black;
  /*#967589*/
}

p::-moz-selection {
  background: rgb(33, 90, 90) !important;
}

p::selection {
  background: rgb(33, 90, 90) !important;
}

.libre {
  font-family: 'Libre Franklin', sans-serif;
}

ul{
  list-style-image: url('/dot.png');
}

input::placeholder{
  color:rgb(209 213 219 / 0.3);
}

textarea::placeholder{
  color:rgb(209 213 219 / 0.3);
}
</style>

