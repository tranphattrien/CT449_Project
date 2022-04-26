<template>
  <v-app id="inspire">
    <v-navigation-drawer v-model="drawer" app class="nav">
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title> FOOTBALL BLOG </v-list-item-title>
        </v-list-item-content>
      </v-list-item>
      <v-divider></v-divider>
      <v-list dense fixed>
        <v-list-item-group color="primary">
          <v-list-item v-for="(item, i) in items" :key="i" :to="item.link" link>
            <v-list-item-icon>
              <v-icon v-text="item.icon"></v-icon>
            </v-list-item-icon>
            <v-list-item-content>
              <v-list-item-title v-text="item.title"></v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar fixed app class="header">
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title>Application</v-toolbar-title>
    </v-app-bar>

    <v-main class="bg">
      <router-view></router-view>
    </v-main>
  </v-app>
</template>

<script>
export default {
  data: () => ({
    drawer: null,
    items: [
      { title: "Home", icon: "mdi-home", link: "/" },
      { title: "Add Post", icon: "mdi-note-plus", link: "/add-post" },
      { title: "About", icon: "mdi-help", link: "/about" }
    ]
  })
};
</script>
<style>
.header {
  background-image: linear-gradient(
    to right bottom,
    rgba(221, 238, 249, 0.7),
    rgba(188, 237, 249, 0.5)
  );
  margin: 10px 10px !important;
  border-radius: 10px !important;
  z-index: 2;
}
.bg {
  background: linear-gradient(45deg, #6f86d6, #88f0f8);
}
.nav {
  background-image: linear-gradient(
    to right bottom,
    rgba(221, 238, 249, 0.7),
    rgba(188, 237, 249, 0.5)
  );
  margin: 10px 10px 10px 5px !important;
  border-radius: 10px !important;
  z-index: 2;
  height: 97% !important;
}
</style>
