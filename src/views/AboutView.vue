<script setup>
import anime from 'animejs/lib/anime.es.js';
import {ref, onMounted} from 'vue';
import LanguageSwitcher from "@/components/LanguageSwitcher.vue"
import '@/assets/imgslider.css'
// import * as skills from '@/assets/skills'


const isChecked = ref(false)

onMounted(()=> {
  mountain()
  cercleTop()
  cercleBottomRight()
  cercleBottomLeft()
  //loadParticles()
})

function loadParticles() {
    tsParticles.load({
        id: "tsparticles",
        options: {
            preset: "snow",
            fullScreen: {
                enable: true, // enabling this will make the canvas fill the entire screen, it's enabled by default
                zIndex: -1, // this is the z-index value used when the fullScreen is enabled, it's 0 by default
            },
            interactivity: {
                detectsOn: "window"
            }
        },
    });
}


const handleCheckboxChange = () => {
  if (isChecked.value) {
    console.log("La checkbox est cochée!");
    document.querySelector('.mountain').style.display = 'none'
    document.querySelector('#welcome').style.display = 'none'
    document.querySelector('.slidiv').style.display = 'none'

    // Appeler votre fonction ici
  } else {
    console.log("La checkbox est décochée!");
    // Appeler une autre fonction si nécessaire
    document.querySelector('.mountain').style.display = ''
    document.querySelector('#welcome').style.display = ''
    document.querySelector('.slidiv').style.display = ''
  }
};

// function snowflakes() {

//     var maDate = new Date();  
//     var mois = maDate.getMonth();

//     // if (mois >= 11 || (mois >= 0 && mois <= 2)) {
//       /* particlesJS.load(@dom-id, @path-json, @callback (optional)); */
//         particlesJS.load('particles-js', 'assets/particles.json', function() {
//             console.log('callback - particles.js config loaded');
//         });
//     // }

// }

function mountain() {

    let timeline = anime.timeline()

    timeline.add({
            targets: '.mountain',
            opacity: 1, // Faire apparaître la div avec une opacité de 1
            duration: 500, // Durée de l'animation en millisecondes
            easing: 'easeInOutQuad' // Type d'interpolation pour l'animation
    })
    .add({
            targets: '#welcome',
            opacity: 1, // Faire apparaître la div avec une opacité de 1
            duration: 300, // Durée de l'animation en millisecondes
            easing: 'easeInOutQuad' // Type d'interpolation pour l'animation
    })
    .add({
            targets: '.mountain',
            translateX: '-50px', // Déplacer la div de 200 pixels vers la gauche
            duration: 800, // Durée de l'animation en millisecondes
            easing: 'easeInOutQuad' // Type d'interpolation pour l'animation
    });

    timeline.play()
}

function cercleTop() {

    let timeline = anime.timeline()

    anime({
      targets: '.cercle1',
      width: '4rem', // Taille finale en vw
      height: '4rem', // Taille finale en vw (pour maintenir la forme de cercle)
      duration: 1000, // Durée de l'animation en millisecondes
      easing: 'easeInOutQuad' // Type d'interpolation pour l'animation
    })
  
    anime({
        targets: '.cercle2',
        width: '4rem', // Taille finale en vw
        height: '4rem', // Taille finale en vw (pour maintenir la forme de cercle)
        duration: 1000, // Durée de l'animation en millisecondes
        easing: 'easeInOutQuad' // Type d'interpolation pour l'animation
    })
    
    anime({
        targets: '.cercle3',
        width: '5rem', // Taille finale en vw
        height: '5rem', // Taille finale en vw (pour maintenir la forme de cercle)
        duration: 1000, // Durée de l'animation en millisecondes
        easing: 'easeInOutQuad' // Type d'interpolation pour l'animation
    });

    timeline.play()
}


function cercleBottomRight() {

    anime({
      targets: '.cerclebottomright1',
      width: '5rem', // Taille finale en vw
      height: '5rem', // Taille finale en vw (pour maintenir la forme de cercle)
      duration: 1000, // Durée de l'animation en millisecondes
      easing: 'easeInOutQuad' // Type d'interpolation pour l'animation
    })

    anime({
      targets: '.cerclebottomright2',
      width: '5rem', // Taille finale en vw
      height: '5rem', // Taille finale en vw (pour maintenir la forme de cercle)
      duration: 1000, // Durée de l'animation en millisecondes
      easing: 'easeInOutQuad' // Type d'interpolation pour l'animation
    })

    anime({
      targets: '.cerclebottomright3',
      width: '5rem', // Taille finale en vw
      height: '5rem', // Taille finale en vw (pour maintenir la forme de cercle)
      duration: 1000, // Durée de l'animation en millisecondes
      easing: 'easeInOutQuad' // Type d'interpolation pour l'animation
    })

    anime({
      targets: '.cerclebottomright4',
      width: '4rem', // Taille finale en vw
      height: '4rem', // Taille finale en vw (pour maintenir la forme de cercle)
      duration: 1000, // Durée de l'animation en millisecondes
      easing: 'easeInOutQuad' // Type d'interpolation pour l'animation
    })
}


function cercleBottomLeft() {

anime({
  targets: '.cerclebottomleft1',
  width: '5rem', // Taille finale en vw
  height: '5rem', // Taille finale en vw (pour maintenir la forme de cercle)
  duration: 1000, // Durée de l'animation en millisecondes
  easing: 'easeInOutQuad' // Type d'interpolation pour l'animation
})

anime({
  targets: '.cerclebottomleft2',
  width: '5rem', // Taille finale en vw
  height: '5rem', // Taille finale en vw (pour maintenir la forme de cercle)
  duration: 1000, // Durée de l'animation en millisecondes
  easing: 'easeInOutQuad' // Type d'interpolation pour l'animation
})

anime({
  targets: '.cerclebottomleft3',
  width: '5rem', // Taille finale en vw
  height: '5rem', // Taille finale en vw (pour maintenir la forme de cercle)
  duration: 1000, // Durée de l'animation en millisecondes
  easing: 'easeInOutQuad' // Type d'interpolation pour l'animation
})

anime({
  targets: '.cerclebottomleft4',
  width: '4rem', // Taille finale en vw
  height: '4rem', // Taille finale en vw (pour maintenir la forme de cercle)
  duration: 1000, // Durée de l'animation en millisecondes
  easing: 'easeInOutQuad' // Type d'interpolation pour l'animation
})
}

function slide(){
    let slideValue = document.getElementById("slider").value;
    document.getElementById("my-img").style.clipPath = "polygon(0 0," + slideValue + "% 0," + slideValue + "% 100%, 0 100%)";
    // console.log("polygon(0 0," + slideValue + "% 0," + slideValue + "% 100%, 0 100%)");
}

</script>

<template>


<input type="checkbox" v-model="isChecked" @change="handleCheckboxChange" id="burger-toggle">
<label for="burger-toggle" class="burger-menu">
  <div class="line"></div>
  <div class="line"></div>
  <div class="line"></div>
</label>

<div class="menu">
  <div class="menu-inner">
    <ul class="menu-nav">
      <li class="menu-nav-item"><a class="menu-nav-link" href="#"><span class="divitemenu">
            <div>{{$t("nav.home")}}</div>
          </span></a></li>
          <li class="menu-nav-item"><router-link class="menu-nav-link" to="/projects"><span  class="divitemenu">
            <div>{{$t("nav.projects")}}</div>
          </span></router-link></li>
      <li class="menu-nav-item"><a class="menu-nav-link" href="/"><span  class="divitemenu">
            <div>{{$t("nav.skills")}}</div>
          </span></a></li>
    <li class="menu-nav-item"><a class="menu-nav-link" href="/"><span class="divitemenu">
            <div>{{$t("nav.contact")}}</div>
          </span></a></li>
    </ul>
    <div class="gallery">
      <div class="title">
        <LanguageSwitcher></LanguageSwitcher>
        <p class="mt-8">{{ $t('nav.discovery') }}</p>
      </div>
      <div class="images">
        <router-link class="image-link" to="/projects">
          <div class="image" data-label="Projet universitaire"><img src="https://imgur.com/U30rNFW.png" alt=""></div>
        </router-link>
        <router-link class="image-link" to="/projects">
          <div class="image" data-label="Bénévolat"><img src="https://imgur.com/T8nR2pG.png" alt=""></div>
        </router-link>
        <router-link class="image-link" to="/projects">
          <div class="image" data-label="Stage en entreprise"><img src="https://imgur.com/JL1vjyP.png" alt=""></div>
        </router-link>
        <router-link class="image-link" to="/projects">
          <div class="image" data-label="Projet web"><img src="https://imgur.com/QEknUuq.png" alt=""></div>
        </router-link>
      </div>
    </div>
  </div>
</div>


<div class="cercle2 w-8 h-8 bg-light-cloudColor rounded-full absolute -top-6 left-12"></div>
<div class="cercle3 w-10 h-10 bg-light-cloudColor rounded-full absolute -top-5 -left-5"></div>
<div class="cercle1 w-8 h-8 bg-light-cloudColor rounded-full absolute top-12 -left-8"></div>

<div class="cercle2 w-8 h-8 bg-light-cloudColor rounded-full absolute -top-6 right-12"></div>
<div class="cercle3 w-10 h-10 bg-light-cloudColor rounded-full absolute -top-5 -right-5"></div>
<div class="cercle1 w-8 h-8 bg-light-cloudColor rounded-full absolute top-12 -right-8"></div>

<div class="cerclebottomright1 w-10 h-10 bg-light-cloudColor rounded-full absolute"></div>
<div class="cerclebottomright2 w-10 h-10 bg-light-cloudColor rounded-full absolute"></div>
<div class="cerclebottomright3 w-10 h-10 bg-light-cloudColor rounded-full absolute"></div>
<div class="cerclebottomright4 w-10 h-10 bg-light-cloudColor rounded-full absolute"></div>

<div class="cerclebottomleft1 w-10 h-10 bg-light-cloudColor rounded-full absolute"></div>
<div class="cerclebottomleft2 w-10 h-10 bg-light-cloudColor rounded-full absolute"></div>
<div class="cerclebottomleft3 w-10 h-10 bg-light-cloudColor rounded-full absolute"></div>
<div class="cerclebottomleft4 w-10 h-10 bg-light-cloudColor rounded-full absolute"></div>

<div class="h-screen w-screen">
    <div class="flex pres flex-col lg:flex-row items-center justify-center">
        <img class="mountain ml-24 w-40 md:w-64 lg:w-80" src="../assets/mountain.svg" alt=""> 
    
        <section id="welcome" class="">
                            <p id="hello" class="first text-center lg:text-left">{{ $t('home.first') }}</p>
                            <p id="name"  class="second py-[15px] text-5xl text-center lg:text-left">{{ $t('home.second') }}</p>
                            <p id="desc"  class="third text-center lg:text-left">{{ $t('home.third') }}</p>
                            <a href="#aboutSection" id="knowMore" class="fourth text-center text-lg lg:text-left"><p>{{ $t('home.fourth') }}</p></a>
        </section>
    </div>
</div>

<section id="aboutSection" class="flex flex-col lg:flex-row items-center justify-center gap-10">

    <article class="basis-1/3 flex flex-col justify-center items-center">
                    <h1 class="text-4xl first text-center ">{{ $t('about.first') }}</h1>
                    <p class="second mt-5 text-md w-4/5 lg:text-lg text-justify text-about">
                        {{ $t('about.second') }}
                    </p>
                    <a href="/projects" id="knowMoreProject" class="third text-lg mt-5 mr-5">{{ $t('about.third') }}</a>
    
    </article>
    <div class="divImg flex flex-col  items-center justify-center ">
        <div class="slidiv">
            <!-- <img class="imgslide" src="../assets/actual_jim.jpg"> -->
            <img class="" id="imgJim" src="../assets/choupi_jim.jpeg">
            <!-- <input type="range" min="0" max="100" value="50" id="slider" :oninput="slide"> -->
          </div>
          <a class="mt-[15px]" :href="$t('about.cv_path')" target="_blank" id="dlCV">{{ $t('about.cv_title') }} <ion-icon name="open-outline"></ion-icon></a>
          <!-- <span class="italic">Jimmy découvre Stack Overflow, 2009</span> -->
    </div>
        <!-- <p class="text-black">testifgdifhgkjfdhgkhdsfjkghdfhgkdfghdfghkdjghdkfjhgkjdfhgkhdfkjgdfghdjkfhkdjhgkdfhgdhdkj</p> -->
</section>

<div class="space"></div>


<section id="skillMobile" class="lg:hidden">

  <section  class="flex flex-col items-center justify-center">

<article class="articleSkill m-16 pr-32 pl-32 pb-32 grid grid-rows-2 justify-center items-center ">
                <h1 class="text-4xl first text-center ">{{$t('skills.cat1')}}</h1>
                <div class="grid grid-cols-2 gap-[60px] place-items-center content-center">
                  <div v-for="(e, index) in $tm('skills.softwares')" class="grid place-items-center content-center">
                      <img class="w-[50px]" :src="'../assets/skills/' + $rt(`${e}.src`)" alt="">
                      <span class="titleskills">{{ $rt(e.title) }}</span>
                  </div>
                </div>
</article>
</section>

<section  class="flex flex-col items-center justify-center gap-10">

<article class="articleSkill m-16 pr-32 pl-32 pb-32 grid grid-rows-2 justify-center items-center ">
                <h1 class="text-4xl first text-center ">{{$t('skills.cat2')}}</h1>
                <div class="grid grid-cols-4 gap-[85px] place-items-center content-center">
                  <div v-for="(e, index) in $tm('skills.back')" class="grid place-items-center content-center">
                      <img class="w-[50px]" :src="$rt(e.src)" alt="">
                      <span class="titleskills">{{ $rt(e.title) }}</span>
                  </div>
                </div>
</article>
</section>

<section  class="flex flex-col items-center justify-center gap-10">

<article class="articleSkill m-16 pr-32 pl-32 pb-32 grid grid-rows-2 justify-center items-center ">
                <h1 class="text-4xl first text-center ">{{$t('skills.cat3')}}</h1>
                <div class="grid grid-cols-4 gap-[60px] place-items-center content-center">
                  <div v-for="(e, index) in $tm('skills.front')" class="grid place-items-center content-center">
                      <img class="w-[50px]" :src="$rt(e.src)" alt="">
                      <span class="titleskills">{{ $rt(e.title) }}</span>
                  </div>
                </div>
</article>
</section>

<section  class="flex flex-col items-center justify-center gap-10">

<article class="articleSkill m-16 pr-32 pl-32 pb-32 grid grid-rows-2 justify-center items-center ">
                <h1 class="text-4xl first text-center ">{{$t('skills.cat4')}}</h1>
                <div class="grid grid-cols-4 gap-[60px] place-items-center content-center">
                  <div v-for="(e, index) in $tm('skills.design')" class="grid place-items-center content-center">
                      <img class="w-[50px]" :src="$rt(e.src)" alt="">
                      <span class="titleskills">{{ $rt(e.title) }}</span>
                  </div>
                </div>
</article>
</section>

</section>


<section class="skillSection flex justify-center hidden lg:block">
  <div class="containeur">

    <div class="topic">{{ $t('skills.title') }}</div>

    <div class="content">
        <input type="radio" name="slider" checked id="home">
        <input type="radio" name="slider" id="blog">
        <input type="radio" name="slider" id="help">
        <input type="radio" name="slider" id="code">
        <input type="radio" name="slider" id="about">

        <div class="list" >
            <label :id="c.ref + 'Label'" v-for="c in $tm('skills.categories')" :for="c.ref" :class="c.ref">
                <span class="catskills">{{ $rt(c.title) }}</span>
            </label>
            <div class="slider"></div>
        </div>

        <div class="text-content">
            <div class="home text">
                    <div class="grid grid-cols-4 gap-10 place-items-center content-center">
                        <div v-for="(e, index) in $tm('skills.softwares')" class="grid place-items-center content-center">
                            <img :src="$rt(e.src)" width="100" height="100" alt="">
                            <span class="titleskills">{{ $rt(e.title) }}</span>
                        </div>
                    </div>
            </div>
            <div class="blog text">
                <div class="grid grid-cols-4 gap-10 place-items-center content-center">
                        <div v-for="(e, index) in $tm('skills.back')" class="grid place-items-center content-center">
                            <img :src="$rt(e.src)" width="100" height="100" alt="">
                            <span class="titleskills">{{ $rt(e.title) }}</span>
                        </div>
                </div>    
            </div>
            <div class="help text">
                <div class="grid grid-cols-4 gap-10 place-items-center content-center">
                        <div v-for="(e, index) in $tm('skills.front')" class="grid place-items-center content-center">
                            <img class="testcolor" :src="$rt(e.src)" width="100" height="100" alt="">
                            <span class="titleskills">{{ $rt(e.title) }}</span>
                        </div>
                </div>     
            </div>
            <div class="code text">
                <div class="grid grid-cols-4 gap-10 place-content-center place-items-center content-center">
                        <div v-for="(e, index) in $tm('skills.design')" class="grid place-content-center place-items-center content-center">
                            <img :src="$rt(e.src)" width="100" height="100" alt="">
                            <span class="titleskills">{{ $rt(e.title) }}</span>
                        </div>
                </div>     
            </div>
        </div>
    </div>
  </div>
</section>

<div class="space"></div>

  <ul id="contactList" class="flex flex-col lg:flex-row justify-center items-center">
    <!-- Mail, linkedin, github, discord -->
    <li class="contactListElement" onclick="window.open('https://www.linkedin.com/in/jimmy-leichtmann/','_blank');">
        <span class="icon"><ion-icon name="logo-linkedin"></ion-icon></span>
        <span class="title">in/jimmy-leichtmann/</span>
    </li>
    <li class="contactListElement" onclick="window.open('https://github.com/leichtmj', '_blank')">
        <span class="icon"><ion-icon name="logo-github"></ion-icon></span>
        <span class="title">leichtmj</span>
    </li>
    <li class="contactListElement liveToastBtn" onclick="copyID(discord)">
        <span class="icon"><ion-icon name="logo-discord"></ion-icon></span>
        <span class="title" id="discord">@jimsoryulangley</span>
    </li>
    <li class="contactListElement liveToastBtn" onclick="copyID(mail)">
        <span class="icon"><ion-icon name="mail-outline"></ion-icon></span>
        <span class="title" id="mail">jimmy.leichtmann@etu.univ-smb.fr</span>
    </li>
    </ul>

<div class="space"></div>

<section class="w-full h-52 bg-light-footer grid grid-cols-1 place-items-center content-center place-content-center">
    <div class="footertitle flex text-xl"><span  class="spaceright">&copy; 2024 Jimmy LEICHTMANN</span> <img src="../assets/skills/license.svg" width="25" height="25" alt="" class="spaceright"> <span class="spaceright">MIT License</span></div>
</section>

</template>../assets/app.js