<template>
  <article class="post">
    <el-card
      shadow="hover"
      :body-style="{padding: 0}"
      class="post"
    >
      <header slot="header" class="post-header">
        <h3>Post Title</h3>
        <small>
          <i class="el-icon-time"></i>
          {{ new Date().toLocaleString() }}
        </small>
      </header>
      <div class="post-body"></div>
      <footer class="post-footer">
        <el-button round @click="openPost">Открыть</el-button>
        <span>
          <i class="el-icon-message" />
          12
        </span>
      </footer>
    </el-card>
  </article>
</template>

<script>
export default {
  name: 'Post',
  methods: {
    openPost() {
      const id = 'test-path'
      this.$router.push(`/post/${id}`)
    }
  }
}
</script>

<style lang="scss" scoped>
  .post {
    margin-bottom: 1.5rem;
  }
  .post-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .post-body {
    height: 400px;
    width: 100%;
    background-image: url("https://pbs.twimg.com/media/EWmfHQZWkAEprOA.jpg:large");
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
  }
  .post-footer {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem;
  }
</style>
