<template>
    <swiper-container
    :breakpoints="swiperBreakpoints"
      slides-per-view="3"
      speed="1500"
      loop="true"
      autoplay="false"
      navigation="true"
      pagination="true"
      css-mode="true"
      space-between="20"
      
    >
    <swiper-slide>
        <h2>Commencement</h2>
        <p>La soirée débute à 19h</p>
    </swiper-slide>
    <swiper-slide>
        <h2>Prix</h2>
        <p>Le prix d'entrée est de x euros</p>
      </swiper-slide>
      <swiper-slide>
        <h2>Déroulement</h2>
        <p>Trois groupes sont programmés :</p>
        <ul>
            <li><a href="https://www.facebook.com/4.Squared.Circles/" target="_blank">4 squared circles</a></li>
            <li><a href="https://www.facebook.com/p/Boddah-Quest-tribute-Nirvana-100078758354425/" target="_blank">Boddah</a></li>
            <li class="font">Valkyrie</li>
        </ul>
      </swiper-slide>
      <swiper-slide>
        <h2>Bonus</h2>
        <p>Un kilt = une boisson offerte</p>
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
      640: { // Medium devices
        slidesPerView: 2,
        spaceBetween: 15,
      },
      768: { // Tablets
        slidesPerView: 3,
        spaceBetween: 20,
      },
    };

    return {
      swiperBreakpoints,
    };
  },
};
  </script>

<style scoped lang="scss">
    a {
        color: lime;
    }

    swiper-container::part(bullet-active) {
      background-color: lime;
    }

    swiper-container::part(bullet) {
      background-color: red;
    }

    swiper-container::part(button-prev), swiper-container::part(button-next) {
      color: lime;
    }
    
</style>