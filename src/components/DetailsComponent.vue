<template>
    <swiper-container class="font"
    :breakpoints="swiperBreakpoints"
      slides-per-view="5"
      loop="true"
      navigation="true"
      pagination="true"
      space-between="20"
      mousewheel-enabled="true"
      
    >
    <swiper-slide>
        <h2>Général</h2>
        <ul>
          <li>15 Mars</li>
          <li>1 Rue des Granges, Salle des fêtes</li>
          <li><a href="https://www.bressenordintercom.fr/communes/bellevesvre/" target="_blank">Bellevesvre</a></li>
          <li>19h</li>
          <li>150 places disponibles</li>
        </ul>
    </swiper-slide>
    <swiper-slide>
        <h2>Prix</h2>
        <ul>
          <li>L'entrée est à 5 euros</li>
          <li>Paiement par carte possible</li>
          <li>L'entrée est <span class="green">gratuite</span> pour les <span class="green"> - 12 ans</span> </li>
          <li>1 kilt = une boisson offerte</li>
          <li>La consommation d'alcool est <br> <span class="forbidden">interdite</span>aux mineurs</li>
        </ul>
      </swiper-slide>
      <swiper-slide>
        <h2>Déroulement</h2>
        <ul>
          <li>Trois groupes sont programmés :</li>
          <li class="font">Valkyrie (chanteuse Pop/Rock)</li>
          <li><a href="https://www.facebook.com/4.Squared.Circles/" target="_blank">4 squared circles (Rock Français)</a></li>
          <li><a href="https://www.facebook.com/p/Boddah-Quest-tribute-Nirvana-100078758354425/" target="_blank">Boddah Nirvanah Tribute (Hommage Nirvana)</a></li>
        </ul>
      </swiper-slide>
      <swiper-slide>
        <h2>Rappel</h2>
        <ul>
          <li>L'événement doit se passer dans la convivialité</li>
          <li>La consommation d'alcool doit rester raisonnable</li>
          <li>L'événement est accessible dans la limite des places disponibles</li>
        </ul>
    </swiper-slide>
    <swiper-slide>
        <h2>Bonus</h2>
        <ul>
          <li>Le happy quart d'heure permettra de gagner une boisson en faisant un centre sur la cible (3 essais par participant)</li>
          <li>Les bouchons d'oreilles sont fournis à l'entrée pour le concert (fortement conseillé)</li>
          <li>Vous pouvez choisir de participer à une tombola calendrier en vous inscrivant à l'entrée <img :src="greenCoinSrc" alt="logo jeton vert"> <img :src="greenCoinSrc" alt="logo jeton vert"></li>
        </ul>
    </swiper-slide>
    <swiper-slide>
        <h2>Boissons Alcool</h2>
        <ul>
          <li><img :src="blondeBeerSrc" alt="logo biere blonde"> 2,5 euros (25cl) <img :src="greenCoinSrc" alt="logo jeton vert"> <img :src="greenCoinSrc" alt="logo jeton vert"> <img :src="yellowCoinSrc" alt="logo jeton jaune"></li>
          <li><img :src="amberBeerSrc" alt="logo biere ambree"> : 3,5 euros (25cl) <img :src="greenCoinSrc" alt="logo jeton vert"> <img :src="greenCoinSrc" alt="logo jeton vert"> <img :src="greenCoinSrc" alt="logo jeton vert"> <img :src="yellowCoinSrc" alt="logo jeton jaune"></li>
          <li><img :src="wizardBeerSrc" alt="logo biere blonde"> : 3,5 euros (25cl) <img :src="greenCoinSrc" alt="logo jeton vert"> <img :src="greenCoinSrc" alt="logo jeton vert"> <img :src="greenCoinSrc" alt="logo jeton vert"> <img :src="yellowCoinSrc" alt="logo jeton jaune"></li>
          <li>Pichet blonde : 9 euros (1L)</li>
        </ul>
    </swiper-slide>
    <swiper-slide>
        <h2>Boissons Sans Alcool</h2>
        <ul>
          <li>Bière : 2 euros <img :src="greenCoinSrc" alt="logo jeton vert"> <img :src="greenCoinSrc" alt="logo jeton vert"></li>
          <li>Coca, coca zéro, Orangina, Ice Tea, Tropical : 2 euros <img :src="greenCoinSrc" alt="logo jeton vert"> <img :src="greenCoinSrc" alt="logo jeton vert"></li>
          <li>Cristaline (0,5l) : 1 euro <img :src="greenCoinSrc" alt="logo jeton vert"></li>
        </ul>
    </swiper-slide>
    <swiper-slide>
        <h2>Tarifs restauration</h2>
        <ul>
          <li>Hot dog : 3,5 euros <img :src="greenCoinSrc" alt="logo jeton vert"> <img :src="greenCoinSrc" alt="logo jeton vert"> <img :src="greenCoinSrc" alt="logo jeton vert"> <img :src="yellowCoinSrc" alt="logo jeton jaune"></li>
          <li>Sandwich rosette beurre : 3 euros <img :src="greenCoinSrc" alt="logo jeton vert"> <img :src="greenCoinSrc" alt="logo jeton vert"> <img :src="greenCoinSrc" alt="logo jeton vert"></li>
          <li>Confiseries : 1 euro <img :src="greenCoinSrc" alt="logo jeton vert"></li>
        </ul>
    </swiper-slide>
    <swiper-slide>
        <h2>Paiement</h2>
        <ul>
          <li>Le paiement se fait à l'entrée en échange de jetons.</li>
          <li>Deux jetons uniquement sont disponibles</li>
          <li><img :src="yellowCoinSrc" alt="logo jeton jaune"> : 0,5 euro</li>
          <li><img :src="greenCoinSrc" alt="logo jeton vert"> : 1 euro</li>
        </ul>
    </swiper-slide>
    </swiper-container>
  </template>

  <script>
  import 'swiper/swiper-bundle.css';
  import { register } from 'swiper/element/bundle';
  import { ref, computed, onMounted, onUnmounted } from "vue";
  import blondBeerMobileSrc from "../assets/images/images/mobile/beer-blond-mobile.svg";
  import blondBeerDesktopSrc from "../assets/images/images/desktop/beer-blond-desktop.svg";
  import amberBeerMobileSrc from "../assets/images/images/mobile/beer-amber-mobile.svg";
  import amberBeerDesktopSrc from "../assets/images/images/desktop/beer-amber-desktop.svg";
  import wizardBeerMobileSrc from "../assets/images/images/mobile/beer-wizard-mobile.svg";
  import wizardBeerDesktopSrc from "../assets/images/images/desktop/beer-wizard-desktop.svg";
  import coinYellowMobileSrc from "../assets/images/images/mobile/coin-yellow-mobile.svg";
  import coinYellowDesktopSrc from "../assets/images/images/desktop/coin-yellow-desktop.svg";
  import coinGreenMobileSrc from "../assets/images/images/mobile/coin-green-mobile.svg";
  import coinGreenDesktopSrc from "../assets/images/images/desktop/coin-green-desktop.svg";
  
  export default {
  name: "SwiperWithBreakpoints",
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

    const blondeBeerSrc = computed(() =>
      isDesktop.value ? blondBeerDesktopSrc : blondBeerMobileSrc
    );

    const wizardBeerSrc = computed(() =>
      isDesktop.value ? wizardBeerDesktopSrc : wizardBeerMobileSrc
    );

    const amberBeerSrc = computed(() =>
      isDesktop.value ? amberBeerDesktopSrc : amberBeerMobileSrc
    );

    const yellowCoinSrc = computed(() =>
      isDesktop.value ? coinYellowDesktopSrc : coinYellowMobileSrc
    )

    const greenCoinSrc = computed(() =>
      isDesktop.value ? coinGreenDesktopSrc : coinGreenMobileSrc
    )

    // Register Swiper Web Components globally
    register();

    // Define breakpoints
    const swiperBreakpoints = {
      320: {
        slidesPerView: 1,
        spaceBetween: 10,
      },
      991: {
        slidesPerView: 1,
        spaceBetween: 20,
      },
      2048: {
        slidesPerView: 2,
        spaceBetween: 20,
      },
      4080: {
        slidesPerView: 4,
        spaceBetween: 30,

      },
    };

    return {
      swiperBreakpoints,
      isDesktop,
      blondeBeerSrc,
      wizardBeerSrc,
      amberBeerSrc,
      yellowCoinSrc,
      greenCoinSrc
    };
  },
};
  </script>

<style scoped lang="scss">

// ********************** GENERAL
    a {
        color: lime;
    }

    .forbidden {
      animation: shake 1.2s ease-in-out 3s 3;
      color: red;
      position: relative;
      left: 0;
      text-transform: uppercase;
    }

    span {
      display: flex;
      justify-content: space-around;
      align-items: center;
    }

    li {
      font-size: 1rem;
      display: flex;
      justify-content: space-evenly;
      align-items: center;
    }

    swiper-container {
      opacity: 0;
      animation: opacity .3s .3s ease forwards
    }

    // ********************** MEDIA

    @media (min-width:320px) and (max-width:991px) {

      h2 {
        letter-spacing: 5px;
        font-size: 1.5rem;
      }

      ul {
        li {
          margin: 8vw auto;
          line-height: 40px;
          font-size: 1.2rem;

          a {
            font-size: inherit;
          }
        }

      }
    }

    @media (min-width:991px) and (max-width:2048px) {

      h2 {
        letter-spacing: 7px;
        font-size: 2.5rem;
      }
      
      ul li {
        margin: 4vw auto;
        font-size: 1.8rem;
        line-height: 40px;

        a {
          font-size: inherit;
        }
      }
    }

    @media (min-width:2048px) {

      h2 {
        letter-spacing: 25px;
        font-size: 3rem;
        margin-bottom: 100px;
      }
      ul li {
      margin: 2vw auto;
      font-size: 1.8rem;

      a {
        font-size: inherit;
      }
    }
    }

    // *************************SWIPER

    swiper-container::part(bullet-active) {
      background-color: lime;
    }

    swiper-container::part(bullet) {
      background-color: red;
    }

    swiper-container::part(button-prev), swiper-container::part(button-next) {
      color: lime;
    }
    
    //******************* */ Animation

    @keyframes shake {
      23% {
        left: -2vw;
      }
      48% {
        left: 2vw;
      }
      73% {
        left: -2vw;
      }
      98% {
        left: 0;
      }
    }
</style>