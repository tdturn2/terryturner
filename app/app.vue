<script setup lang="ts">
const nav = [
  { label: 'Services', to: '#services' },
  { label: 'Stack', to: '#stack' },
  { label: 'Contact', to: '#contact' }
]

useHead({
  meta: [
    { name: 'viewport', content: 'width=device-width, initial-scale=1' }
  ],
  link: [
    { rel: 'icon', href: '/favicon.ico' }
  ],
  htmlAttrs: {
    lang: 'en'
  }
})

const title = 'Terry Turner — Custom Websites & Apps in Central Kentucky'
const description = 'Freelance developer providing tailored website and app solutions in Central KY — WordPress, PHP, and modern web applications built for your business.'

useSeoMeta({
  title,
  description,
  ogTitle: title,
  ogDescription: description,
  ogUrl: 'https://terryturner.org',
  twitterCard: 'summary_large_image'
})
</script>

<template>
  <UApp>
    <UHeader>
      <template #left>
        <NuxtLink
          to="/"
          class="font-semibold tracking-tight text-highlighted"
        >
          Terry Turner
        </NuxtLink>

        <nav class="hidden sm:flex items-center gap-1 ms-4">
          <UButton
            v-for="item in nav"
            :key="item.to"
            :to="item.to"
            :label="item.label"
            color="neutral"
            variant="ghost"
            size="sm"
          />
        </nav>
      </template>

      <template #right>
        <UButton
          to="#contact"
          label="Get in touch"
          size="sm"
        />
      </template>
    </UHeader>

    <UMain>
      <NuxtPage />
    </UMain>

    <UFooter>
      <template #left>
        <p class="text-sm text-muted">
          © {{ new Date().getFullYear() }} Terry Turner
        </p>
      </template>

      <template #right>
        <UButton
          to="mailto:tdturn2@gmail.com"
          icon="i-lucide-mail"
          aria-label="Email"
          color="neutral"
          variant="ghost"
        />
        <UButton
          to="https://github.com/tdturn2"
          target="_blank"
          icon="i-simple-icons-github"
          aria-label="GitHub"
          color="neutral"
          variant="ghost"
        />
      </template>
    </UFooter>
  </UApp>
</template>
