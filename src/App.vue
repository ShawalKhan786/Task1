<template>
  <v-app>
    <v-main>
      <HeaderQA/>
      <ToolQA/>
      <FooterQA/>
    </v-main>
  </v-app>
</template>

<script>
import HeaderQA from './components/HeaderQA.vue'
import ToolQA from './components/ToolQA.vue'
import FooterQA from './components/FooterQA.vue'
export default {
  name: 'App',

  components: {
    ToolQA,
    HeaderQA,
    FooterQA,
  },

  data: () => ({
    //
  }),
}
</script>
