<script setup lang="ts">
import icons from "@/utils/icons";
import type { PropType } from "vue";

const props = defineProps({
  service: {
    type: Object as PropType<{
      title: string;
      img: string;
      description: string;
    }>,
  },
});
</script>
<template>
  <div class="rounded-md bg-white p-6 w-[min(21.75rem,100%)] flex flex-col gap-6" >
    <h3 class="text-lg font-bold" >{{ service?.title }}</h3>
    <div class="realtive rounded-md overflow-hidden" >
      <img class="max-w-full w-full object-cover bg-accent h-[161px]" :src="service?.img" />
    </div>
    <p class="opacity-80">
      {{ service?.description }}
    </p>
    <div class="flex">
      <button class="text-sm flex items-center gap-4 text-primary">
        View All <i v-html="icons.longArrow" />
      </button>
    </div>
  </div>
</template>
