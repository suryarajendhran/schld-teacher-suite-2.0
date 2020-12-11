<template>
  <v-app>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant.sync="mini"
      :permanent="!is_mobile"
      app
    >
      <v-list-item style="height: 64px" class="px-2">
        <v-list-item-avatar>
          <!-- TODO: Change to our logo -->
          <v-img src="https://randomuser.me/api/portraits/men/85.jpg"></v-img>
        </v-list-item-avatar>

        <v-list-item-title>Scholared</v-list-item-title>

        <v-btn v-if="!is_mobile" icon @click.stop="mini = !mini">
          <v-icon>mdi-chevron-left</v-icon>
        </v-btn>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense nav>
        <v-list-item
          v-for="item in items"
          :key="item.title"
          :to="item.to"
          router
          link
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar elevate-on-scroll app>
      <v-app-bar-nav-icon
        v-if="is_mobile"
        @click.stop="drawer = !drawer"
      ></v-app-bar-nav-icon>
      <v-spacer></v-spacer>
      <v-btn class="mr-1" icon><v-icon>mdi-bell</v-icon></v-btn>
      <v-btn class="mr-1" text>Go to docs</v-btn>
      <v-btn class="ml-1" icon><v-icon>mdi-account</v-icon></v-btn>
    </v-app-bar>
    <v-main>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  data() {
    var is_mobile = false
    if (window.innerHeight < 800 || window.innerWidth < 400) {
      is_mobile = true
    }
    return {
      is_mobile,
      drawer: !is_mobile,
      mini: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Dashboard',
          to: '/',
        },
        {
          icon: 'mdi-face',
          title: 'Students',
          to: '/student',
        },
        {
          icon: 'mdi-newspaper-variant',
          title: 'Concepts',
          to: '/concepts',
        },
        {
          icon: 'mdi-chart-areaspline',
          title: 'Analytics',
          to: '/results',
        },
        {
          icon: 'mdi-atom',
          title: 'Question Papers',
          to: '/qpapers',
        },
      ],
      title: 'Vuetify.js',
    }
  },
}
</script>
