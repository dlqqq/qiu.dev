<template>
  <div>
    <h1>
      about
    </h1>
    <p>
      hi. i'm david qiu. i'm a {{ age }}-year-old currently looking into web development.
    </p>
    <p>
      i also review music and write sometimes.
    </p>
    <p>
      i don't use social media, but you can stalk me below:
    </p>
    <div v-for="profile in profiles" :key="profile.name">
      <v-icon>{{ profile.icon }}</v-icon>
      {{ profile.name }}: {{ profile.desc }}
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from '@vue/composition-api'

export default defineComponent({
  name: 'about',
  setup () {
    const age = ref(19)
    const profiles = [
      {
        name: 'email',
        icon: 'mdi-email',
        desc: 'david [at] qiu [dot] dev'
      },
      {
        name: 'linkedin',
        icon: 'mdi-linkedin',
        desc: 'https://www.linkedin.com/in/senpie/'
      }
    ]
    return { age, profiles }
  }
})
</script>
