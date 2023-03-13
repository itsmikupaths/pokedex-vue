<template>
  <main>
    <div class="header">
      welcome to
      <p>Pokedex</p>
    </div>
    <img src="../assets/images/gen1-homescreen-removebg.png" alt="home screen image">
    <nav>
      <a href="/pokedex">Pokedex</a>
      <a href="/about">About</a>
    </nav>
  </main>
</template>

<style scope>
main {
  color: var(--text);
}
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
a {
  border: 1px solid var(--text-accent);
  border-radius: 5px;
  color: var(--text);
  text-decoration: none;
  padding: 10px;
  display: flex;
  justify-content: center;
  font-size: 20px;
  font-weight: 700;
}
a:hover {
  background-color: var(--text-accent);
  color: var(--text-grey);
}
</style>