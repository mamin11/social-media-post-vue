<template>
  <v-container>
    <v-row class="text-center">
      <PostImage/>

      <v-col
        class="mb-5"
        cols="12"
      >
      <LikeCounter @incrementParentLikes="updateLikes" :likes.sync="likes"/>
      <Comments :comments="comments" />
      </v-col>

    </v-row>
  </v-container>
</template>

<script>
import PostImage from './Posts/PostImage.vue'
import LikeCounter from './Posts/LikeCounter.vue'
import Comments from './Posts/Comments.vue'
  export default {
  components: { PostImage, LikeCounter, Comments },
    name: 'Post',

    data: () => ({
      likes: 221,
      comments: [
        {text: 'OMG this is amazing 🤩'},
        {text: 'sooo coool 🔥'},
        {text: '🔥🔥🔥🔥🔥🔥🔥🔥'},
        {text: 'This Lorem ipsum dolor sit amet, consectetur adipisicing 🥇.'},
      ],

    }),

    methods: {
      updateLikes () {
        // console.log('incrementing from parent function')
        this.likes++
      }
    },

  }
</script>
