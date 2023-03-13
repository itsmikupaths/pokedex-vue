<template>
  <main>
    <div class="header">
      welcome to
      <p>Pokedex</p>
    </div>
    <img src="../assets/images/gen1-homescreen-removebg.png" alt="home screen image">
    <nav>
      <a href="/pokemon">Pokemon</a>
      <a href="/about">About</a>
    </nav>
  </main>
</template>

<style scoped>
.header {
  margin-bottom: 80px;
}
.header p {
  color: var(--text-accent);
  font-size: 42px;
  font-weight: 700;
  line-height: 42px;
  margin: 0 0;
}
img {
  width: 100%;
}
nav {
  display: flex;
  flex-direction: column;
  gap: 20px;
  margin-top: 60px;
}
</style>