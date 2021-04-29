<template>
  <v-app>
    <v-main>
      <Post/>
      <!-- <Dashboard /> -->
    </v-main>
  </v-app>
</template>

<script>
import Post from './components/Post';
// import Dashboard from './components/Dashboard';

export default {
  name: 'App',

  components: {
    Post
  },

  data: () => ({
    //
  }),
};
</script>
