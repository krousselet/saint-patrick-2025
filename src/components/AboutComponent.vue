<template>
    <main>
      <div class="skull-container image-container">
        <img :src="skullSrc" alt="logo association skull darts 71">
      </div>
      <div class="informations">
        <div class="title-container">
            <h2>Skull darts 71 ?</h2>
        </div>
        <div class="text">
          <p class="text-zero">Skull Darts 71 est née en 2023.</p>
          <p class="text-one">Il s'agit d'une association de fléchettes regroupant des participants amateurs.</p>
          <p class="text-two" >Elle est basée dans le village de <a href="https://www.bressenordintercom.fr/communes/bellevesvre/" target="_blank"><span id="bellevesvre">Bellevesvre</span></a>.</p>
          <p class="text-three">Celle-ci compte actuellement {{ membres }} membres, mais nous accueillons à bras ouverts chaque nouvelle personne.</p>
          <p class="text-four">Nous nous retrouvons le vendredi soir, où le but essentiel est de se reposer et de rire dans la convivialité et la bonne humeur.</p>
        </div>
      </div>
      <div class="group-container image-container appear-three">
        <img :src="groupSrc" alt="image groupe skull darts 71">
      </div>
      <div class="informations">
        <div class="title-container">
            <h2>Saint Patrick 2024</h2>
        </div>
        <div class="text">
          <p class="appear-zero">Voici une image de la dernière Saint Patrick</p>
          <p class="appear-one">Comme vous le constaterez, l'association a tout de même bien grandi depuis...</p>
          <p class="appear-two" >C'est avec le même engouement que nous vous attendrons cette année.</p>
          <p class="appear-three">N'oubliez pas que l'adhésion est toujours quelque chose que nous avons à coeur</p>
          <p class="appear-four">Alors n'hésitez pas à nous rejoindre si le coeur vous en dit. Tout seul on va plus vite, ensemble, on va plus loin !</p>
        </div>
      </div>
      
    </main>
  </template>
  
  <script>

import { ref, computed, onMounted, onUnmounted } from "vue";
import skullMobileSrc from "../assets/images/logos/logos-mobile/skull.png";
import groupMobileSrc from "../assets/images/about/mobile/photo-groupe-mobile.png";
import skullDesktopSrc from "../assets/images/logos/logos-desktop/skull.png";
import groupDesktopSrc from "../assets/images/about/desktop/photo-groupe-desktop.png";
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

    const groupSrc = computed(() =>
      isDesktop.value ? groupDesktopSrc : groupMobileSrc
    );

    return {
      isDesktop,
      skullSrc,
      groupSrc
    };
  },
  }
  </script>
  
  <style scoped lang="scss">

.image-container {
  position: relative;
  overflow-x: hidden;
  // img {
  //   position: absolute;
  //   left: 100%;
  //   animation: left 1s .3s ease-in-out forwards;
  // }
}

.skull-container {
    opacity: 0;
    animation: opacity 1s .3s ease-in-out forwards;
}

.title-container {
  position: relative;
  opacity: 0;
  right: -100%;
  animation: opacity 1s .5s ease-in-out forwards, right 1s .5s ease-in-out forwards;
  overflow-x: hidden;
}

.text {
  opacity: 0;
  animation: opacity 1s .5s ease-in-out forwards;
  text-align: justify;
  overflow-x: hidden;
  right: -100%;
  position: relative;
  animation: opacity 1s .5s ease-in-out forwards, right 1s .7s ease-in-out forwards;
}

.appear-zero {
  position: relative;
  opacity: 0;
  animation: opacity 1s .7s ease-in-out forwards, right 1s .9s ease-in-out forwards;
}

.appear-one {
  position: relative;
  opacity: 0;
  animation: opacity 1s .9s ease-in-out forwards;
}

.appear-two {
  position: relative;
  opacity: 0;
  animation: opacity 1s 1.1s ease-in-out forwards;
}

.appear-three {
  opacity: 0;
  animation: opacity 1s 1.3s ease-in-out forwards;
}

.appear-four {
  position: relative;
  opacity: 0;
  animation: opacity 1s 1.5s ease-in-out forwards;
}

  #bellevesvre {
    color: lime;
  }

  @media (min-width:320px) and (max-width:991px) {
    .skull-container {
      margin-top: 5vw;
    }

    .title-container {
      font-size: 30px;
    }

    .informations {
      margin: 5vw auto;

      .text {
        max-width: 550px;
        margin: 0 auto;
        text-align: center;
  
        p {
          font-size: 20px;
          line-height: 30px;
        }
      }
    }

  }

  @media (min-width: 992px) and (max-width:2048px) {
    main {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      grid-template-rows: 1fr;
      }
      
        .image-container {
            max-width: 1024px;
            max-height: 1024px;
    
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
                  font-size: 1.5rem;
              }
            }
        }
  }

  @media (min-width: 2048px) {
    main {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      grid-template-rows: 1fr;
      }
      
        .image-container {
            max-width: 1024px;
            max-height: 1024px;
    
            img {
                width: 75%;
                border-radius: 25%;
            }
        }

        .informations {

          margin: 15vw auto;

            .title-container {
              font-size: 3rem;
            }

            .text {

              p {
                  margin-bottom: 2vw;
                  font-size: 1.8rem;
                  line-height: 5.5vh;
              }
            }
        }

  }
  </style>