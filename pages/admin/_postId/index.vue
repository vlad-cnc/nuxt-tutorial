<template>
  <div class="admin-post-page">
    <section class="update-form">
      <AdminPostForm :posts="loadedPost" @submit="onSubmitted"/>
    </section>
  </div>
</template>

<script>
import axios from 'axios'
import AdminPostForm from '@/components/Admin/AdminPostForm'

export default {
  layout: 'admin',
  components: {
    AdminPostForm
  },
  asyncData(context) {
    return axios.get('https://nuxt-blog-b7a24.firebaseio.com/posts/' + context.params.id + '.json')
    .then(res => {
      return {
        loadedPost: {...res.data, id: context.params.post.id}
      }
    })
    .catch(e => context.error(e))
  },
  methods: {
    onSubmitted(editedPost) {
      this.$store.disppatch('editPost', editedPost).then(() => {
        this.$router.push('/admin');
      })
    }
  },
}
</script>

<style scoped>
.update-form {
  width: 90%;
  margin: 20px auto;
}

@media (min-width: 768px) {
  .update-form {
    width: 500px;
  }
}
</style>
