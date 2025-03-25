<script setup lang="ts">
import icons from "@/utils/icons";
import type { PropType } from "vue";

const props = defineProps({
  card: Object as PropType<{ title: string; description: string }>,
});
</script>
<template>
  <div
    class="w-[17.75rem] h-[17.375rem] p-[34px_26px] rounded-lg bg-white flex flex-col gap-5"
  >
    <p class="title line-clamp-1 text-text-clr/90">{{ card?.title }}</p>
    <p class="description line-clamp-4 text-text-clr/80">
      {{ card?.description }}
    </p>
    <button
      class="cursor-pointer btn-text flex items-center gap-4 text-primary/80"
    >
      More Info <i v-html="icons.longArrow" />
    </button>
  </div>
</template>

<style lang="css" scoped>
.title {
  font-size: 24px;
  line-height: 100%;
  letter-spacing: 0%;
}

.description {
  font-size: 16px;
  line-height: 185%;
  letter-spacing: 0%;
}

.btn-text {
  font-size: 14px;
  line-height: 185%;
  letter-spacing: 0%;
}
</style>
