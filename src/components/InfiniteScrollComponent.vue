<template>
  <div class="loop-slider" style="--duration:19260ms; --direction:reverse;">
    <div class="inner">
      <div v-for="(item, index) in duplicatedItems" :key="index" class="tag font">
        <span>🍀</span> {{ item }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "InfiniteScrollComponent",
  props: {
    items: {
      type: Array,
      required: true,
    },
  },
  computed: {
    duplicatedItems() {
      return [...this.items, ...this.items]; // Duplicate for smooth looping
    },
  },
};
</script>

<style lang="scss">
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
  align-items: center;
  gap: 0 0.2rem;
  color: #e2e8f0;
  font-size: 0.9rem;
  background-color: #334155;
  border-radius: 0.4rem;
  padding: 0.7rem 1rem;
  margin-right: 1rem; // Must use margin-right instead of gap for smooth looping
  box-shadow: 
    0 0.1rem 0.2rem rgb(0 0 0 / 20%),
    0 0.1rem 0.5rem rgb(0 0 0 / 30%),
    0 0.2rem 1.5rem rgb(0 0 0 / 40%);
  
  span {
    font-size: 1.2rem;
    color: #64748b;
  }
}

@media (min-width:992px) and (max-width: 2048px) {
  .tag {
    display: flex;
    justify-content: space-around;
    align-items: center;
    width: 150px;
    height: 40px;
    font-size: 1.5rem;
  }
}

@media (min-width:2049px) {
  .tag {
    display: flex;
    justify-content: space-around;
    align-items: center;
    width: 250px;
    height: 80px;
    font-size: 2rem;
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
