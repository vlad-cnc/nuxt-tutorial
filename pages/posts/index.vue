<template>
  <div class="posts-page">
    <PostList :posts="loadedPosts" />
  </div>
</template>

<script>
import PostList from '@/components/Posts/PostList'

export default {
  components: {
    PostList
  },
  fetch(context) {
    return new Promise((resolve, reject) => {
      setTimeout( 
        resolve({
          loadedPosts: [
            { 
              id: '1',
              title: 'First Post za postspage',
              previewText: 'This is our first staghod',
              thumbnail: 'https://cdn.techinasia.com/wp-content/uploads/2017/06/47724337_l.jpg'
            },
            { 
              id: '2',
              title: 'Second Postpage',
              previewText: 'This is our second staghod',
              thumbnail: 'http://anthillonline.com/wp-content/uploads/2016/03/keyboard.jpg'
            }
          ]
        })
      ,1000)
    })
    .then(data => {
      return data
    })
    .catch(e => {
      context.error(new Error())
    })
  },
  // created() {
  //   this.$store.dispatch('setPosts', this.loadedPosts)
  // }
  
}
</script>


<style scoped>
.posts-page {
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
