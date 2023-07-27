<template>
  <div id="Container" class="container">
    <br />
    <img
      src="https://avatars.githubusercontent.com/u/66653440?v=4"
      alt="Avatar of EstebanVeronesi"
      width="100"
      class="img"
    />
    <h2>Projects</h2>
    <br />
    <loading v-if="load" />
    <div class="cards" v-for="project in projects" :key="project.id">
      <Card
        :name="project.name"
        :description="project.description"
        :author="project.owner.login"
        :url="project.html_url"
        :homepage="project.homepage"
      />
    </div>
  </div>
</template>

<script>
import Card from './Card';
import Loading from './Loading.vue';
export default {
  data() {
    return {
      projects: null,
      load: false
    };
  },
  components: {
    Card,
    Loading
  },
  mounted() {
    this.getProjects();
  },
  methods: {
    async getProjects() {
      this.load = true;
      const res = await fetch(
        'https://api.github.com/users/EstebanVeronesi/repos'
      );
      const data = await res.json();

      this.load = false;
      this.projects = data;
    }
  }
};
</script>

<style scoped>
h2 {
  color: #f9f9f9;
}
.cards {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
.container {
  overflow: hidden;
  text-align: center;
  border: solid 2px rgb(58, 55, 55);
  box-shadow: 1px 1px 4px #333;
  background-color: #504f4f;
}
.img {
  border-radius: 50%;
  border: solid 2px #010101;
  box-shadow: 1px 1px 4px #333;
}
</style>
