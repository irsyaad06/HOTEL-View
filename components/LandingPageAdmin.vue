<template>
  <v-container class="justify-end" style="margin-top: 150px">
    <h1 class="d-flex justify-center">
      ROOM TYPE <font class="font-weight-thin ml-3"> TABLE </font>
    </h1>

    <v-simple-table class="mt-16">
      <template v-slot:default>
        <thead>
          <tr>
            <th v-for="(header, i) in headers" :key="i" class="text-center">
              {{ header.text }}
            </th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(jenis, i) in jenkam" :key="i" class="text-center">
            <td>{{ jenis.id }}</td>
            <td>{{ jenis.name }}</td>
            <td>{{ jenis.jumlah }}</td>
            <td>
              <v-btn plain small icon @click.stop="edites = true">
                <v-icon small> mdi-pencil-outline </v-icon>
              </v-btn>

              <v-btn plain small icon @click.stop="deletess = true">
                <v-icon small> mdi-delete-outline </v-icon>
              </v-btn>
              <!-- dialog edit -->
              <v-dialog v-model="edites" persistent max-width="600px">
                <v-card>
                  <v-card-title>
                    <span class="text-h5">Change Type Room</span>
                  </v-card-title>
                  <v-card-text>
                    <v-container>
                      <v-row>
                        <v-col sm="12" md="6">
                          <v-text-field
                            v-model="editnama"
                            label="Type Room Name*"
                            required
                          ></v-text-field>
                        </v-col>
                      </v-row>
                    </v-container>
                  </v-card-text>
                  <v-card-actions>
                    <v-spacer></v-spacer>
                    <v-btn
                      color="blue darken-1"
                      plain
                      text
                      @click="edites = false"
                    >
                      Close
                    </v-btn>
                    <v-btn
                      color="green darken-1"
                      plain
                      text
                      @click="updates(jenis.id)"
                    >
                      Save
                    </v-btn>
                  </v-card-actions>
                </v-card>
              </v-dialog>
              <!-- dialog delete -->
              <v-dialog v-model="deletess" persistent max-width="290">
                <v-card>
                  <v-card-title class="text-h5"> Delete item? </v-card-title>

                  <v-card-text>
                    Careful because you will permanently delete this item.
                  </v-card-text>

                  <v-card-actions>
                    <v-spacer></v-spacer>
                    <v-btn
                      color="grey darken-1"
                      text
                      plain
                      small
                      @click="deletess = false"
                    >
                      Close
                    </v-btn>

                    <v-btn
                      color="red darken-1"
                      text
                      plain
                      small
                      @click="deletes(jenis.id)"
                    >
                      Delete
                    </v-btn>
                  </v-card-actions>
                </v-card>
              </v-dialog>
            </td>
          </tr>
        </tbody>
      </template>
    </v-simple-table>
    <v-div class="d-flex justify-end">
      <v-btn fab small @click="buat = true">
        <v-icon color="black"> mdi-plus </v-icon>
      </v-btn>

      <v-dialog v-model="buat"> </v-dialog>
    </v-div>
  </v-container>
</template>


<script>
import axios from 'axios'
export default {
  name: 'LandingPageAdmin',
  data() {
    return {
      id: '',
      search: '',
      buat: false,
      edites: false,
      editnama: '',
      editharga: 69000,
      editkapasitas: 69,
      deletess: false,
      jenkam: null,
      headers: [
        { text: 'Number' },
        { text: 'Room Type' },
        { text: 'Amount Room' },
        { text: 'Actions' },
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
    updates(id) {
      this.edites = false
      axios
        .put('http://localhost:5000/services/jenis-kamar/' + id, {
          name: this.editnama,
          // harga_kamar: this.editharga,
          // max_kapasitas: this.editkapasitas,
        })
        .then(console.log)
        .catch(console.error)
    },
    deletes(id) {
      axios
        .delete('http://localhost:5000/services/jenis-kamar?id=' + id)
        .then(console.log)
        .catch(console.error)
    },
    created() {
      axios
        .post('http://localhost:5000/services/jenis-kamar')
        .then(console.log)
        .catch(console.error)
    },
  },
}
</script>
 <style>
</style>