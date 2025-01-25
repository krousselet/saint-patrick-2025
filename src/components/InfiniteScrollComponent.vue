<template>
    <footer>
        <div class="images-container">
            <div class="4-squared-circles-container">
                <a href="https://www.facebook.com/4.Squared.Circles/" target="_blank">
                    <img :src="fourSquaredCirclesMobileSrc" alt="logo du groupe four squared circles">
                </a>
            </div>
            <div class="boddah-container">
                <a href="https://www.facebook.com/p/Boddah-Quest-tribute-Nirvana-100078758354425/" target="_blank">
                    <img :src="boddahLogoMobileSrc" alt="logo du groupe boddah">
                </a>
            </div>
            <div class="valkyrie-container">
                <img :src="valkyrieLogoMobileSrc" alt="logo du groupe valkyrie">
            </div>
        </div>
        <div class="loop-slider" style="--duration:19260ms; --direction:reverse;">
          <div class="inner">
            <div class="tag"><span>#</span> SaintPatrick</div>
            <div class="tag"><span>#</span> Bière</div>
            <div class="tag"><span>#</span> Fléchettes</div>
            <div class="tag"><span>#</span> Amis</div>
            <div class="tag"><span>#</span> Fête</div>
            <!-- duplicated content -->
            <div class="tag"><span>#</span> SaintPatrick</div>
            <div class="tag"><span>#</span> Bière</div>
            <div class="tag"><span>#</span> Fléchettes</div>
            <div class="tag"><span>#</span> Amis</div>
            <div class="tag"><span>#</span> Fête</div>
          </div>
        </div>
    </footer>
</template>

<script>
import fourSquaredCirclesMobileSrc from "../assets/images/logos/logos-mobile/4-squared-circles.png";
import boddahLogoMobileSrc from "../assets/images/logos/logos-mobile/boddah.png";
import valkyrieLogoMobileSrc from "../assets/images/logos/logos-mobile/valkyrie.png";
export default {
  name: 'InfiniteScrollComponent',
  setup() {
    return {
      fourSquaredCirclesMobileSrc,
      boddahLogoMobileSrc,
      valkyrieLogoMobileSrc,
    };
  },
}
</script>

<style lang="scss" scoped>

.loop-slider {
    overflow-x: hidden;
      .inner {
        display: flex;
        width: fit-content;
        animation-name: loop;
        animation-timing-function: linear;
        animation-iteration-count: infinite;
        animation-direction: var(--direction);
        animation-duration: var(--duration);
        overflow-x: hidden;
      }
    }
    
    .tag {
      display: flex;
      font-family: "UnifrakturCook", serif;
      align-items: center;
      gap: 0 0.2rem;
      color: #e2e8f0;
      font-size: 0.9rem;
      background-color: #334155;
      border-radius: 0.4rem;
      padding: 0.7rem 1rem;
      margin-right: 1rem; // Must used margin-right instead of gap for the loop to be smooth
      box-shadow: 
        0 0.1rem 0.2rem rgb(0 0 0 / 20%),
        0 0.1rem 0.5rem rgb(0 0 0 / 30%),
        0 0.2rem 1.5rem rgb(0 0 0 / 40%);
      
      span {
        font-size: 1.2rem;
        color: #64748b;
      }
    }
    
    .fade {
      pointer-events: none;
      background: linear-gradient(90deg, #1e293b, transparent 30%, transparent 70%, #1e293b);
      position: absolute;
      inset: 0;
    }

    @media (min-width:320px) and (max-width:991px) {
        .tag {
            font-size: 1.2rem;
        }
    }
    @media (min-width:992px) and (max-width:2048px) {

        .tag {
        font-size: 1.3rem;
        padding: 0.7rem 1rem;
        margin-right: 8rem; // Must used margin-right instead of gap for the loop to be smooth
        span {
            font-size: 1.8rem;
        }
        }
    }

@media (min-width:2049px) {

.tag {
  font-size: 1.3rem;
  padding: 0.7rem 1rem;
  margin-right: 15rem; // Must used margin-right instead of gap for the loop to be smooth
  span {
    font-size: 2.1rem;
  }
}
}
@keyframes loop {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(-50%);
  }
}
</style>