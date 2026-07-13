<script setup lang="ts">
const open = ref(false)

const nav = [
  { label: 'Services', to: '#services' },
  { label: 'Stack', to: '#stack' },
  { label: 'Contact', to: '#contact' }
]

const footerLinks = [
  { label: 'Terms', to: '/terms' },
  { label: 'Privacy', to: '/privacy' },
  { label: 'Refunds', to: '/refunds' }
]

const socials = [
  {
    label: 'Instagram',
    to: 'https://instagram.com/tdturn2',
    icon: 'i-simple-icons-instagram'
  },
  {
    label: 'X',
    to: 'https://x.com/tdturn2',
    icon: 'i-simple-icons-x'
  },
  {
    label: 'Facebook',
    to: 'https://facebook.com/worldturners',
    icon: 'i-simple-icons-facebook'
  },
  {
    label: 'GitHub',
    to: 'https://github.com/tdturn2',
    icon: 'i-simple-icons-github'
  },
  {
    label: 'Email',
    to: 'mailto:hello@terryturner.org',
    icon: 'i-lucide-mail'
  }
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

    <UFooter
      class="border-t border-default bg-muted/40"
      :ui="{
        top: 'border-b border-default',
        container: 'py-6 flex flex-col gap-4 sm:flex-row sm:items-center sm:justify-between'
      }"
    >
      <template #top>
        <UContainer class="grid gap-10 py-10 sm:grid-cols-2 lg:grid-cols-3">
          <div class="space-y-3">
            <p class="font-semibold tracking-tight text-highlighted">
              Terry Turner
            </p>
            <p class="text-sm text-muted max-w-xs leading-relaxed">
              Custom websites and apps for businesses in Central Kentucky.
            </p>
            <p class="text-sm text-muted">
              705 Spears Ln.<br>
              Danville, KY 40422
            </p>
          </div>

          <div class="space-y-3">
            <p class="text-xs font-medium uppercase tracking-wider text-dimmed">
              Pages
            </p>
            <ul class="space-y-2 text-sm">
              <li
                v-for="link in footerLinks"
                :key="link.to"
              >
                <NuxtLink
                  :to="link.to"
                  class="text-muted hover:text-highlighted transition-colors"
                >
                  {{ link.label }}
                </NuxtLink>
              </li>
            </ul>
          </div>

          <div class="space-y-3 sm:col-span-2 lg:col-span-1">
            <p class="text-xs font-medium uppercase tracking-wider text-dimmed">
              Connect
            </p>
            <NuxtLink
              to="mailto:hello@terryturner.org"
              class="inline-block text-sm text-muted hover:text-highlighted transition-colors"
            >
              hello@terryturner.org
            </NuxtLink>
            <div class="flex flex-wrap items-center gap-1 pt-1">
              <UButton
                v-for="social in socials"
                :key="social.label"
                :to="social.to"
                :target="social.to.startsWith('mailto:') ? undefined : '_blank'"
                :icon="social.icon"
                :aria-label="social.label"
                color="neutral"
                variant="ghost"
              />
            </div>
          </div>
        </UContainer>
      </template>

      <template #left>
        <p class="text-sm text-muted">
          © {{ new Date().getFullYear() }} Terry Turner
        </p>
      </template>

      <template #right>
        <p class="text-sm text-muted">
          Built in Danville, KY
        </p>
      </template>
    </UFooter>
  </UApp>
</template>
