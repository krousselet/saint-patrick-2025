<template>
    <div class="images-container">
        <div class="4-squared-circles-container">
          <a href="https://www.facebook.com/4.Squared.Circles/" target="_blank">
            <img :src="fourSquaredCirclesLogoSrc" alt="logo du groupe four squared circles" />
          </a>
      </div>
      <div class="boddah-container">
         <a
      href="https://www.facebook.com/p/Boddah-Quest-tribute-Nirvana-100078758354425/"
      target="_blank"
          >
             <img :src="boddahLogoSrc" alt="logo du groupe boddah" />
          </a>
      </div>
      <div class="valkyrie-container">
    <img :src="valkyrieLogoSrc" alt="logo du groupe valkyrie" />
  </div>
</div>
</template>

<script>
import { ref, computed, onMounted, onUnmounted } from "vue";
import fourSquaredCirclesMobileSrc from "../assets/images/logos/logos-mobile/4-squared-circles.png";
import fourSquaredCirclesDesktopSrc from "../assets/images/logos/logos-desktop/4-squared-circles.png";
import boddahLogoMobileSrc from "../assets/images/logos/logos-mobile/boddah.png";
import boddahLogoDesktopSrc from "../assets/images/logos/logos-desktop/boddah.png";
import valkyrieLogoMobileSrc from "../assets/images/logos/logos-mobile/valkyrie.png";
import valkyrieLogoDesktopSrc from "../assets/images/logos/logos-desktop/valkyrie.png";

export default {
  name: "GroupsComponent",
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

    const fourSquaredCirclesLogoSrc = computed(() =>
      isDesktop.value ? fourSquaredCirclesDesktopSrc : fourSquaredCirclesMobileSrc
    );
    const boddahLogoSrc = computed(() =>
      isDesktop.value ? boddahLogoDesktopSrc : boddahLogoMobileSrc
    );
    const valkyrieLogoSrc = computed(() =>
      isDesktop.value ? valkyrieLogoDesktopSrc : valkyrieLogoMobileSrc
    );

    return {
      isDesktop,
      fourSquaredCirclesLogoSrc,
      boddahLogoSrc,
      valkyrieLogoSrc,
    };
  },
};
</script>

<style lang="scss" scoped>

.images-container {
  display: flex;
  justify-content: space-around;
  margin: 75px auto;

  img {
    height: 100%;
    width: 100%;
  }
}

</style>