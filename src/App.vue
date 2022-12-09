<template>
  <header>
    <router-link to="/" >
      <h1>Kakashi's<span>Vue</span>Movies App</h1>
    </router-link>
  </header>
  <main>
    <router-view/>
  </main>
</template>

<style lang="scss">
  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: Arial, Helvetica, sans-serif;

    &::selection {
      background: transparentize(#42b883, 0.5);
    }
  }

  body {
    background: #333;
  }

  a {
    text-decoration: none;
  }

  header {
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 10px 16px;
    background: #333;
    box-shadow: 0px 0px 6px rgba(0,0,0,0.1);
  }

  h1 {
    color: #fff;
    font-size: 28px;

    span {
      color: #42b883;
    }
  }

</style>
