<script setup lang="ts">
import type { PropType } from "vue";

export type Techestimonial = { profile: string, name: string; job: string; comment: string };

const props = defineProps({
  testimonial: {
    type: Object as PropType<Techestimonial>,
    required: true,
  },
});
</script>
<template>
  <div class="rounded-md overflow-hidden isolate min-w-[20.875rem] testimonial-card-grid">
    <div class="relative bg-transparent z-20 logo-area">
      <img
        height="50"
        width="50"
        class="bg-white rounded-full mx-auto"
        :src="testimonial.profile"
      />
    </div>
    <div class="gap-5 z-0 bg-gray-100 rounded-b-3xl flex flex-col items-center justify-center content-area">
			<div class="flex flex-col gap-1.5" >
				<span class="testimonials-title text-xs md:text-lg">{{testimonial.name}}</span>
				<span class="text-xs text-center opacity-60" >{{testimonial.job}}</span>
			</div>
      <p class="text-xs md:text-sm opacity-80 px-10 testimonials-description" >
				{{ testimonial.comment }}
			</p>
    </div>
  </div>
</template>
<style scoped>
.testimonials-title {
	line-height: 100%;
	letter-spacing: 0%;
	text-align: center;
	text-transform: capitalize;
}

.testimonials-description {
  line-height: 24px;
  letter-spacing: 0%;
  text-align: center;
	text-align: center;
}

.testimonial-card-grid {
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: 1.5625rem 1.5625rem 11.3125rem;
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
	border-top-left-radius: 1.5rem;
	border-top-right-radius: 1.5rem;
}

.content-area {
  grid-row: 3 / span 1;
}
</style>
