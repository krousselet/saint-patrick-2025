<template>
    <h2 class="block-effect" style="--td: 1.2s">
    <div class="block-reveal" style="--bc: green; --d: .1s">{{ textOne }}</div>
    <div class="block-reveal" style="--bc: lime; --d: .5s">{{textTwo}}</div>
    </h2>
  </template>
  
  <script>
  export default {
    name: 'RevealComponent',
    data() {
      return {
        textOne: "Saint Patrick",
        textTwo: "Evénement"
      }
    }
  }
  </script>
  
  <style scoped lang="scss">

p {
  color: #2e2e2e;
  margin-bottom: 20px;
}


/* block-$ */
.block-effect {
  font-size: calc(8px + 6vw);
}

.block-reveal {
  --t: calc(var(--td) + var(--d));

  color: transparent;
  padding: 4px;

  position: relative;
  overflow: hidden;
  border-radius: 7px;

  animation: revealBlock 0s var(--t) forwards;
}

.block-reveal::after {
  content: '';

  width: 0%;
  height: 100%;
  padding-bottom: 4px;
  border-radius: 7px;

  position: absolute;
  top: 0;
  left: 0;

  background: var(--bc);
  animation: revealingIn var(--td) var(--d) forwards, revealingOut var(--td) var(--t) forwards;
}


/* animations */
@keyframes revealBlock {
  100% {
    color: white;
  }
}

@keyframes revealingIn {

  0% {
    width: 0;
  }

  100% {
    width: 100%;
  }
}

@keyframes revealingOut {

  0% {
    transform: translateX(0);
  }

  100% {
    transform: translateX(100%);
  }

}

  </style>