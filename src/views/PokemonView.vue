<template>
  <main>
    <div class="header">
      <p>{{ title }}</p>
    </div>
  </main>
</template>

<script>
export default {
  data () {
    return {
      title: "Pokemon"
    }
  },
}
</script>

<style scoped>
.header p {
  color: var(--text-accent);
  font-size: 42px;
  font-weight: 700;
  line-height: 42px;
  margin: 0 0;
}
</style>