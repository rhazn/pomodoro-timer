<template>
  <router-view />
  <div id="nav">
    <router-link to="/">Timer</router-link>
    <router-link to="/about">Settings</router-link>
    <router-link to="/stats">Stats</router-link>
  </div>
</template>

<style>
:root {
  --font-text: "Space Mono", monospace;
  --font-title: "BioRhyme", serif;

  --background-color: var(--prussian-blue);
  --text-color: var(--lemon-meringue);

  --highlight-color: var(--maximum-yellow-red);

  --prussian-blue: #003049ff;
  --maximum-red: #d62828ff;
  --orange: #f77f00ff;
  --maximum-yellow-red: #fcbf49ff;
  --lemon-meringue: #eae2b7ff;
}

@import url("https://fonts.googleapis.com/css2?family=BioRhyme:wght@200;400&family=Space+Mono&display=swap");

html {
  font-size: 100%;
} /*16px*/

body {
  background-color: var(--background-color);
  font-family: var(--font-text);
  font-weight: 400;
  line-height: 1.75;

  margin: 0;
  padding: 0;
  border: 0;
}
p {
  margin-bottom: 1rem;
}

h1,
h2,
h3,
h4,
h5 {
  font-family: var(--font-title);
  color: var(--text-color);
  margin: 3rem 0 1.38rem;
  font-weight: 400;
  line-height: 1.3;
}

h1 {
  margin-top: 0;
  font-size: 3.052rem;
}

h2 {
  font-size: 2.441rem;
}

h3 {
  font-size: 1.953rem;
}

h4 {
  font-size: 1.563rem;
}

h5 {
  font-size: 1.25rem;
}

small,
.text_small {
  font-size: 0.8rem;
}

#nav {
  box-sizing: border-box;
  width: 100%;
  position: fixed;
  bottom: 0px;
  padding: 1rem;

  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: space-around;

  border-top: var(--text-color) 5px solid;
}

#nav a {
  font-size: 1.5rem;
  color: var(--text-color);
}

#nav a.router-link-exact-active {
  font-weight: bold;
  color: var(--highlight-color);
}
</style>
