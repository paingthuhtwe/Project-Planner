<template>
  <div class="home">
    <h1>Home</h1>
    <div v-for="project in projects" :key="project.id">
      <SingleProject :project="project" @delete="deleteProject"></SingleProject>
    </div>
  </div>
</template>

<script>
import SingleProject from "../components/SingleProject";
// @ is an alias to /src

export default {
  name: "Home",
  components: {
    SingleProject,
  },
  data() {
    return {
      projects: [],
    };
  },
  mounted() {
    fetch("http://localhost:3000/projects")
      .then((response) => {
        return response.json();
      })
      .then((data) => {
        this.projects = data;
      })
      .catch((err) => {
        console.log(err.message());
      });
  },
  methods: {
    deleteProject(id) {
      this.projects = this.projects.filter((project) => {
        return project.id != id;
      });
    },
  },
};
</script>
