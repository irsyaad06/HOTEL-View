<template>
  <v-container fill-height style="height: 100vh">
    <v-card class="pb-10 mx-auto rounded-lg" max-width="400">
      <v-card-title class="justify-center">
        <p class="text-h4 text--primary ma-0 font-weight-bold">Login</p>
      </v-card-title>
      <v-divider class="d-block"></v-divider>
      <body class="px-11 pt-5">
        <v-card-text>
          <v-text-field
            v-model="name"
            :error-messages="errors"
            label="Username"
            required
          ></v-text-field>
          <v-text-field
            v-model="name"
            :error-messages="errors"
            label="Password"
            required
          ></v-text-field>
        </v-card-text>
      </body>
      <v-card-actions class="justify-center">
        <v-btn class="text-capitalize px-16" rounded color="primary" to="/">
          <p class="px-3 ma-0">Login</p>
        </v-btn>
      </v-card-actions>
      <v-card-actions class="justify-center">
        <small style="color:grey">
          Not a member?
          <nuxt-link class="text-capitalize" text color="primary" to="signup">
            Sign Up
          </nuxt-link>
        </small>
      </v-card-actions>
    </v-card>
  </v-container>
</template>

<script>
export default {
  name: 'LoginForms',
}
</script>