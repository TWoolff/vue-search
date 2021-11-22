<template>
  <article>
    <h2>{{ project.title }}</h2>
    <p>{{ project.body }}</p>
  </article>
</template>

<script>
export default {
  props: [ 'project' ]
}
</script>
