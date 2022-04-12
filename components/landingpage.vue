<template>
  <section id="home">
    <v-container
      class="d-flex justify-center align-content-center px-16 pt-16"
      fluid
      fill-height
    >
      <v-img
        src="hotellp2.png"
        height="480px"
        class="mx-12 rounded-lg align-center pl-16 mt-2"
      >
        <h1 class="white--text mb-6 mt-n10">
          Enjoy Your <br />
          Luxury Night
        </h1>

        <p
          class="mb-8 white--text"
          style="font-family: PoppinsThin; font-size: 15px"
        >
          Welcome to our hotel , The Grand Luxury Kanzler Hotel . <br />
          Gain a lot of advantages from our great facilities with good view
          outside.
        </p>
        <div class="d-flex">
          <p
            class="ma-0 white--text"
            style="font-family: PoppinsThin; font-size: 15px"
          >
            Supported by :
          </p>
          <v-img src="glh.jpg" max-width="25px" class="ml-4"></v-img>
        </div>
      </v-img>
      <v-card
        class="rounded-lg justify-center"
        height="160px"
        width="1200px"
        style="margin-top: -80px"
      >
      </v-card>
    </v-container>
  </section>
</template>

<script>
export default {
  name: 'LandingPages',
  data() {
    return {}
  },
}
</script>

<style>
#home {
  justify-content: center !important;
}
h1 {
  font-family: PoppinsSemiBold;
  font-size: 50px;
}
</style>
