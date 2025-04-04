<script setup lang="ts">
import type { PropType } from "vue";

export type Product = { title: string; logo: string; description: string };

const props = defineProps({
  product: {
    type: Object as PropType<Product>,
    required: true,
  },
});
</script>
<template>
  <div class="rounded-md overflow-hidden w-full isolate description-card-grid">
    <div class="bg-area rounded-t-md"></div>
    <div class="relative bg-transparent z-20 logo-area">
      <img class="bg-white rounded-full mx-auto" :src="product.logo" />
    </div>
    <div
      class="gap-2 md:gap-5 z-0 bg-accent flex flex-col items-center justify-center content-area"
    >
      <span class="product-title !text-sm md:!text-[20px]">{{
        product.title
      }}</span>
      <p
        class="product-description line-clamp-4 px-4 leading-none md:!leading-[24px] !text-[11px] md:!text-base"
      >
        {{ product.description }}
      </p>
    </div>
  </div>
</template>
<style scoped>
.product-title {
  font-weight: 700;
  line-height: 26px;
  letter-spacing: 0%;
  text-align: center;
}

.product-description {
  font-size: 16px;
  letter-spacing: 0%;
  text-align: center;
  text-align: center;
}

.description-card-grid {
  max-width: calc(2.3rem * 4);
  display: grid;
  grid-template-columns: repeat(4, max(2.3rem, 1fr));
  grid-template-rows: 2.3rem 2.3rem 7rem;
  grid-template-areas:
    "t l l o"
    "e l l f"
    "b b b b";
}

@media (width >= 48rem) {
  .description-card-grid {
    max-width: calc(4.4rem * 4);
    max-height: calc(4.4rem * 2+12.8rem);
    grid-template-columns: 1fr repeat(2, minmax(1rem, 1fr)) 1fr;
    grid-template-rows: repeat(2, minmax(1rem, 1fr)) 12.8rem;
  }
}

.bg-area {
  grid-row: 2 / span 1;
  grid-column: 1 / span 4;
  background-color: var(--color-accent);
}

.logo-area {
  grid-area: l;
  isolation: isolate;
}

.content-area {
  grid-area: b;
}
</style>
