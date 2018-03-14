<template>
  <div class="posts-page">
    <PostList :posts="dummyPosts" />
  </div>
</template>

<script>
import PostList from '@/components/Posts/PostList'

export default {
  components: {
    PostList
  },
  asyncData(context, callback) {
    callback(null, {
      dummyPosts: [
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
  }
}
</script>


<style scoped>
.posts-page {
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
