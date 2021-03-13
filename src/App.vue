<template>
  <div
    class="relative flex flex-col w-full transition duration-500 ease-in-out"
    :class="bgColor"
  >
    <div ref="section1" class="relative h-screen">
      <div class=" flex flex-col justify-center w-full h-full text-center">
        <h1 class="text-5xl leading-normal">
          We're Heesh
        </h1>
        <br />
        <h1 class="text-5xl leading-normal font-semibold">
          We help move your <br />
          business forward with <br />
          design, technology & creativity
        </h1>
      </div>
    </div>
    <div
      ref="section2"
      class="relative block m-auto w-full"
      style="height: 300vw"
    >
      <div
        class="sticky top-0 flex justify-between items-center pt-8 pb-8 h-screen"
        style="width:300vw;will-change:transform;transform-style:preserve-3d"
        :style="{ transform: 'translate3d(' + X + 'px ,0px ,0px)' }"
      >
        <div
          id="img1"
          class="bg-contain bg-center bg-no-repeat w-1/5 h-full"
        ></div>
        <div
          id="img2"
          class="bg-contain bg-center bg-no-repeat w-1/5 h-full"
        ></div>
        <div
          id="img3"
          class="bg-contain bg-center bg-no-repeat w-1/5 h-full"
        ></div>
        <div
          id="img4"
          class="bg-contain bg-center bg-no-repeat w-1/5 h-full"
        ></div>
        <div
          id="img5"
          class="bg-contain bg-center bg-no-repeat w-1/5 h-full"
        ></div>
        <div
          id="img7"
          class="bg-contain bg-center bg-no-repeat w-1/5 h-full"
        ></div>
        <div
          id="img8"
          class="bg-contain bg-center bg-no-repeat w-1/5 h-full"
        ></div>
      </div>
    </div>
    <div class="relative h-screen">
      <div class="flex flex-col justify-center w-full h-full text-center">
        <h1 class="text-5xl leading-normal font-semibold">
          We want to build <br />
          excitement around your <br />
          vision and accelerate the <br />
          growth of your business.
        </h1>
      </div>
    </div>
  </div>
</template>

<script>
import { defineComponent, onMounted, ref } from "vue";

export default defineComponent({
  name: "App",

  setup() {
    const X = ref(null);
    const section1 = ref(null);
    const section2 = ref(null);
    const bgColor = ref("");

    function handleScroll() {
      if (window.scrollY >= section1.value.offsetHeight) {
        X.value = -(window.scrollY - section1.value.offsetHeight);
      }
      if (X.value <= -(section2.value.offsetHeight - window.innerWidth)) {
        X.value = -(section2.value.offsetHeight - window.innerWidth);
      }
      if (window.scrollY < section1.value.offsetHeight) {
        X.value = 0;
      }
    }
    function handleScroll2() {
      if (window.scrollY <= section1.value.offsetHeight) {
        bgColor.value = "bg-white";
      }
      if (window.scrollY >= section1.value.offsetHeight) {
        bgColor.value = "bg-gray-800";
      }
      if (window.scrollY >= section2.value.offsetHeight) {
        bgColor.value = "bg-white";
      }
    }

    onMounted(() => {
      document.addEventListener("scroll", handleScroll);
      document.addEventListener("scroll", handleScroll2);
    });

    return {
      X,
      section1,
      section2,
      bgColor,
      handleScroll,
      handleScroll2,
    };
  },
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
#img1 {
  background-image: url("/images/img1.jpg");
}
#img2 {
  background-image: url("/images/img2.jpg");
}
#img3 {
  background-image: url("/images/img3.jpg");
}
#img4 {
  background-image: url("/images/img4.jpg");
}
#img5 {
  background-image: url("/images/img5.jpg");
}
#img6 {
  background-image: url("/images/img6.jpg");
}
#img7 {
  background-image: url("/images/img7.jpg");
}
#img8 {
  background-image: url("/images/img8.jpg");
}

body {
  overflow-x: hidden;
}
</style>
