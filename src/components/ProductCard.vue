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
  <div class="rounded-md overflow-hidden isolate w-[16.6rem] h-[25.8rem] description-card-grid">
    <div class="relative bg-transparent z-20 logo-area">
      <img
        height="207"
        width="207"
        class="bg-white rounded-full mx-auto"
        :src="product.logo"
      />
    </div>
    <div class="gap-5 z-0 bg-accent flex flex-col items-center justify-center content-area">
      <span class="product-title">{{ product.title }}</span>
      <p class="product-description" >{{ product.description }}</p>
    </div>
  </div>
</template>
<style scoped>
.product-title {
  font-weight: 700;
  font-size: 20px;
  line-height: 26px;
  letter-spacing: 0%;
  text-align: center;
}

.product-description {
  font-size: 16px;
  line-height: 24px;
  letter-spacing: 0%;
  text-align: center;
	text-align: center;
}

.description-card-grid {
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: 6.5rem 6.5rem 12.8rem;
  grid-template-areas:
    "r"
    "r"
    "c";
}

.bg-area {
  grid-row: 2 / span 1;
  background-color: var(--color-accent);
}

.logo-area {
  grid-row: 1 / span 2;
  isolation: isolate;
}

.logo-area::after {
  content: "";
  position: absolute;
  height: 50%;
  left: 0;
  bottom: 0;
  width: 100%;
  background-color: var(--color-accent);
  z-index: -1;
}

.content-area {
  grid-row: 3 / span 1;
}
</style>
