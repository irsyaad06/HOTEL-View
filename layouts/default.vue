<template>
<v-app id="app">
      <v-container id="app" fluid  class="pa-0">
        <Nuxt />
      </v-container>
</v-app>
    
</template>

<script>
export default {
  name: 'DefaultLayout',
  
}
</script>
<style scoped>
 #app{
    font-family: Poppins;
 }
</style>