<script setup lang="ts">
const open = ref(false)

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

function closeMenu() {
  open.value = false
}
</script>

<template>
  <UApp>
    <UHeader v-model:open="open">
      <template #left>
        <NuxtLink
          to="/"
          class="font-semibold tracking-tight text-highlighted"
          @click="closeMenu"
        >
          Terry Turner
        </NuxtLink>
      </template>

      <UNavigationMenu
        :items="nav"
        class="hidden lg:flex"
      />

      <template #right>
        <UButton
          to="#contact"
          label="Get in touch"
          size="sm"
          class="hidden sm:inline-flex"
          @click="closeMenu"
        />
      </template>

      <template #body>
        <UNavigationMenu
          :items="nav"
          orientation="vertical"
          class="-mx-2.5"
          @click="closeMenu"
        />

        <UButton
          to="#contact"
          label="Get in touch"
          block
          class="mt-6"
          @click="closeMenu"
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
