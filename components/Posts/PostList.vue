<template>
  <section class="featured-posts">  
      <PostPreview
        id="1"
        :is-admin="isAdmin"
        thumbnail="https://www.visioncritical.com/wp-content/uploads/2015/12/tech-companies-resources-950x700.jpg"
        title="Hello There"
        previewText="This is my first post!"
      />
      <PostPreview
        id="2"
        :is-admin="isAdmin"
        thumbnail="https://www.visioncritical.com/wp-content/uploads/2015/12/tech-companies-resources-950x700.jpg"
        title="Hello There"
        previewText="This is my second post!"
      />
      <PostPreview
        id="3"
        :is-admin="isAdmin"
        thumbnail="https://www.visioncritical.com/wp-content/uploads/2015/12/tech-companies-resources-950x700.jpg"
        title="Hello There"
        previewText="This is my third post!"
      />
  </section>
</template>

<script>
import PostPreview from '@/components/Posts/PostPreview'
export default {
  components: {
    PostPreview
  },
  props: {
    isAdmin: {
      type: Boolean,
      default: false,
    }
  }
}
</script>