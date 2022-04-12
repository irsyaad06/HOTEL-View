<template>
  <section id="room">
    <v-container class="align-end justify-center mt-16 pt-16 pa-0" fill-height>
      <h1 class="d-flex justify-center">
        KNZLR ROOM TYPE <font class="font-weight-thin ml-3"> </font>
      </h1>
      <v-container fluid fill-height class="align-start justify-center pa-0 mt-10">
        <v-card
          class="mx-11 mb-16 py-5 px-6 rounded-lg"
          hover
          max-width="300"
          v-for="(tyroom, i) in tydata"
          :key="i"
        >
          <v-img :src="tyroom.img" height="200px" class="rounded-lg"></v-img>

          <v-card-title class="text-h5 font-weight-bold my-5 pa-0">
            {{ tyroom.title }}
          </v-card-title>

          <v-card-subtitle class="pa-0">
            {{ tyroom.subtitle }}
          </v-card-subtitle>

          <v-card-actions class="pa-0 my-2">
            <small class="text-capitalize" @click="tyroom.k = !tyroom.k">
              {{ tyroom.k ? 'View Facilities' : 'Close' }}
            </small>
          </v-card-actions>

          <v-card-actions class="d-flex justify-center">
            <v-btn
              color="brown"
              elevation="0"
              width="250px"
              class="py-6 white--text text-capitalize rounded-lg"
              @click="scrollToHome()"
            >
              Book now
            </v-btn>
          </v-card-actions>

          <v-expand-transition>
            <div v-show="!tyroom.k">
              <v-divider></v-divider>

              <v-card-text class="pb-0" v-for="(jeniss,i) in jenkam" :key="i">
                {{ jeniss.jenis_kamar_id }
              </v-card-text>
            </div>
          </v-expand-transition>
        </v-card>
      </v-container>
    </v-container>
  </section>
</template>

<script>
import axios from 'axios'
export default {
  name: 'TypeRoom',
  data() {
    return {
      jenkam:'null',
      show: false,
      tydata: [
        {
          title: 'Regular',
          subtitle: 'Feel good sensation With Gayung Pecah and rough kapuk',
          facilities: 'kasur',
          k: 'show',
          img: 'Regular.jpg',
        },
        {
          title: 'Supperior',
          subtitle: 'Feel Supperior Typerooms with coconut and kanzler',
          facilities:
            'Room with 32m2 Large | Shower Room | Coffe Maker | Air Conditioner | LED TV 100inch',
          k: 'show',
          img: 'Supperior.jpg',
        },
        {
          title: 'Deluxe',
          subtitle: 'Feel the Deluxe room with some sugar and bananas',
          facilities: 'Deluxe',
          k: 'show',
          img: 'Deluxe.jpg',
        },
      ],
    }
  },
  
  mounted() {
    axios
      .get('http://localhost:5000/services/jenis-kamar')
      .then((res) => (this.jenkam = res.data.result))
      .catch(console.error)
  },
  methods: {
    scrollToHome() {
      document.getElementById('home').scrollIntoView({ behavior: 'smooth' })
      this.Clicklist = false
    },
  },
}
</script>

<style>
small {
  color: rgb(159, 139, 41);
  transition: 0.5s;
}
small:hover {
  color: rgb(236, 213, 97);
  transition: 0.5s;
}
</style>