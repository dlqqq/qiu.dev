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
      <a v-if="profile.link" :href="profile.link">
        <b>{{ profile.name }}</b>
      </a>
      <span v-else>
        {{ profile.name }}: {{ profile.desc }}
      </span>
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
        desc: 'david [at] qiu.dev'
      },
      {
        name: 'linkedin',
        icon: 'mdi-linkedin',
        link: 'https://www.linkedin.com/in/senpie/'
      },
      {
        name: 'stack overflow',
        icon: 'mdi-stack-overflow',
        link: 'https://stackoverflow.com/users/12548458/qiu'
      },
      {
        name: 'stack exchange',
        icon: 'mdi-stack-exchange',
        link: 'https://stackexchange.com/users/10699787/qiu'
      }
    ]
    return { age, profiles }
  }
})
</script>
