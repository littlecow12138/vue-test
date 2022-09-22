<template>
  <div class="about">
    <h1>This is an about page</h1>
    <div id="tickLottie" ref="tick"></div>
  </div>
</template>

<script setup>
import tickAnim from "@/assets/tick.json";
import { ref, onMounted } from "vue";
import lottie from "lottie-web";
// eslint-disable-next-line @typescript-eslint/no-unused-vars
let animation = null;

onMounted(() => {
  animation = lottie.loadAnimation({
    container: document.getElementById("tickLottie"),
    renderer: "svg",
    loop: false,
    autoplay: false,
    animationData: tickAnim,
  });

  setInterval(() => {
    // animation.goToAndPlay(0)
  }, 2000);
  // setTimeout(() => {
  //   animation.play()
  // }, 2000);
});
</script>

<style>
@media (min-width: 1024px) {
  h1 {
    color: lightblue;
  }

  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}

#tickLottie {
  width: 8rem;
  height: 4rem;
}
</style>
