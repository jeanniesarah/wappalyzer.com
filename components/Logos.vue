<template>
  <div>
    <v-divider />
    <v-container>
      <Testimonials />
    </v-container>

    <v-divider class="mb-12" />

    <v-container class="logos text-center mb-6">
      <p class="overline font-weight-regular">
        Wappalyzer is trusted by thousands of professionals world-wide
      </p>

      <v-row align="center">
        <v-col v-for="(logo, name) in logos" :key="name" cols="3" sm="2" lg="1">
          <component :is="name" class="companies__logo mx-auto" />
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
import Testimonials from '~/components/Testimonials.vue'

import Adobe from '~/assets/images/logos/Adobe.svg?inline'
import Amazon from '~/assets/images/logos/Amazon.svg?inline'
import Ebay from '~/assets/images/logos/Ebay.svg?inline'
import Google from '~/assets/images/logos/Google.svg?inline'
import IBM from '~/assets/images/logos/IBM.svg?inline'
import Microsoft from '~/assets/images/logos/Microsoft.svg?inline'
import Oracle from '~/assets/images/logos/Oracle.svg?inline'
import PayPal from '~/assets/images/logos/PayPal.svg?inline'
import Salesforce from '~/assets/images/logos/Salesforce.svg?inline'
import SAP from '~/assets/images/logos/SAP.svg?inline'
import Shopify from '~/assets/images/logos/Shopify.svg?inline'
import Stripe from '~/assets/images/logos/Stripe.svg?inline'

export default {
  components: {
    Testimonials,
    Google,
    Oracle,
    Amazon,
    IBM,
    PayPal,
    Ebay,
    Shopify,
    Stripe,
    SAP,
    Microsoft,
    Salesforce,
    Adobe,
  },
  data() {
    return {
      logos: {
        Google,
        Oracle,
        Amazon,
        IBM,
        PayPal,
        Ebay,
        Shopify,
        Stripe,
        SAP,
        Microsoft,
        Salesforce,
        Adobe,
      },
    }
  },
}
</script>

<style>
.companies__logo {
  opacity: 0.5;
  width: 100%;
  max-width: 100px;
  height: auto;
}
</style>
