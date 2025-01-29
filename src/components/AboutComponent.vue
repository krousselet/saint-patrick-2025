<template>
    <main>
      <div class="skull-container">
        <img :src="skullSrc" alt="logo association skull darts 71">
      </div>
      <div class="informations">
        <div class="title-container">
            <h2>Skull darts 71 ?</h2>
        </div>
        <div class="text">
            <p class=".text-one">Skull Darts est une association de fléchettes regroupant des participants amateurs.</p>
            <p class=".text-two" >Elle est basée dans le village de <a href="https://www.bressenordintercom.fr/communes/bellevesvre/" target="_blank"><span id="bellevesvre">Bellevesvre</span></a>.</p>
            <p class=".text-three">Celle-ci compte actuellement {{ membres }} membres, mais nous accueillons à bras ouverts chaque nouvelle personne.</p>
        </div>
      </div>
      
    </main>
  </template>
  
  <script>

import { ref, computed, onMounted, onUnmounted } from "vue";
import skullMobileSrc from "../assets/images/logos/logos-mobile/skull.png";
import skullDesktopSrc from "../assets/images/logos/logos-desktop/skull.png";
  export default {
    name: 'AboutComponent',
    props: {
        membres: Number,
    },
    setup() {
    const isDesktop = ref(window.matchMedia("(min-width: 992px)").matches);

    const updateIsDesktop = () => {
      isDesktop.value = window.matchMedia("(min-width: 992px)").matches;
    };

    onMounted(() => {
      window.addEventListener("resize", updateIsDesktop);
    });

    onUnmounted(() => {
      window.removeEventListener("resize", updateIsDesktop);
    });

    const skullSrc = computed(() =>
      isDesktop.value ? skullDesktopSrc : skullMobileSrc
    );

    return {
      isDesktop,
      skullSrc,
    };
  },
  }
  </script>
  
  <style scoped lang="scss">

.skull-container {
    opacity: 0;
    animation: opacity 1s .2s ease-in-out forwards;
}

.title-container {
  opacity: 0;
  animation: opacity 1s .5s ease-in-out forwards;
}

.text {
  opacity: 0;
  animation: opacity 1s .7s ease-in-out forwards;
}

.text-one {
  opacity: 0;
  animation: opacity 1s .9s ease-in-out forwards;
}

.text-two {
  opacity: 0;
  animation: opacity 1s 1.1s ease-in-out forwards;
}

.text-three {
  opacity: 0;
  animation: opacity 1s 1.3s ease-in-out forwards;
}


  #bellevesvre {
    color: lime;
  }

  @media (min-width:320px) and (max-width:991px) {
    .skull-container {
      margin-top: 5vw;
    }
  }


  @media (min-width:992px) {
    main {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      grid-template-rows: 1fr;
      }
      
        .skull-container {
            width: 100%;
    
            img {
                width: 75%;
                border-radius: 25%;
            }
        }

        .informations {

          margin: 10vw auto;

            .title-container {
              font-size: 3rem;
            }

            .text {

              p {
                  margin-bottom: 2vw;
                  font-size: 1.2rem;
              }
            }
        }
      }
  </style>