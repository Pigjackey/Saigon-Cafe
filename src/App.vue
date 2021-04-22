<template>
  <v-app style="background-color: #e6e6c1">
    <v-app-bar
      app
      color="primary"
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
