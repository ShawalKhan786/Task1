<template>
  <v-app>
    <v-main>
      <ToolQA/>
    </v-main>
  </v-app>
</template>

<script>
import ToolQA from './components/ToolQA.vue'

export default {
  name: 'App',

  components: {
    ToolQA,
  },

  data: () => ({
    //
  }),
}
</script>
