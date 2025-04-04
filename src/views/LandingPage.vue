<script setup lang="ts">
import Button from "@/components/Button.vue";
import Card from "@/components/Card.vue";
import ContactForm from "@/components/ContactForm.vue";
import ProductCard, { type Product } from "@/components/ProductCard.vue";
import TestimonialsCard from "@/components/TestimonialsCard.vue";
import icons from "@/utils/icons";
import Dropdown from "@/components/Dropdown.vue";
import { ref } from "vue";
import product1 from "/src/assets/img/product1.png";
import product5 from "/src/assets/img/product5.png";
import product3 from "/src/assets/img/product3.png";
import product4 from "/src/assets/img/product4.png";
import profile2 from "/src/assets/img/profile2.png";
import profile1 from "/src/assets/img/profile1.png";
import profile3 from "/src/assets/img/profile3.png";
import service1 from "/src/assets/img/service1.png";
import service2 from "/src/assets/img/service2.png";
import service3 from "/src/assets/img/service3.png";
import service4 from "/src/assets/img/service4.png";
import service5 from "/src/assets/img/service5.png";

import Services from "@/components/Services.vue";

interface BestSeller {
  [key: string]: Product[];
}

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

const bestSellers = ref<BestSeller>({
  Soda: [
    {
      title: "Pepsi",
      logo: product1,
      description:
        "Experience the bold and crisp taste of Pepsi, the ultimate soft drink for any occasion. Stop by and grab a chilled Pepsinow!",
    },
    {
      title: "Coca-cola",
      logo: product3,
      description:
        "Enjoy the classic, refreshing taste of Coca-Cola, the perfect soft drink to quench your thirst. Pick up an ice-cold Coketoday!",
    },
    {
      title: "Red Bull",
      logo: product4,
      description:
        "Need an energy boost? Red Bull energy drinks keep you going with a refreshing taste and high-performance.",
    },
    {
      title: "Monster Energy",
      logo: product5,
      description:
        "Unleash the beast with Monster Energy—a powerful blend of flavor, attitude, and energy. Grab a can and fuel your day!",
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
    profile: profile2,
    name: "Bruck Girma",
    job: "CEO - Qwe Store",
    comment:
      "“Terimakasih banyak, kini ruanganku menjadi lebih mewah dan terlihat mahal“",
  },
  {
    profile: profile3,
    name: "Lemma Tsadik",
    job: "General Manager -  Xyz Groceries",
    comment:
      "“Makasih Panto, aku sekarang berasa tinggal di apartment karena barang-barang yang terlihat mewah“",
  },
  {
    profile: profile1,
    name: "Hewan Habtamu",
    job: "Store Manager -  Yiu Groceries",
    comment: "“Sangat terjangkau untuk kantong saya yang tidak terlalu banyak“",
  },
];
const service = [
  {
    title: "Snacks and groceries",
    description:
      "From locally sourced fresh snacks to international treats, we carry a wide variety of chips, chocolates, candies, protein bars, and pantry essentials.",
    img: service1,
  },
  {
    title: "Cigarettes and tobacco products",
    description:
      "We offer a selection of premium cigarettes, cigars, rolling tobacco, and vaping products, ensuring customers have access to their preferred brands.",
    img: service2,
  },
  {
    title: "Lottery tickets",
    description:
      "Try your luck with popular Canadian lottery games such as Lotto 6/49, Lotto Max, and scratch tickets, available daily.",
    img: service3,
  },
  {
    title: "Dairy products",
    description:
      "Fresh milk, yogurt, cheese, and other dairy essentials are stocked to cater to your daily needs.",
    img: service4,
  },
  {
    title: "Beer, liquor, and wine",
    description:
      "We offer a curated selection of local and imported beer, fine wines, and premium spirits for your enjoyment.",
    img: service5,
  },
];
</script>

<template>
  <main class="isolate h-full min-h-full bg-accent">
    <div
      class="z-20 bg-primary font-montserrat flex items-center px-6 md:px-24 justify-between h-[5rem]"
    >
      <RouterLink to="/">
        <span class="col-span-4 font-black text-3xl font-montserrat text-white"
          >INS</span
        >
      </RouterLink>
      <nav class="hidden md:flex relative __nav flex-1 justify-center">
        <ul class="flex items-center gap-9 text-white">
          <li class="text-lg font-bold">
            <RouterLink to="/">Home</RouterLink>
          </li>
          <li class="group relative text-lg font-bold">
            <Dropdown v-slot="{ toggle, setRef }">
              <RouterLink to="/services">
                <p @mouseover="toggle">Services</p>
              </RouterLink>
              <div :ref="setRef">
                <div class="w-[40rem] h-[13.5rem] rounded-md bg-white"></div>
              </div>
            </Dropdown>
          </li>
          <li class="text-lg font-bold">
            <RouterLink to="/Products">Products</RouterLink>
          </li>
          <li class="text-lg font-bold">
            <RouterLink to="/Locations">Locations</RouterLink>
          </li>
          <li class="text-lg font-bold">
            <RouterLink to="/About">About Us</RouterLink>
          </li>
          <li class="text-lg font-bold">
            <RouterLink to="/Contact">Contact</RouterLink>
          </li>
        </ul>
      </nav>
      <Dropdown
        position="right-bottom"
        v-slot="{ toggle, setRef }"
        class="md:hidden flex items-center"
      >
        <button class="cursor-pointer" @click="toggle">
          <i class="text-white *:size-6" v-html="icons.menu" />
        </button>
        <div :ref="setRef">
          <nav
            class="__small-screen-nav relative rounded-lg shadow-xl w-52 bg-white flex-1 justify-center"
          >
            <ul class="flex p-4 flex-col items-center gap-1">
              <li class="flex items-center text-left w-full px-4 text-sm h-10">
                <RouterLink class="flex-1" to="/">Home</RouterLink>
              </li>
              <li
                class="group relative flex items-center text-left w-full px-4 text-sm h-10"
              >
                <RouterLink class="flex-1" to="/services">
                  Services
                </RouterLink>
              </li>
              <li class="flex items-center text-left w-full px-4 text-sm h-10">
                <RouterLink class="flex-1" to="/Products">Products</RouterLink>
              </li>
              <li class="flex items-center text-left w-full px-4 text-sm h-10">
                <RouterLink class="flex-1" to="/Locations"
                  >Locations</RouterLink
                >
              </li>
              <li class="flex items-center text-left w-full px-4 text-sm h-10">
                <RouterLink class="flex-1" to="/About">About Us</RouterLink>
              </li>
              <li class="flex items-center text-left w-full px-4 text-sm h-10">
                <RouterLink class="flex-1" to="/Contact">Contact</RouterLink>
              </li>
            </ul>
            <div class="text-dark/50 text-xs py-1 px-8 flex justify-between">
              &copy;2025<span>License</span><span>Terms</span>
            </div>
          </nav>
        </div>
      </Dropdown>
    </div>
    <section
      role="banner"
      aria-labelledby="hero-section"
      class="z-10 hero-gradient px-6 relative !min-h-[calc(100%-5rem)] isolate text-white grid place-content-center place-items-center gap-[2.125rem]"
    >
      <div
        class="spin spin-1 bg-white/5 !top-[55%] -z-20 border-1 border-white/30 w-[100vw] h-[100vw] md:w-[55vw] md:h-[55vw] rounded-[9999px]"
      ></div>
      <div
        class="spin bg-white/5 !top-[60%] -z-20 border-1 border-white/30 w-[100vw] h-[100vw] md:w-[55vw] md:h-[55vw] rounded-[9999px]"
      ></div>
      <div
        class="spin spin-2 bg-white/5 !left-[55%] !top-[65%] -z-20 border-1 border-white/30 w-[100vw] h-[100vw] md:w-[55vw] md:h-[55vw] rounded-[9999px]"
      ></div>
      <h1 class="hero-head flex flex-col text-[4.5rem]">
        <span>INS Market,</span>
        <span>your ultimate destination</span>
        <span>for convenience.</span>
      </h1>
      <p class="flex flex-col hero-text">
        <span
          >At INS Market Franchise #5608, we bring the trusted reputation of INS
          Market</span
        >
        <span
          >right to your neighborhood. As part of a fast-growing network with
          over 150</span
        >
        <span
          >locations, we are committed to offering top-quality products and
          services that</span
        >
        <span>stand out in the market.</span>
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
    <div
      role="img"
      class="-mt[5rem] -z-10 hero-gradient isolate relative justify-center pointer-events-none"
    >
      <div
        class="absolute-center absolute -z-20 left-0 top-0 w-[90%] h-[80%] bg-white/60 rounded-2xl"
      ></div>
      <div
        class="absolute -z-10 h-[60%] absolute-center left-0 w-full bg-white"
      ></div>
      <img class="mx-auto -z-20" src="/src/assets//img/groceries.png" />
    </div>
    <section class="*:px-6 py-16 min-h-full flex flex-col gap-5 items-center">
      <div class="flex flex-col items-center gap-2">
        <span class="text-primary text-sm md:text-base">About us</span>
        <p class="font-bold text-[1.5rem] md:text-5xl">Who we are...</p>
      </div>
      <p class="pb-16 md:py-0 flex flex-col text-xs md:text-lg text-center">
        <span>
          We are proud to be a part of INS Market, a leading convenience store
          franchise known for its diverse range of products
        </span>
        <span>
          and excellent customer service. Our goal is to provide a convenient
          and enjoyable shopping experience while offering
        </span>
        <span>
          exclusive and hard-to-find products that you won’t see elsewhere
        </span>
      </p>
      <div
        class="!p-0 *:w-full *:h-full *:object-cover gap-4 md:gap-10 gallery-grid md:mt-16"
      >
        <img class="area-l" src="/src/assets/img/can.png" alt="" />
        <img class="area-r" src="/src/assets/img/office.png" alt="" />
        <img class="area-b" src="/src/assets/img/fruit.png" alt="" />
      </div>
    </section>
    <section class="px-6 py-16 gap-6 grid lg:grid-cols-3 bg-accent">
      <div
        class="lg:p-20 items-center col-span-2 lg:col-span-1 flex flex-col gap-2"
      >
        <h2
          class="text-center lg:text-left w-full font-bold text-base md:text-3xl self-start"
        >
          INS Products and Services
        </h2>
        <p
          class="text-sm md:text-base px-6 md:px-20 lg:p-0 text-center lg:text-left"
        >
          We are committed to bringing our customers high-quality products at
          competitive prices, ensuring satisfaction with every visit.
        </p>
      </div>
      <div class="col-span-2 flex flex-wrap justify-center gap-6">
        <Services
          class="w-full min-[765px]:w-[21.5rem]"
          :key="ser.title"
          v-for="ser in service"
          :service="ser"
        />
      </div>
    </section>
    <div class="min-h-full flex flex-col gap-12 md:gap-32 bg-accent">
      <section
        class="gap-7 py-16 min-h-full flex flex-col items-center justify-center bg-white"
      >
        <div class="flex flex-col items-center gap-4">
          <h2 class="text-primary font-bold text-base md:text-[2.625rem]">
            Our Best Selling Product
          </h2>
          <p
            class="px-6 text-xs md:text-base text-center flex items-center flex-col"
          >
            <span>
              we take pride in offering high-demand products that our customers
              love. Here are some of our best-selling items:
            </span>
          </p>
        </div>
        <div class="products-wrapper bg-accent rounded-full">
          <div class="text-xs md:text-base flex md:h-12 rounded-full p-1.5">
            <button
              @click="(el) => {
                const target = el.target as HTMLButtonElement
                target.closest('.products-wrapper')?.style.setProperty('--position-left', `${target.offsetLeft}px`)
                target.closest('.products-wrapper')?.style.setProperty('--indicator-width', `${target.getBoundingClientRect().width}px`)
                target.closest('.products-wrapper')?.style.setProperty('--indicator-height', `${target.getBoundingClientRect().height}px`)
              }"
              class="px-2 md:px-4 py-1 grid place-items-center"
              :key="product"
              v-for="(product, idx) in Object.keys(bestSellers)"
            >
              {{ product }}
            </button>
          </div>
          <div class="products-indicator"></div>
        </div>
        <div class="px-6 gap-8 grid md:grid-cols-[3.5rem_1fr_3.5rem]">
          <div class="hidden md:block"></div>
          <div
            class="grid grid-cols-2 grid-rows-2 md:grid-cols-4 md:grid-rows-1 w-full gap-7"
          >
            <ProductCard
              :product="product"
              :key="product.title"
              v-for="product in bestSellers[activeProduct]"
            />
          </div>
          <div class="hidden md:block"></div>
        </div>
        <div class="flex justify-center">
          <button class="flex items-center gap-4 text-primary">
            View All <i v-html="icons.longArrow" />
          </button>
        </div>
      </section>
      <section
        class="gap-4 bg-accent place-items-center lg:bg-white lg:py-16 min-h-full grid lg:grid-cols-[48.3rem_1fr]"
      >
        <div
          class="max-w-[30rem] lg:max-w-[100%] rounded-md bg-white lg:bg-transparent p-4 lg:px-0 food-grid h-[18.75rem] lg:h-auto grid-rows-2 my-auto grid lg:grid-rows-[14.3rem_19.8rem] gap-4 lg:gap-10 md:grid-cols-[13.9rem_1fr]"
        >
          <img class="area-top" src="/src/assets/img/food1.png" />
          <img class="area-left my-auto" src="/src/assets/img/food3.png" />
          <img class="area-bottom" src="/src/assets/img/food2.png" />
        </div>
        <div class="px-4 flex flex-col justify-center md:mx-auto gap-5">
          <span class="text-base lg:text-4xl">INS Food</span>
          <p class="flex flex-col max-w-[65ch] text-sm lg:text-lg leading-8 line-clamp-6">
            INS Food is your ultimate destination for healthy, halal meals on the go. Made with the finest ingredients, our selection of wraps, pitas, burritos, meal boxes, smoothies, and more is perfect for customers seeking nutritious, quick, and delicious options. Whether you’re in a rush or enjoying a break, INS Food has you covered with fresh, satisfying meals.
          </p>
          <button
            class="text-xs lg:text-base flex items-center gap-4 text-primary"
          >
            More info <i v-html="icons.longArrow" />
          </button>
        </div>
      </section>
      <section
        class="product-desctiption-grid gap-4 bg-accent place-items-center lg:bg-white lg:py-16 min-h-full grid"
      >
        <div
          class="px-4 product-top-area flex flex-col justify-center md:mx-auto gap-5"
        >
          <span class="text-base lg:text-4xl">INS Vape</span>
          <p class="flex flex-col max-w-[65ch] line-clamp-6 text-sm lg:text-lg leading-8">
            INS Vape is a top retailer in the vaping industry in Canada, offering a vast selection of high-quality e-cigarettes, vaporizers, and vape accessories. Whether you’re looking for premium vape juice, disposable vapes, or vaping essentials, we provide the best products at competitive prices. Visit us today to explore our wide range of vapor productsand find everything you need for the ultimate vaping experience in Canada.
          </p>
          <button
            class="text-xs lg:text-base flex items-center gap-4 text-primary"
          >
            More info <i v-html="icons.longArrow" />
          </button>
        </div>
        <div
          class="product-bottom-area max-w-[30rem] lg:max-w-none rounded-md bg-white lg:bg-transparent p-4 lg:px-0 food-grid-right h-[18.75rem] lg:h-auto grid-rows-2 my-auto grid lg:grid-rows-[14.3rem_19.8rem] gap-4 lg:gap-10 md:grid-cols-[13.9rem_1fr] lg:ml-auto"
        >
          <img class="area-top" src="/src/assets/img/home1.png" />
          <img class="area-left my-auto" src="/src/assets/img/home2.png" />
          <img class="area-bottom" src="/src/assets/img/home3.png" />
        </div>
      </section>
      <section
        class="gap-4 bg-accent place-items-center lg:bg-white lg:py-16 min-h-full grid lg:grid-cols-[48.3rem_1fr]"
      >
        <div
          class="max-w-[30rem] lg:max-w-[100%] rounded-md bg-white lg:bg-transparent p-4 lg:px-0 food-grid h-[18.75rem] lg:h-auto grid-rows-2 my-auto grid lg:grid-rows-[14.3rem_19.8rem] gap-4 lg:gap-10 md:grid-cols-[13.9rem_1fr]"
        >
          <img class="area-top" src="/src/assets/img/gro1.png" />
          <img class="area-left my-auto" src="/src/assets/img/gro2.png" />
          <img class="area-bottom" src="/src/assets/img/gro3.png" />
        </div>
        <div class="lg:px-4 flex flex-col justify-center md:mx-auto gap-5">
          <span class="text-base lg:text-4xl">Other Items</span>
          <p class="flex flex-col line-clamp-4 text-sm lg:text-lg leading-8">
            <span>Lorem ipsum dolor sit amet consectetur. Morbi morbi</span>
            <span>est nibh arcu enim urna gravida Vel scelerisque a</span>
            <span
              >ante ullamcorper. Ultrices felis et elit blandit viverra</span
            >
            <span>eget. Donec neque montes non tempor at quis.</span>
          </p>
          <button
            class="text-xs lg:text-base flex items-center gap-4 text-primary"
          >
            More info <i v-html="icons.longArrow" />
          </button>
        </div>
      </section>
      <section class="flex gap-4 items-stretch min-h-full bg-accent">
        <div class="hidden lg:flex flex-1 justify-center items-center">
          <img
            class="my-auto shadow-2xl rounded-xl"
            width="655"
            loading="lazy"
            src="/src/assets/img/map.png"
          />
        </div>
        <div class="bg-white py-16 flex-1 grid place-items-center h-full">
          <div
            class="bg-dark text-white flex flex-col gap-2 lg:gap-6 max-w-[33rem] min-h-full p-6 rounded-md"
          >
            <span class="text-base lg:text-4xl">Location</span>
            <p class="text-xs lg:text-base">
              Makasih Panto, aku sekarang berasa tinggal di apartment karena
              barang-barang yang terlihat mewah“
            </p>
            <div
              class="h-12 lg:h-16 flex rounded-sm gap-6 px-4 py-2 bg-[rgb(56_56_56)]"
              :key="location.title"
              v-for="(location, idx) in loactions"
            >
              <div class="text-sm lg:text-base">
                {{ idx + 1 }}
              </div>
              <div class="flex flex-col">
                <span class="text-sm lg:text-lg">{{ location.title }}</span>
                <span class="text-xs lg:text-sm">{{ location.address }}</span>
              </div>
            </div>
          </div>
        </div>
      </section>
      <section
        class="bg-white py-16 min-h-full flex-col gap-16 items-center justify-center flex"
      >
        <div class="flex flex-col items-center gap-5">
          <span class="text-primary gap-6 text-xs md:text-sm flex items-center">
            Testimonials
            <i v-html="icons.longArrow" />
          </span>
          <h2 class="text-base md:text-4xl">Our Client Reviews</h2>
        </div>
        <div
          class="max-w-full px-6 overflow-x-auto flex items-center gap-[4.5rem]"
        >
          <TestimonialsCard
            :key="testimonial.name"
            v-for="testimonial in testimonials"
            :testimonial="testimonial"
          />
        </div>
      </section>
    </div>
    <section>
      <div
        class="hidden lg:block relative h-[25.0625rem] overflow-hidden w-full"
      >
        <img src="/src/assets/img/photo.jpeg" class="w-full object-cover" />
        <div
          class="absolute bottom-0 left-0 h-20 flex items-center justify-center font-extrabold text-3xl text-white backdrop-blur-sm w-full"
        >
          Contact Us
        </div>
      </div>
      <div
        class="bg-white flex flex-col md:flex-row gap-6 md:gap-32 px-6 lg:py-20 justify-center"
      >
        <div class="flex flex-col md:flex-col gap-7">
          <div class="max-w-[22.8rem] flex flex-col gap-5">
            <span class="font-bold text-lg md:text-4xl"
              >Let's talk with us</span
            >
            <p class="text-sm md:text-base">
              Questions, comments, or suggestions? Simply fill in the form and
              we’ll be in touch shortly.
            </p>
          </div>
          <div class="flex flex-col gap-3.5 max-w-full">
            <div class="text-sm md:text-lg flex flex-wrap gap-4">
              <div class="w-5">
                <i class="text-primary" v-html="icons.location" />
              </div>
              <p class="flex-1">
                1055 Arthur ave Elk Groot, 67.<br />
                New Palmas South Carolina.
              </p>
            </div>
            <div class="flex flex-wrap gap-4">
              <div class="w-5">
                <i class="text-primary" v-html="icons.phone" />
              </div>
              <p class="flex-1">+1 234 678 9108 99</p>
            </div>
            <div class="flex flex-wrap gap-4">
              <div class="w-5 grid place-items-center">
                <i class="text-primary" v-html="icons.mail" />
              </div>
              <p class="flex-1 flex items-center">Contact@ins.com</p>
            </div>
          </div>
        </div>
        <ContactForm />
      </div>
    </section>
    <footer
      class="bg-primary gap-5 p-6 py-12 lg:p-24 flex flex-col justify-center"
    >
      <span class="col-span-4 font-black text-3xl font-montserrat text-white"
        >INS</span
      >
      <section class="text-white grid md:grid-cols-4 gap-6 md:gap-32">
        <div class="flex flex-col gap-5 pb-6 md:pb-0 border-b md:border-b-0">
          <p class="leading-[160%] line-clamp-7">
            Terimakasih banyak, kini ruanganku menjadi lebih mewah dan terlihat
            mahal. banyak, kini ruanganku menjadi lebih mewah dan terlihat
            mahal“
          </p>
        </div>
        <div
          class="col-span-2 grid grid-cols-2 justify-between place-content-between"
        >
          <div>
            <ul class="flex flex-col gap-4">
              <li>Grocery Distribution</li>
              <li>Products Delivery</li>
              <li>Consultancy</li>
            </ul>
          </div>
          <div class="flex md:justify-center justify-end">
            <ul class="flex flex-col gap-4">
              <li>Sodas</li>
              <li>Foods</li>
              <li>Snacks</li>
              <li>Appliance</li>
              <li>Others</li>
            </ul>
          </div>
        </div>
        <div>
          <ul class="flex justify-between md:justify-start md:flex-col gap-4">
            <li class="flex items-center gap-2">
              <i v-html="icons.fb" />
              <span>Facebook</span>
            </li>
            <li class="flex items-center gap-2">
              <i v-html="icons.twitter" />
              <span>Twitter</span>
            </li>
            <li class="flex items-center gap-2">
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
  grid-template-columns: repeat(2, 1fr);
  grid-template-areas:
    "l b"
    "r r";
}

@media (width >= 48rem) {
  .gallery-grid {
    display: grid;
    grid-template-columns: repeat(4, 2fr);
    grid-template-rows: 14.5rem 19.5rem;
    grid-template-areas:
      "l r r r"
      "b r r r";
  }
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
  font-size: 30px;
  line-height: 100%;
  letter-spacing: 0%;
  text-align: center;
  text-transform: capitalize;
}

.hero-text {
  font-family: Montserrat;
  font-weight: 400;
  font-size: 13px;
  line-height: 19px;
  letter-spacing: 0%;
  text-align: center;
}

@media (width >= 48rem) {
  .hero-head {
    font-weight: 900;
    font-size: 67px;
    line-height: 80px;
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
}

.__nav .router-link-exact-active {
  text-decoration: underline;
}

.__small-screen-nav .router-link-exact-active {
  color: var(--color-primary);
  font-weight: 700;
  text-decoration: underline;
}

.food-grid {
  grid-template-areas:
    "l t"
    "l b";
}

.food-grid-right {
  grid-template-areas:
    "t l"
    "b l";
}

.area-left {
  grid-area: l;
  height: 100%;
  max-height: 100%;
  max-width: 100%;
  width: 100%;
  object-fit: cover;
}

.area-top {
  grid-area: t;
  max-height: 100%;
  max-width: 100%;
  width: 100%;
  object-fit: cover;
}

.area-bottom {
  grid-area: b;
  max-height: 100%;
  max-width: 100%;
  width: 100%;
  object-fit: cover;
}

.product-desctiption-grid {
  grid-template-columns: 1fr;
  grid-template-areas:
    "t t"
    "b b";
}

.product-top-area {
  grid-area: b;
}

.product-bottom-area {
  grid-area: t;
}

@media (width >= 64rem) {
  .food-grid {
    grid-template-areas:
      "t l"
      "b l";
  }

  .area-left {
    height: auto;
    margin: auto 0;
    height: auto;
    max-height: auto;
    max-width: auto;
    width: auto;
  }

  .product-top-area {
    grid-area: t;
  }

  .product-bottom-area {
    grid-area: b;
  }

  .product-desctiption-grid {
    grid-template-columns: 1fr 48.3rem;
    grid-template-areas: "t b";
  }
}
</style>
