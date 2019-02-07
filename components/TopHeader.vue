<template>
  <header class="header">
    <nav>
      <ul>
        <li>
          <nuxt-link to="/">Home</nuxt-link>
        </li>
        <li>
          <nuxt-link to="/form">Form</nuxt-link>
        </li>
      </ul>
    </nav>
  </header>
</template>

<style>

  .header {
  padding: 10px;
  text-align: center;
  background: deepskyblue;
  color: white;
}

  ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  overflow: hidden;
  background-color: #333;
}

li {
  float: left;
}

li a {
  display: block;
  color: white;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

li a:hover:not(.active) {
  background-color: #111;
}
</style>