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
      class="hero-surface"
      title="Tailored websites and apps for Central Kentucky"
      description="Custom web solutions built around your business — from WordPress sites and PHP backends to modern web apps. Based in Central KY, working with local teams and clients who want something that fits, not a one-size-fits-all template."
      :links="[
        {
          label: 'Start a project',
          to: '#contact',
          trailingIcon: 'i-lucide-arrow-right',
          size: 'xl'
        },
        {
          label: 'View services',
          to: '#services',
          size: 'xl',
          color: 'neutral',
          variant: 'subtle'
        }
      ]"
    >
      <template #headline>

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
        description="Send a note with a rough idea of what you need — I'll reply within a day or two."
        variant="subtle"
        :links="[
          {
            label: 'tdturn2@gmail.com',
            to: 'mailto:tdturn2@gmail.com',
            icon: 'i-lucide-mail',
            size: 'lg'
          }
        ]"
      />
    </UPageSection>
  </div>
</template>
