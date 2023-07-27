<template>
  <div id="cards">
    <div class="card">
      <h4>{{ name }}</h4>
      <br />
      <p>
        {{ description }}
      </p>
      <br />
      <p>
        <strong>{{ author }}</strong>
      </p>

      <button-url color="red" :url="url" />
      <button-url :url="homepage" v-if="homepage != null" title="Deploy" />
    </div>
  </div>
</template>

<script>
import ButtonUrl from './ButtonUrl.vue';
export default {
  components: { ButtonUrl },
  props: {
    name: String,
    description: String,
    author: String,
    url: String,
    homepage: String
  }
};
</script>

<style scoped>
.card {
  width: 250px;
  margin: 7px;
  text-align: center;
  border: solid 2px rgb(58, 55, 55);
  box-shadow: 1px 1px 4px #333;
  background-color: #ede8e4;
  border-radius: 2.4%;
}
</style>
