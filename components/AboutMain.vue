<template>
  <section id="about" style="padding-top: 80px">
    <v-container fill-height class="my-2 pt-16 mb-16">
      <div>
        <v-row class="justify-center">
          <v-col md="6" sm="5" cols="12" class="pt-4">
            <header>
              <h3 class="px-0 mb-2">OUR STORY</h3>
              <h2>
                We're build the best <br />
                infrastructure for our customer. <br />
                The Luxury Thing is US,
              </h2>
            </header>
            <div class="my-11">
              <div class="pa-2 secondary rounded-circle d-inline-block"></div>
              <div
                class="pa-2 secondary rounded-circle d-inline-block mx-2"
              ></div>
              <div class="pa-2 secondary rounded-circle d-inline-block"></div>
            </div>

            <!-- <img src="/TKanzler.png" width="70px" class="ml-n4" /> -->
            <p class="mb-10">
              We are committed to providing first-class services , <br />
              Trust us with our services. <br />
              We are to fulfil our promises to customers, .
            </p>

            <p>look up to our facilities below</p>
            <v-btn outlined small class="py-5" color="#d7a368">
              Facilities >>
            </v-btn>
          </v-col>

          <v-col md="6" sm="5" cols="12" class="pt-2">
            <h3 class="text-h4 font-weight-bold">What About</h3>
            <div class="d-flex align-center mb-6">
              <p class="text-h4 font-weight-light mb-0 mr-3">Our Serve</p>
              <img src="moonasset.png" width="40px" />
            </div>
            <p>Best Services and property will give you best experience</p>
            <p class="">
              We care passionately about the quality of our editorial work.
              <br />
              Design and comfort matter to us because we want our hotels to be
              beautiful objects.
            </p>
            <br />
          </v-col>
        </v-row>
      </div>
    </v-container>
  </section>
</template>


<script>
export default {
  name: 'AboutHotel',
  data() {
    return {}
  },
}
</script>

<style>
h3 {
  color: #d7a368;
  font-family: PoppinsSemiBold;
}
</style>