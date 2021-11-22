<template>
  <main>
    <input type="text" v-model="search">
    <div v-for="project in filteredProjects" :key="project.id">
      <Project :project="project" />
    </div>
  </main>
</template>

<script>
import Project from '@/components/Project'

export default {
  name: 'App',
  components: { Project },
  data () {
    return {
      search: '',
      projects: [
        {
          id: 1,
          title: "Project 1",
          body: "This is project 1"
        },
        {
          id: 2,
          title: "Project 2",
          body: "This is project 2"
        },
        {
          id: 3,
          title: "Project 3",
          body: "This is project 3"
        }
      ]
    }
  },
  computed: {
    filteredProjects() {
      return this.projects.filter(project =>
        project.body.toLowerCase().includes(this.search.toLowerCase())
      );
    }
  }
}
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
