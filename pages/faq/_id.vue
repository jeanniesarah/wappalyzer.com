<!-- eslint-disable vue/no-v-html -->
<template>
  <div>
    <Page
      :title="title"
      :side="side"
      :crumbs="[{ title: 'FAQs', to: '/faq/lists/' }]"
      seo-title="Frequently asked questions"
      no-head
    >
      <h1 class="mb-4">Frequently asked questions</h1>

      <Faqs :topic="$route.params.id" />
    </Page>
  </div>
</template>

<script>
import Page from '~/components/Page.vue'
import Faqs from '~/components/Faqs.vue'

const faqs = {
  lists: {
    title: 'Lead lists',
    icon: 'mdiFilterVariant',
    to: '/faq/lists/',
  },
  api: {
    title: 'APIs',
    icon: 'mdiConsole',
    to: '/faq/api/',
  },
  credits: {
    title: 'Credits',
    icon: 'mdiAlphaCCircle',
    to: '/faq/credits/',
  },
  extension: {
    title: 'Browser extension',
    icon: 'mdiPuzzle',
    to: '/faq/extension/',
  },
}

export default {
  components: {
    Page,
    Faqs,
  },
  data() {
    return {
      title: faqs[this.$route.params.id].title,

      side: Object.values(faqs).map(({ title, icon, to }) => ({
        title,
        icon,
        to,
      })),
    }
  },
  created() {
    if (!faqs[this.$route.params.id]) {
      return this.$nuxt.error({ statusCode: 404, message: 'Page not found' })
    }
  },
  methods: {
    slugify(string) {
      return string
        .toLowerCase()
        .replace(/[^a-z0-9]/g, '-')
        .replace(/--+/, '-')
        .replace(/(^-|-$)/, '')
    },
  },
}
</script>

<style>
h3 .faq__anchor {
  visibility: hidden;
}

h3:hover .faq__anchor {
  visibility: visible;
}

.faq__anchor {
  text-decoration: none;
}
</style>
