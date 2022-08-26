<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <article>
    <h2>{{ anime.title }}</h2>
    <p>
      {{ anime.description }}
    </p>
  </article>
</template>

<script>
export default {
  props: ["anime"],
};
</script>

<style>
article {
  background-color: #fefae0;
  border-radius: 1rem;
  padding: 1rem 2rem;
  box-shadow: 0px 3px 6px rgba(0, 0, 0, 0.2);
  margin-bottom: 2rem;
  color: #283618;
}
article h2 {
  margin-bottom: 1rem;
}
</style>