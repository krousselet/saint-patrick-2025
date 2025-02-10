<template>
    <div class="images-container">
      <div class="skull-darts-71-container image-container">
        <a href="https://www.facebook.com/p/Skull-Darts-71-100091328505582/" target="_blank">
          <img :src="skullDartsLogoSrc" alt="logo de skull darts 71" />
        </a>
      </div>
      <div class="valkyrie-container image-container">
        <img :src="valkyrieLogoSrc" alt="logo du groupe valkyrie" />
      </div>
        <div class="4-squared-circles-container image-container">
          <a href="https://www.facebook.com/4.Squared.Circles/" target="_blank">
            <img :src="fourSquaredCirclesLogoSrc" alt="logo du groupe four squared circles" />
          </a>
      </div>
      <div class="boddah-container">
         <a
      href="https://www.facebook.com/share/14pQEdHoAH/"
      target="_blank"
          >
             <img :src="boddahLogoSrc" alt="logo du groupe boddah" />
          </a>
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
import skullDartsLogoMobileSrc from "../assets/images/logos/logos-mobile/skull-darts-71-definitif-weigh-0-mobile.svg"
import skullDartsLogoDesktopSrc from "../assets/images/logos/logos-desktop/skull-darts-71-definitif-weigh-0-desktop.svg"

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
    const skullDartsLogoSrc = computed(() =>
      isDesktop.value ? skullDartsLogoDesktopSrc : skullDartsLogoMobileSrc
    );

    return {
      isDesktop,
      fourSquaredCirclesLogoSrc,
      boddahLogoSrc,
      valkyrieLogoSrc,
      skullDartsLogoSrc
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

@media (min-width: 991px) {
  .images-container {
  max-height: 105px;

  img {
    max-height: 230px;
    max-width: 230px;
  }
  }
}

</style>