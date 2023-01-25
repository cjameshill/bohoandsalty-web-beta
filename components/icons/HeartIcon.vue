<script setup>
import { onMounted, ref } from "vue";
import { create } from "@lottiefiles/lottie-interactivity";
import { useVibrate } from "@vueuse/core";
const { vibrate } = useVibrate({ pattern: [200] });

const lottie = ref();
const click = () => {
  console.log("click");
  vibrate();
};
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
    @click="click"
    class="cursor-pointer rounded-full active:bg-slate-100"
    src="https://assets8.lottiefiles.com/packages/lf20_l5g0dsej.json"
    speed="3"
    debug
  />
</template>
