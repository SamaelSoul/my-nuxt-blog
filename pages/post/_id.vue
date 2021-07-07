<template>
  <article class="post">
    <header class="post-header">
      <div class="post-title">
        <nuxt-link to="/">
          <i class="el-icon-back"></i>
        </nuxt-link>
        <h1>Post title</h1>
      </div>
      <div class="post-info">
        <small>
          <i class="el-icon-time"></i>
          {{ new Date().toLocaleString() }}
        </small>
        <small>
          <i class="el-icon-view"></i>
          42
        </small>
      </div>
      <div class="post-img">
        <img
          src="https://pbs.twimg.com/media/EWmfHQZWkAEprOA.jpg:large"
          alt="post-image"
        >
      </div>
    </header>
    <main class="post-content">
      <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ad beatae fugiat modi nostrum ullam. Nulla.</p>
    </main>
    <footer>
      <!-- Form -->
      <div class="comments" v-if="true">
        <comment v-for="comment in 4" :key="comment" :comment="comment"/>
      </div>
      <div class="text-center" v-else>Комментариев пока нет...</div>
    </footer>
  </article>
</template>

<script>
import Comment from "~/components/main/Comment";

export default {
  name: "_id.vue",
  components: {
    Comment
  },
  validate({params}) {
    return Boolean(params.id)
  }
}
</script>

<style lang="scss" scoped>
.post {
  max-width: 600px;
  margin: 0 auto;
}
.post-title {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 1rem;
}
.post-img {
  img {
    width: 100%;
    height: auto;
  }
}
.post-info {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: .5rem;
}
.post-header {
  margin-bottom: 1.5rem;
}
.post-content {
  margin-bottom: 2rem;
}
</style>
