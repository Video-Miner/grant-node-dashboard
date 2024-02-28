<template>
  <footer class="footer">
    <div class="container-fluid">
      <div class="copyright">
        © {{year}} <a href="https://www.video-miner.com" target="_blank" rel="noopener">Video Miner</a>
      </div>
    </div>
  </footer>
</template>
<script>
  export default {
    data() {
      return {
        year: new Date().getFullYear()
      }
    }
  };
</script>
<style scoped>
a {
  color: #2196f3 !important;
}
</style>

