<template>
  <v-app dark>
    <v-content>
      <Header />
      <v-container>
        <nuxt />
      </v-container>
    </v-content>

    <v-footer
      :fixed="fixed"
      app
    >
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
import Header from '@/components/Header'

export default {
  components: {
    Header
  },
  data () {
    return {

    }
  }
}
</script>
