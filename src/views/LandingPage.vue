<script setup lang="ts">
import Button from "@/components/Button.vue";
import Card from "@/components/Card.vue";
import ContactForm from "@/components/ContactForm.vue";
import ProductCard, { type Product } from "@/components/ProductCard.vue";
import TestimonialsCard from "@/components/TestimonialsCard.vue";
import icons from "@/utils/icons";
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

interface BestSeller {
  [key: string]: Product[];
}

const bestSellers = ref<BestSeller>({
  Soda: [
    {
      title: "Pepsi",
      logo: "/src/assets/img/product1.png",
      description:
        "Lorem ipsum dolor sit amet consectetur. Morbi morbi est nibh arcu ",
    },
    {
      title: "Coca-cola",
      logo: "/src/assets/img/product3.png",
      description:
        "Lorem ipsum dolor sit amet consectetur. Morbi morbi est nibh arcu ",
    },
    {
      title: "Red Bull",
      logo: "/src/assets/img/product4.png",
      description:
        "Lorem ipsum dolor sit amet consectetur. Morbi morbi est nibh arcu ",
    },
    {
      title: "Frito Lay",
      logo: "/src/assets/img/product2.png",
      description:
        "Lorem ipsum dolor sit amet consectetur. Morbi morbi est nibh arcu ",
    },
  ],
  Snacks: [],
  Foods: [],
  Others: [],
});

const activeProduct = ref<keyof typeof bestSellers.value>(
  Object.keys(bestSellers.value)[0]
);

const loactions = [
  {
    title: "12 Medium Store",
    address: "Street. 51 100 00 Toronto, Canda",
  },
  {
    title: "Xyz Downtown Store",
    address: "Street. st. Giorge 100 Toronto, Canda",
  },
  {
    title: "Alpha Boutique",
    address: "Avenue. 45 Central Park 200 New York, USA",
  },
  {
    title: "Beta Electronics",
    address: "Boulevard. 23 Tech Plaza 300 San Francisco, USA",
  },
  {
    title: "Gamma Fashion Hub",
    address: "Road. 78 Fashion Street 400 Los Angeles, USA",
  },
  {
    title: "Delta Home Goods",
    address: "Drive. 12 Comfort Lane 500 Chicago, USA",
  },
  {
    title: "Epsilon Pet Supplies",
    address: "Way. 60 Animal Avenue 600 Miami, USA",
  },
  {
    title: "Zeta Bookstore",
    address: "Path. 34 Literacy Lane 700 Seattle, USA",
  },
  {
    title: "Eta Fitness Center",
    address: "Circle. 90 Health Drive 800 Austin, USA",
  },
];

const testimonials = [
  {
    profile: "/src/assets/img/profile2.png",
    name: "Bruck Girma",
    job: "CEO - Qwe Store",
    comment:
      "“Terimakasih banyak, kini ruanganku menjadi lebih mewah dan terlihat mahal“",
  },
  {
    profile: "/src/assets/img/profile3.png",
    name: "Lemma Tsadik",
    job: "General Manager -  Xyz Groceries",
    comment:
      "“Makasih Panto, aku sekarang berasa tinggal di apartment karena barang-barang yang terlihat mewah“",
  },
  {
    profile: "/src/assets/img/profile1.png",
    name: "Hewan Habtamu",
    job: "Store Manager -  Yiu Groceries",
    comment: "“Sangat terjangkau untuk kantong saya yang tidak terlalu banyak“",
  },
];
</script>

<template>
  <main class="h-full min-h-full bg-accent">
    <nav class="bg-primary flex items-center px-24 justify-between h-[5rem]">
      <span class="col-span-4 font-extrabold text-3xl font-host-grotesk text-white">INS</span>
      <nav class="__nav flex-1 flex justify-center" >
        <ul class="flex items-center gap-9 text-white" >
          <li class="text-lg font-bold" >
            <RouterLink to="/" >Home</RouterLink>
          </li>
          <li class="text-lg font-bold" >
            <RouterLink to="/Services" >Services</RouterLink>
          </li>
          <li class="text-lg font-bold" >
            <RouterLink to="/Products" >Products</RouterLink>
          </li>
          <li class="text-lg font-bold" >
            <RouterLink to="/Locations" >Locations</RouterLink>
          </li>
          <li class="text-lg font-bold" >
            <RouterLink to="/About" >About Us</RouterLink>
          </li>
          <li class="text-lg font-bold" >
            <RouterLink to="/Contact" >Contact</RouterLink>
          </li>
        </ul>
      </nav>
    </nav>
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
    <div role="img" class="relative justify-center pointer-events-none">
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
    <div class="min-h-full flex flex-col gap-32 bg-accent">
      <section
        class="gap-7 py-16 min-h-full flex flex-col items-center justify-center bg-white"
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
        <div class="products-wrapper bg-accent rounded-full">
          <div class="flex h-12 rounded-full p-1.5">
            <button
              @click="(el) => {
                const target = el.target as HTMLButtonElement
                target.closest('.products-wrapper')?.style.setProperty('--position-left', `${target.offsetLeft}px`)
                target.closest('.products-wrapper')?.style.setProperty('--indicator-width', `${target.getBoundingClientRect().width}px`)
                target.closest('.products-wrapper')?.style.setProperty('--indicator-height', `${target.getBoundingClientRect().height}px`)
              }"
              class="px-4 py-1 grid place-items-center"
              :key="product"
              v-for="(product, idx) in Object.keys(bestSellers)"
            >
              {{ product }}
            </button>
          </div>
          <div class="products-indicator"></div>
        </div>
        <div class="gap-8 grid grid-cols-[3.5rem_1fr_3.5rem]">
          <div></div>
          <div class="flex gap-7">
            <ProductCard
              :product="product"
              :key="product.title"
              v-for="product in bestSellers[activeProduct]"
            />
          </div>
          <div></div>
        </div>
        <div class="flex justify-center">
          <button class="flex items-center gap-4 text-primary">
            View All <i v-html="icons.longArrow" />
          </button>
        </div>
      </section>
      <section class="bg-white py-16 min-h-full grid grid-cols-[48.3rem_1fr]">
        <div
          class="my-auto grid grid-rows-[14.3rem_19.8rem] gap-10 grid-cols-[13.9rem_1fr]"
        >
          <img src="/src/assets/img/food1.png" />
          <img class="row-span-2 my-auto" src="/src/assets/img/food3.png" />
          <img src="/src/assets/img/food2.png" />
        </div>
        <div class="flex flex-col justify-center mx-auto gap-5">
          <span class="text-4xl">Food</span>
          <p class="flex flex-col line-clamp-4 text-lg leading-8">
            <span>Lorem ipsum dolor sit amet consectetur. Morbi morbi</span>
            <span>est nibh arcu enim urna gravida Vel scelerisque a</span>
            <span
              >ante ullamcorper. Ultrices felis et elit blandit viverra</span
            >
            <span>eget. Donec neque montes non tempor at quis.</span>
          </p>
          <button class="flex items-center gap-4 text-primary">
            More info <i v-html="icons.longArrow" />
          </button>
        </div>
      </section>
      <section class="bg-white py-16 min-h-full grid grid-cols-[48.3rem_1fr]">
        <div class="flex flex-col justify-center mx-auto gap-5">
          <span class="text-4xl">Home appliance</span>
          <p class="flex flex-col line-clamp-4 text-lg leading-8">
            <span>Lorem ipsum dolor sit amet consectetur. Morbi morbi</span>
            <span>est nibh arcu enim urna gravida Vel scelerisque a</span>
            <span
              >ante ullamcorper. Ultrices felis et elit blandit viverra</span
            >
            <span>eget. Donec neque montes non tempor at quis.</span>
          </p>
          <button class="flex items-center gap-4 text-primary">
            More info <i v-html="icons.longArrow" />
          </button>
        </div>
        <div
          class="ml-auto my-auto justify-end grid grid-rows-[14.3rem_19.8rem] gap-10 grid-cols-[13.9rem_1fr]"
        >
          <img src="/src/assets/img/home1.png" />
          <img class="row-span-2 my-auto" src="/src/assets/img/home2.png" />
          <img src="/src/assets/img/home3.png" />
        </div>
      </section>
      <section class="bg-white py-16 min-h-full grid grid-cols-[48.3rem_1fr]">
        <div
          class="my-auto grid grid-rows-[14.3rem_19.8rem] gap-10 grid-cols-[13.9rem_1fr]"
        >
          <img src="/src/assets/img/gro1.png" />
          <img class="row-span-2 my-auto" src="/src/assets/img/gro2.png" />
          <img src="/src/assets/img/gro3.png" />
        </div>
        <div class="flex flex-col justify-center mx-auto gap-5">
          <span class="text-4xl">Groceries</span>
          <p class="flex flex-col line-clamp-4 text-lg leading-8">
            <span>Lorem ipsum dolor sit amet consectetur. Morbi morbi</span>
            <span>est nibh arcu enim urna gravida Vel scelerisque a</span>
            <span
              >ante ullamcorper. Ultrices felis et elit blandit viverra</span
            >
            <span>eget. Donec neque montes non tempor at quis.</span>
          </p>
          <button class="flex items-center gap-4 text-primary">
            More info <i v-html="icons.longArrow" />
          </button>
        </div>
      </section>
      <section class="flex items-stretch min-h-full bg-accent">
        <div class="flex-1 flex justify-center items-center">
          <img
            class="my-auto shadow-2xl rounded-xl"
            width="655"
            loading="lazy"
            src="/src/assets/img/map.png"
          />
        </div>
        <div class="bg-white py-16 flex-1 grid place-items-center h-full">
          <div
            class="bg-dark text-white flex flex-col gap-6 w-[33rem] min-h-full p-6 rounded-md"
          >
            <span class="text-4xl">Location</span>
            <p>
              Makasih Panto, aku sekarang berasa tinggal di apartment karena
              barang-barang yang terlihat mewah“
            </p>
            <div
              class="h-16 flex rounded-sm gap-6 px-4 py-2 bg-[rgb(56_56_56)]"
              :key="location.title"
              v-for="(location, idx) in loactions"
            >
              <div>
                {{ idx + 1 }}
              </div>
              <div class="flex flex-col">
                <span class="text-lg">{{ location.title }}</span>
                <span class="text-sm">{{ location.address }}</span>
              </div>
            </div>
          </div>
        </div>
      </section>
      <section
        class="bg-white py-16 min-h-full flex-col gap-16 items-center justify-center flex"
      >
        <div class="flex flex-col items-center gap-5">
          <span class="text-primary gap-6 text-sm flex items-center">
            Testimonials
            <i v-html="icons.longArrow" />
          </span>
          <h2 class="text-4xl">Our Client Reviews</h2>
        </div>
        <div class="flex items-center gap-[4.5rem]">
          <TestimonialsCard
            :key="testimonial.name"
            v-for="testimonial in testimonials"
            :testimonial="testimonial"
          />
        </div>
      </section>
    </div>
    <section>
      <div class="relative h-[25.0625rem] overflow-hidden w-full">
        <img src="/src/assets/img/photo.jpeg" class="w-full object-cover" />
        <div
          class="absolute bottom-0 left-0 h-20 flex items-center justify-center font-extrabold text-3xl text-white backdrop-blur-sm w-full"
        >
          Contact Us
        </div>
      </div>
      <div class="flex gap-32 py-20 justify-center">
        <div class="flex flex-col gap-7">
          <div class="max-w-[22.8rem] flex flex-col gap-5">
            <span class="font-bold text-4xl">Let's talk with us</span>
            <p>
              Questions, comments, or suggestions? Simply fill in the form and
              we’ll be in touch shortly.
            </p>
          </div>
          <div class="flex flex-col gap-3.5 max-w-full" >
            <div class="flex flex-wrap gap-2.5">
              <div class="w-5" >
                <i class="text-primary" v-html="icons.location" />
              </div>
              <p class="flex-1 text-lg">1055 Arthur ave Elk Groot, 67.<br/> New Palmas South Carolina.</p>
            </div>
            <div class="flex flex-wrap gap-2.5">
              <div class="w-5" >
                <i class="text-primary" v-html="icons.phone" />
              </div>
              <p class="flex-1 text-lg">+1 234 678 9108 99</p>
            </div>
            <div class="flex flex-wrap gap-2.5">
              <div class="w-5 grid place-items-center" >
                <i class="text-primary" v-html="icons.mail" />
              </div>
              <p class="flex-1 flex items-center text-lg">Contact@ins.com</p>
            </div>
          </div>
        </div>
        <ContactForm />
      </div>
    </section>
    <footer class="bg-primary gap-5 p-24 flex flex-col justify-center" >
      <span class="col-span-4 font-extrabold text-3xl font-host-grotesk text-white">INS</span>
      <section class="text-white grid grid-cols-4 gap-32" >
        <div class="flex flex-col gap-5" >
          <p class="leading-[160%]" >
            Terimakasih banyak, kini ruanganku menjadi lebih mewah dan terlihat mahal.  banyak, kini ruanganku menjadi lebih mewah dan terlihat mahal“
          </p>
        </div>
        <div>
          <ul class="flex flex-col gap-4" >
            <li>Grocery Distribution</li>
            <li>Products Delivery </li>
            <li>Consultancy</li>
          </ul>
        </div>
        <div>
          <ul class="flex flex-col gap-4" >
            <li>Sodas</li>
            <li>Foods</li>
            <li>Snacks</li>
            <li>Appliance </li>
            <li>Others</li>
          </ul>
        </div>
        <div>
          <ul class="flex flex-col gap-4" >
            <li class="flex items-center gap-2" >
              <i v-html="icons.fb" />
              <span>Facebook</span>
            </li>
            <li class="flex items-center gap-2" >
              <i v-html="icons.twitter" />
              <span>Twitter</span>
            </li>
            <li class="flex items-center gap-2" >
              <i v-html="icons.insta" />
              <span>Instagram</span>
            </li>
          </ul>
        </div>
      </section>
    </footer>
  </main>
</template>
<style>
.products-wrapper {
  --position-left: 0%;
  --indicator-width: 0%;
  --indicator-width: 0%;
  position: relative;
  isolation: isolate;
}

.products-indicator {
  position: absolute;
  top: 6px;
  left: var(--position-left);
  width: var(--indicator-width);
  height: var(--indicator-height);
  background-color: #fff;
  border-radius: 15px;
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

.__nav .router-link-exact-active {
  text-decoration: underline;
}
</style>
