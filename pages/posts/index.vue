<template>
  <div class="posts-page">
    <PostList/>
  </div>
</template>

<script>
import PostList from '@/components/Posts/PostList'
export default {
  components: {
    PostList
  }
}
</script>


<style scoped>
.posts-page {
  display: flex;
  align-items: center;
  justify-content: center;
}

.featured-posts {
  display: flex;
  padding: 20px;
  box-sizing: border-box;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
}

</style>
