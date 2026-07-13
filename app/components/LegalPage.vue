<script setup lang="ts">
const props = defineProps<{
  title: string
  description: string
}>()

useSeoMeta({
  title: `${props.title} — Terry Turner`,
  description: props.description
})
</script>

<template>
  <UContainer class="py-16 sm:py-24 max-w-3xl">
    <UButton
      to="/"
      icon="i-lucide-arrow-left"
      label="Back"
      color="neutral"
      variant="ghost"
      class="-ms-2.5 mb-8"
    />

    <h1 class="text-3xl sm:text-4xl font-bold tracking-tight text-highlighted text-pretty">
      {{ title }}
    </h1>
    <p class="mt-3 text-muted">
      Last updated: July 13, 2026
    </p>

    <div class="mt-10 space-y-8 text-base leading-relaxed text-toned [&_h2]:text-xl [&_h2]:font-semibold [&_h2]:text-highlighted [&_h2]:mt-10 [&_h2]:mb-3 [&_p]:mb-4 [&_ul]:list-disc [&_ul]:ps-5 [&_ul]:space-y-2">
      <slot />
    </div>

    <p class="mt-12 text-sm text-muted">
      Questions?
      <NuxtLink
        to="mailto:hello@terryturner.org"
        class="text-primary"
      >
        hello@terryturner.org
      </NuxtLink>
    </p>
  </UContainer>
</template>
