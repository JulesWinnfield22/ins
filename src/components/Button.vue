<script setup lang="ts">
import { PropType } from "vue";

const props = defineProps({
  pending: {
    type: Boolean,
    default: false,
  },
  size: {
    type: String,
    default: "sm",
  },
  type: {
    type: String as PropType<"primary" | "secondary" | "edge">,
    default: "secondary",
  },
});
</script>
<template>
  <button :class="[$style?.[size], $style?.[type]]" class="btn">
    <slot v-if="!pending"></slot>
  </button>
  <!-- <i class="m-auto" v-else v-html="icons.spinner" /> -->
</template>
<style module>
.xs {
  min-width: auto;
  height: auto;
}

.sm {
  min-width: 14.5rem;
  height: 3.875rem;
}

.md {
  min-width: 6.8rem;
  min-height: 2rem;
}

.lg {
  min-width: 6.8rem;
  min-height: 2rem;
}

.secondary {
  font-weight: 700;
  font-size: 1.5rem;
  line-height: 100%;
  letter-spacing: 0%;
  color: var(--color-primary);
  background-color: white;
}

.primary {
  @apply bg-primary text-white;
}
</style>
<style>
.btn {
  gap: 10px;
  border-radius: 4px;
  padding-top: 16px;
  padding-right: 46px;
  padding-bottom: 16px;
  padding-left: 46px;
  cursor: pointer;
}
</style>
