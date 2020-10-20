<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
    <li v-for="post of posts" :key="post.slug">
      <NuxtLink :to="post.slug">{{ post.title }}</NuxtLink>
    </li>

    </v-col>
  </v-row>
</template>

<script>
export default {
     async asyncData({ $content }) {
    const posts = await $content("blog").fetch();

    return {
      posts,
    };
  },
  components: {
  },
    head() {
    return {
      script: [{ src: 'https://identity.netlify.com/v1/netlify-identity-widget.js' }],
    }
  },
}
</script>
