<template>
  <nuxt-content :document="page" />
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  async asyncData ({ $content }) {
    const page = await $content('techstack').fetch()

    return {
      page
    }
  }
})
</script>

<style lang="scss">
// remove extra whitespace at lists with >1 element
.nuxt-content ul li:last-of-type p {
  margin-bottom: 0px;
}

.nuxt-content h2 {
  padding-top: 24px;
}
</style>
