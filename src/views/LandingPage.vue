<script setup lang="ts">
import Button from "@/components/Button.vue";
import Card from "@/components/Card.vue";
import { ref } from "vue";

const services = [
  {
    title: "Grocery Distribution",
    description:
      "The advantage of hiring a workspace with us is that givees you comfortable service and all-around facilities.",
  },
  {
    title: "Products Delivery ",
    description:
      "You can get a workspace of the highst quality at an affordable price and still enjoy the facilities that are oly here.",
  },
  {
    title: "Store Opening Consultancies",
    description:
      "We provide many unique work space choices so that you can choose the workspace to your liking.",
  },
];

const bestSellers = ref({
  Soda: [],
  Snacks: [],
  Foods: [],
  Others: [],
});

const activeProduct = ref(Object.keys(bestSellers)[0]);
</script>

<template>
  <main class="h-full min-h-full">
    <nav class="bg-primary h-[5rem]"></nav>
    <section
      role="banner"
      aria-labelledby="hero-section"
      class="relative min-h-[max(40rem,100%)] isolate text-white grid place-content-center place-items-center gap-[2.125rem] hero-gradient"
    >
      <div
        class="spin spin-1 bg-white/5 !top-[55%] -z-20 border-1 border-white/30 w-[55vw] h-[55vw] rounded-[9999px]"
      ></div>
      <div
        class="spin bg-white/5 !top-[60%] -z-20 border-1 border-white/30 w-[55vw] h-[55vw] rounded-[9999px]"
      ></div>
      <div
        class="spin spin-2 bg-white/5 !left-[55%] !top-[65%] -z-20 border-1 border-white/30 w-[55vw] h-[55vw] rounded-[9999px]"
      ></div>
      <div
        class="absolute -z-10 w-2/3 h-[40rem] bg-white/60 rounded-2xl top-[80%] left-1/2 origin-top -translate-x-1/2"
      ></div>
      <h1 class="hero-head flex flex-col text-[4.5rem]">
        <span>fringilla arcu co ultrices</span>
        <span>npharetra fringilla.</span>
      </h1>
      <p class="flex flex-col hero-text">
        <span
          >Lorem ipsum dolor sit amet consectetur. Viverra fringilla arcu
          convallis nisl ultrices</span
        >
        <span
          >sed pharetra fringilla. Lorem ipsum dolor sit amet consectetur.
          Viverra fringilla arcu</span
        >
        <span>convallis nisl ultrices sed pharetra fringilla.</span>
      </p>
      <Button class="group flex items-center gap-2 truncate">
        <div class="btn-border">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 24 24"
            fill="currentColor"
            class="w-0 h-6 transition-all duration-300 ease-out group-hover:w-6"
          >
            <path
              fill-rule="evenodd"
              d="M1.5 4.5a3 3 0 013-3h1.372c.86 0 1.61.586 1.819 1.42l1.105 4.423a1.875 1.875 0 01-.694 1.955l-1.293.97c-.135.101-.164.249-.126.352a11.285 11.285 0 006.697 6.697c.103.038.25.009.352-.126l.97-1.293a1.875 1.875 0 011.955-.694l4.423 1.105c.834.209 1.42.959 1.42 1.82V19.5a3 3 0 01-3 3h-2.25C8.552 22.5 1.5 15.448 1.5 6.75V4.5z"
              clip-rule="evenodd"
            />
          </svg>
        </div>
        Call Us Now
      </Button>
    </section>
    <div role="img" class="relative  justify-center pointer-events-none">
      <img
        class="h-[67rem] mx-auto -mt-[20%] -z-20"
        src="/src/assets//img/groceries.png"
      />
    </div>
    <section class="p-16 min-h-full flex flex-col gap-5 items-center">
      <div class="flex flex-col items-center gap-2">
        <span class="text-primary text-base">About us</span>
        <p class="font-bold text-5xl">Who we are...</p>
      </div>
      <p class="flex flex-col text-lg text-center">
        <span>
          Lorem ipsum dolor sit amet consectetur. Morbi morbi est nibh arcu enim
          urna gravida iaculis. Vel scelerisque a ante
        </span>
        <span>
          ullamcorper. Ultrices felis et elit blandit viverra eget. Donec neque
          montes non tempor at quis. Lorem ipsum dolor
        </span>
        <span>
          sit amet consectetur. Morbi morbi est nibh arcu enim urna gravida
          iaculis. Vel scelerisque a ante ullamcorper.
        </span>
        <span>
          Ultrices felis et elit blandit viverra eget. Donec neque montes non
          tempor at quis.
        </span>
      </p>
      <div class="gap-10 gallery-grid mt-16">
        <img class="area-l" src="/src/assets/img/can.png" alt="" />
        <img class="area-r" src="/src/assets/img/office.png" alt="" />
        <img class="area-b" src="/src/assets/img/fruit.png" alt="" />
      </div>
    </section>
    <section
      class="bg-accent h-96 gap-16 justify-center services flex items-center gap-"
    >
      <p class="service-header p-12 flex flex-col">
        <span>Here are our </span>
        <span>main services</span>
      </p>
      <div class="justify-center flex items-center gap-7">
        <Card
          :key="service.title"
          v-for="service in services"
          :card="service"
        />
      </div>
    </section>
    <section
      class="gap-7 min-h-full flex flex-col items-center justify-center bg-white"
    >
      <div class="flex flex-col items-center gap-4">
        <h2 class="text-primary font-bold text-[2.625rem]">
          Our Best Selling Product
        </h2>
        <p class="flex items-center justify-center flex-col">
          <span>
            Lorem ipsum dolor sit amet consectetur. Egestas nunc convallis
            viverra mi volutpat viverra commodo. Lorem sem magna
          </span>
          <span> feugiat odio ullamcorper ac volutpat feugiat. </span>
        </p>
      </div>
      <div>
        <div class="products-wrapper flex bg-accent h-12 rounded-full p-1.5">
          <button
            class="px-4 py-1 grid place-items-center"
            :key="product"
            v-for="(product, idx) in Object.keys(bestSellers)"
          >
            {{ product }}
          </button>
        </div>
        <!-- <div class="products-indicator"></div> -->
      </div>
    </section>
  </main>
</template>
<style>
.products-wrapper {
  --position-top: 0%;
  --position-left: 0%;
  --indicator-width: 100%;
    position: relative;
    isolation: isolate;
}

.products-indicator {
  position: absolute;
  top: var(--position-top);
  left: var(--position-left);
  width: var(--indicator-width);
  height: 100%;
  background-color: #fff;
  border-radius: 999px;
  transition: all 0.3s ease-in-out;
  z-index: -1;
}

.gallery-grid {
  display: grid;
  grid-template-columns: repeat(4, 2fr);
  grid-template-rows: 14.5rem 19.5rem;
  grid-template-areas:
    "l r r r"
    "b r r r";
}

.area-l {
  grid-area: l;
}

.area-b {
  grid-area: b;
}

.area-r {
  grid-area: r;
}

@keyframes spin {
  from {
    border-radius: 55vw / 55vw;
    transform: translate(-50%, -50%) rotateZ(0deg);
  }

  50% {
    border-radius: var(--radius);
    transform: translate(-50%, -50%) rotateZ(180deg);
  }

  to {
    border-radius: 55vw / 55vw;
    transform: translate(-50%, -50%) rotateZ(360deg);
  }
}

@keyframes btnwabble {
  from {
    border-radius: 100% / 90%;
    transform: translate(-50%, -50%) rotateZ(0deg);
  }

  50% {
    border-radius: 100% / 70%;
    transform: translate(-50%, -50%) rotateZ(180deg);
  }

  to {
    border-radius: 100% / 90%;
    transform: translate(-50%, -50%) rotateZ(360deg);
  }
}

.service-header {
  font-size: 42px;
  line-height: 100%;
  letter-spacing: 0%;
}

.btn-border {
  position: relative;
  display: grid;
  place-items: center;
}

.btn-border::after {
  content: "";
  transform-origin: center;
  position: absolute;
  top: 50%;
  left: 50%;
  width: 2rem;
  height: 2rem;
  border: 1px;
  border: 1px solid red;
  animation: btnwabble 2s linear infinite;
}

.spin {
  --time: 5s;
  --radius: 55vw / 65vw;
  position: absolute;
  top: 50%;
  left: 50%;
  animation: spin var(--time) linear infinite;
}

.spin-1 {
  --time: 3s;
}

.spin-2 {
  --time: 4s;
}

.hero-gradient {
  background: linear-gradient(90deg, #f85032 0%, #e73827 100%);
}

.hero-head {
  font-weight: 900;
  font-size: 68px;
  line-height: 100%;
  letter-spacing: 0%;
  text-align: center;
  text-transform: capitalize;
}

.hero-text {
  font-family: Montserrat;
  font-weight: 400;
  font-size: 18px;
  line-height: 27px;
  letter-spacing: 0%;
  text-align: center;
}
</style>
