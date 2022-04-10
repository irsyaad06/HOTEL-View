<template>
  <v-container
    id="home"
    class="d-flex justify-center align-content-center px-16 pt-16"
    fluid
    fill-height
  >
    <v-img
      src="hotellp2.png"
      height="480px"
      class="mx-12 rounded-lg align-center pl-16 mt-2"
    >
      <h1 class="white--text mb-8 mt-n10">
        Enjoy Your <br />
        Luxury Night
      </h1>

      <p
        class="mb-8 white--text"
        style="font-family: PoppinsThin; font-size: 15px"
      >
        lorem ipsum dolor sit amet gatau mau apa lagi yang penting kanzler hotel
        kece dah <br />
        karena dia taukan kalo aku suka ama dia dan aku juga tau dia suka ama
        gua tapi dia shy shy cat.
      </p>
      <div class="d-flex" >
        <v-img src="glh.jpg" max-width="25px" class="mr-4"></v-img>
        <p
          class="ma-0 white--text"
          style="font-family: PoppinsThin; font-size: 15px"
        >
          Supported by icad
        </p>
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
