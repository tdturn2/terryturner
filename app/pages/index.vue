<script setup lang="ts">
const services = [
  {
    icon: 'i-lucide-layout-dashboard',
    title: 'Web applications',
    description: 'Full-stack apps from MVP to production — dashboards, SaaS products, and internal tools.'
  },
  {
    icon: 'i-simple-icons-wordpress',
    title: 'WordPress & PHP',
    description: 'Custom themes, plugins, WooCommerce stores, and site maintenance — built to perform and easy to manage.'
  },
  {
    icon: 'i-lucide-plug',
    title: 'APIs & integrations',
    description: 'REST and GraphQL APIs, third-party integrations, webhooks, and data pipelines.'
  },
  {
    icon: 'i-lucide-refresh-cw',
    title: 'Modernization',
    description: 'Legacy refactors, performance tuning, and migrations to current frameworks and cloud.'
  },
  {
    icon: 'i-lucide-handshake',
    title: 'Contract & freelance',
    description: 'Scoped projects or ongoing part-time support. Clear communication, predictable delivery.'
  }
]

const stack = [
  'TypeScript',
  'Vue / Nuxt',
  'React / Next',
  'PHP',
  'WordPress',
  'Node.js',
  'PostgreSQL',
  'AWS / Vercel',
  'Docker',
  'CI/CD'
]
</script>

<template>
  <div>
    <UPageHero
      class="hero-video"
      title="Tailored websites and apps for Central Kentucky"
      description="Custom web solutions built around your business — from WordPress sites and PHP backends to modern web apps. Based in Central KY, working with local teams and clients who want something that fits, not a one-size-fits-all template."
      :ui="{
        container: 'relative z-10',
        title: 'text-white',
        description: 'text-white/85'
      }"
      :links="[
        {
          label: 'Start a project',
          to: '#contact',
          trailingIcon: 'i-lucide-arrow-right',
          size: 'xl',
          color: 'neutral',
          class: 'bg-white text-neutral-900 hover:bg-white/90 ring-0'
        },
        {
          label: 'View services',
          to: '#services',
          size: 'xl',
          color: 'neutral',
          variant: 'outline',
          class: 'bg-transparent text-white ring-white/50 hover:bg-white/10 hover:ring-white/70'
        }
      ]"
    >
      <template #top>
        <video
          class="hero-video__media"
          autoplay
          muted
          loop
          playsinline
          aria-hidden="true"
        >
          <source
            src="/20220924_152848.mp4"
            type="video/mp4"
          >
        </video>
        <div
          class="hero-video__overlay"
          aria-hidden="true"
        />
      </template>
    </UPageHero>

    <UPageSection
      id="services"
      class="section-default"
      title="What I do"
      description="Pragmatic engineering focused on shipping — not over-engineering."
      :features="services"
    />

    <UPageSection
      id="stack"
      class="section-muted"
      title="Tech stack"
      description="Comfortable across PHP, WordPress, the modern JS/TS ecosystem, and common backend tooling."
    >
      <div class="flex flex-wrap justify-center gap-2">
        <UBadge
          v-for="tech in stack"
          :key="tech"
          color="neutral"
          variant="subtle"
          size="lg"
        >
          {{ tech }}
        </UBadge>
      </div>
    </UPageSection>

    <UPageSection
      class="section-accent"
      title="How I work"
      description="Straightforward process, no surprises."
      :features="[
        {
          icon: 'i-lucide-message-square',
          title: 'Discovery call',
          description: 'We align on scope, timeline, and budget before any code is written.'
        },
        {
          icon: 'i-lucide-git-branch',
          title: 'Iterative delivery',
          description: 'Regular check-ins with working increments — not a big reveal at the end.'
        },
        {
          icon: 'i-lucide-receipt',
          title: 'Clear quotes & billing',
          description: 'Custom project quotes with a deposit to start, then invoices on milestones or delivery. Retainers available for ongoing work.'
        },
        {
          icon: 'i-lucide-file-check',
          title: 'Clean handoff',
          description: 'Documented code, deployed infrastructure, and knowledge transfer when we wrap.'
        }
      ]"
    />

    <UPageSection
      id="contact"
      class="section-cta"
    >
      <UPageCTA
        title="Have a project in mind?"
        variant="subtle"
        :links="[
          {
            label: 'hello@terryturner.org',
            to: 'mailto:hello@terryturner.org',
            icon: 'i-lucide-mail',
            size: 'lg'
          }
        ]"
      >
        <template #description>
          <p>
            Send a note with a rough idea of what you need — I'll reply within a day or two.
          </p>
        </template>
      </UPageCTA>
    </UPageSection>
  </div>
</template>
