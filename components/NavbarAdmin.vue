<template>
  <section id="navbar">
    <v-container fluid class="ma-0 pa-0">
      <v-app-bar
        fixed
        elevate-on-scroll
        color="white"
        height="69px"
        class="px-16"
      >
        <nuxt-link to="/">
          <v-img src="Kanzler.png" width="130px" class="ml-10 pa-0"></v-img>
        </nuxt-link>

        <v-spacer></v-spacer>

        <v-toolbars>
          <v-toolbar-items
            class="text-decoration-none hidden-xs-only d-sm-flex"
          >
            <v-list-item class="pa-0 align-center">
              <nuxt-link class="d-flex justify-center" to="/">
                <v-items class="d-flex justify-center" @click="scrollToHome()">
                  Home
                </v-items>
              </nuxt-link>

              <a
                v-for="(items, i) in linkbar"
                :key="i"
                class="d-flex justify-center align-center"
              >
                <v-items
                  class="d-flex justify-center"
                  @click="scrollTo(items.link)"
                >
                  {{ items.title }}
                </v-items>
              </a>
            </v-list-item>
          </v-toolbar-items>

          <v-btn
            class="hidden-sm-and-up pl-4"
            icon
            @click="Clicklist = !Clicklist"
          >
            <v-icon color="black"> mdi-menu</v-icon>
          </v-btn>
        </v-toolbars>

        <v-spacer></v-spacer>

        <v-toolbars class="mx-10 ml-13">
          <nuxt-link to="/">
            <v-btn outlined small color="#342719" class="py-5 px-4">
              Customers
            </v-btn>
          </nuxt-link>
          <!-- <v-btn small outlined color="primary" class="py-5 px-4 ml-5"> Sign In </v-btn> -->
        </v-toolbars>
      </v-app-bar>
    </v-container>
  </section>
</template>

<script>
export default {
  name: 'NavbarSection',
  data() {
    return {
      drawer: null,
      Clicklist: false,
      linkbar: [
        // { title: "Home", icon: "" , link:"/AdminPage"},
        { title: 'Room', icon: '', link: 'room' },
        { title: 'Facilities', icon: '', link: 'facilities' },
      ],
    }
  },
  methods: {
    scrollTo(id) {
      document.getElementById(id).scrollIntoView({ behavior: 'smooth' })
      this.Clicklist = false
    },
    scrollToHome() {
      document.getElementById('home').scrollIntoView({ behavior: 'smooth' })
      this.Clicklist = false
    },

    CloseNavbar() {
      this.Clicklist = false
    },
  },
}
</script>

<style>
#navbar {
  font-family: Poppins;
}
a {
  text-decoration: none;
}
v-items {
  font-family: PoppinsSemiBold;
}
.v-toolbar__content {
  padding: 4px 12px 4px 12px !important;
}
v-items {
  color: black;
  transition: 0.5s;
  width: 90px;
  font-size: 14px;
}
v-items:hover {
  font-size: 16px;
  transition: 0.5s;
}
@media (max-width: 600px) {
  v-items p {
    color: black;
    transition: 0.5s;
    width: 90px;
    font-size: 13px;
  }
  v-items p:hover {
    font-size: 13px;
  }
}
</style>