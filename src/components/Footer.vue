<template>
  <div id="footer">
    <footer>
      <h3 class="p-3">&copy; Esteban Veronesi - {{ year }}</h3>
    </footer>
  </div>
</template>

<script>
export default {
  computed: {
    year() {
      return new Date().getFullYear();
    }
  }
};
</script>

<style scoped>
h3 {
  background-color: #010101;
  margin-top: 7px;
  width: 100%;
  text-align: center;
  color: #f9f9f9;
  width: 100%;
}
</style>
