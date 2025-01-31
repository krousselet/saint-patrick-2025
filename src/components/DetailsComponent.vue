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
          <li>2 Rue des Granges</li>
          <li><a href="https://www.bressenordintercom.fr/communes/bellevesvre/" target="_blank">Bellevesvre</a></li>
          <li>19h</li>
          <li>150 places disponibles</li>
        </ul>
    </swiper-slide>
    <swiper-slide>
        <h2>Prix</h2>
        <ul>
          <li>L'entrée est à 5 euros</li>
          <li>1 kilt = une boisson offerte</li>
          <li>La consommation d'alcool est <br> <span class="forbidden">interdite</span> <br> aux mineurs</li>
        </ul>
      </swiper-slide>
      <swiper-slide>
        <h2>Déroulement</h2>
        <ul>
          <li>Trois groupes sont programmés :</li>
          <li><a href="https://www.facebook.com/4.Squared.Circles/" target="_blank">4 squared circles</a></li>
          <li><a href="https://www.facebook.com/p/Boddah-Quest-tribute-Nirvana-100078758354425/" target="_blank">Boddah</a></li>
          <li class="font">Valkyrie</li>
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
    </swiper-container>
  </template>

  <script>
  import 'swiper/swiper-bundle.css';
  import { register } from 'swiper/element/bundle';
  
  export default {
  name: "SwiperWithBreakpoints",
  setup() {
    // Register Swiper Web Components globally
    register();

    // Define breakpoints
    const swiperBreakpoints = {
      320: { // Small devices
        slidesPerView: 1,
        spaceBetween: 10,
      },
      768: { // Tablets
        slidesPerView: 2,
        spaceBetween: 20,
      },
      991: { // Tablets
        slidesPerView: 3,
        spaceBetween: 20,
      },
      2048: { // large
        slidesPerView: 4,
        spaceBetween: 30,

      },
    };

    return {
      swiperBreakpoints,
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

    ul li {
      font-size: 1rem;
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