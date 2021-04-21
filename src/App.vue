<template>
  <v-app>
    <v-app-bar
      app
      color="green darken-3"
      dark
    >
      <div class="d-flex align-center">
        <h2>Saigon Cafe</h2>
      </div>
      <v-spacer></v-spacer>
    </v-app-bar>

    <v-main>
      <Main/>
    </v-main>
  </v-app>
</template>

<script>
import Main from './components/Main';

export default {
  name: 'App',

  components: {
    Main,
  },

  data: () => ({
    //
  }),
};
</script>
