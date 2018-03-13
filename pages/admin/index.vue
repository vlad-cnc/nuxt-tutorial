<template>
  <div class="admin-page">
    <section class="new-post">
      <appButton @click="$router.push('/admin/new-post')">Create Post</appButton>
    </section>
    <section class="existing-posts">
      <h1>Existing Posts</h1>
      <PostList isAdmin/>
    </section>
  </div>
</template>

<script>
import PostList from '@/components/Posts/PostList'
import appButton from '@/components/UI/appButton'
export default {
  layout: 'admin',
  components: {
    PostList,
    appButton
  }

}
</script>
