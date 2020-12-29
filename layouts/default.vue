<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      clipped
      app
      right
      floating
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar
      clipped-right
      fixed
      app
    >
      <v-toolbar-title id="title" v-text="title" />
      <v-spacer />
      <v-btn
        icon
        @click.stop="drawer = !drawer"
      >
        <v-icon>mdi-menu</v-icon>
      </v-btn>
    </v-app-bar>
    <v-main class="ma-10">
      <v-container>
        <nuxt />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      items: [
        {
          icon: 'mdi-apps',
          title: 'home',
          to: '/'
        },
        {
          icon: 'mdi-information',
          title: 'about',
          to: '/about'
        },
        {
          icon: 'mdi-memory',
          title: 'techstack',
          to: '/techstack'
        }
      ],
      drawer: true,
      title: 'qiu.dev'
    }
  }
}
</script>

<style lang="scss">
#title {
  font-size: 30px;
}
</style>
