<template>
  <div>
    <Page :title="title" no-head no-subscribe>
      <h1 class="text-h1 mt-4 mb-8" style="font-size: 3rem !important;">
        {{ title }}
      </h1>

      <v-row class="mb-4">
        <v-col cols="12" lg="8" class="py-0">
          <p class="text-h2 mb-6">
            Discover who's using your software and that of your competitors.
            Instantly find out the technology stack of your competition's
            websites, individually or in bulk. Automate technology lookups and
            real-time analysis with our highly scalable APIs.
          </p>
        </v-col>
      </v-row>

      <v-btn x-large color="primary" @click="signInDialog = true"
        >Sign up for a free account</v-btn
      >

      <v-divider class="mt-12 mb-8" />

      <v-row class="mb-8" justify="center" justify-md="space-between">
        <v-col
          v-for="feature in features"
          :key="feature.text"
          cols="6"
          sm="4"
          md="3"
        >
          <div class="mb-2 d-flex align-center">
            <v-avatar color="secondary" size="48" class="elevation-2">
              <v-icon color="primary" size="32">{{ feature.icon }}</v-icon>
            </v-avatar>
            <div class="body-2 font-weight-medium primary--text ml-4">
              {{ feature.text }}
            </div>
          </div>
        </v-col>
      </v-row>

      <v-divider class="my-4 my-sm-6" />

      <Product name="lookup" />

      <v-divider class="my-4 my-sm-6" />

      <Product name="lists" mirror />

      <v-divider class="my-4 my-sm-6" />

      <Product name="bulk" />

      <v-divider class="my-4 my-sm-6" />

      <Product name="apis" mirror />

      <v-divider class="my-4 my-sm-6" />

      <Product name="alerts" />

      <v-divider class="my-4 my-sm-6" />

      <Product name="download" mirror />

      <template v-slot:footer>
        <Logos />
      </template>
    </Page>

    <v-dialog v-model="signInDialog" max-width="400px">
      <SignIn sign-up />
    </v-dialog>
  </div>
</template>

<script>
import {
  mdiEye,
  mdiClockFast,
  mdiConsoleLine,
  mdiLayers,
  mdiTimerOutline,
  mdiPuzzle,
  mdiFileDownloadOutline,
  mdiFileChart,
} from '@mdi/js'

import Page from '~/components/Page.vue'
import Logos from '~/components/Logos.vue'
import Product from '~/components/Product.vue'
import SignIn from '~/components/SignIn.vue'

export default {
  components: {
    Page,
    Logos,
    Product,
    SignIn,
  },
  data() {
    return {
      title: 'Competitor analysis',
      signInDialog: false,
      features: [
        {
          text: 'Technology stacks',
          icon: mdiLayers,
        },
        {
          text: 'Website monitoring',
          icon: mdiEye,
        },
        {
          text: 'API access',
          icon: mdiConsoleLine,
        },
        {
          text: 'Real-time analysis',
          icon: mdiTimerOutline,
        },
        {
          text: 'Instant results',
          icon: mdiClockFast,
        },
        {
          text: 'Browser extension',
          icon: mdiPuzzle,
        },
        {
          text: 'Custom reports',
          icon: mdiFileChart,
        },
        {
          text: 'Data import & export',
          icon: mdiFileDownloadOutline,
        },
      ],
    }
  },
}
</script>
