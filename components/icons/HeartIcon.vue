<script setup>
import { onMounted, ref } from "vue";
import { create } from "@lottiefiles/lottie-interactivity";
const lottie = ref();
onMounted(() => {
  lottie.value.addEventListener("load", function () {
    create({
      player: "#toggleLottie",
      mode: "cursor",
      actions: [
        {
          type: "toggle",
        },
      ],
    });
  });
});
</script>
<template>
  <lottie-player
    id="toggleLottie"
    ref="lottie"
    style="width: 50px"
    class="cursor-pointer"
    src="https://assets8.lottiefiles.com/packages/lf20_l5g0dsej.json"
    speed="3"
    debug
  />
</template>
