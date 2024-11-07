<template>
  <v-app>
    <v-card>
      <v-layout>
        <v-app-bar color="primary" prominent>
          <v-app-bar-nav-icon variant="text" @click.stop="drawer = !drawer"></v-app-bar-nav-icon>

          <v-toolbar-title>My files</v-toolbar-title>

          <v-spacer></v-spacer>

          <template v-if="$vuetify.display.mdAndUp">
            <v-btn icon="mdi-magnify" variant="text"></v-btn>

            <v-btn icon="mdi-filter" variant="text"></v-btn>
          </template>

          <v-btn icon="mdi-dots-vertical" variant="text"></v-btn>
        </v-app-bar>

        <v-navigation-drawer v-model="drawer" :location="$vuetify.display.mobile ? 'bottom' : undefined" temporary>
          <v-list>
            <v-list>
              <v-list-item to="/login" router-link>
                <v-list-item-content>
                  <v-list-item-title>Login</v-list-item-title>
                </v-list-item-content>
              </v-list-item>
              <v-list-item to="/home" router-link>
                <v-list-item-content>
                  <v-list-item-title>Home</v-list-item-title>
                </v-list-item-content>
              </v-list-item>
            </v-list>
          </v-list>
        </v-navigation-drawer>

        <v-main style="height: 500px;">
        </v-main>
      </v-layout>
    </v-card>
    <v-main>
      <router-view></router-view>
    </v-main>
  </v-app>
</template>

<script>

export default {
  name: 'App',

  components: {
  },

  data: () => ({
    drawer: false,
  }),
}
</script>
