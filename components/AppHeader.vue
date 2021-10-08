<template>
  <header>
    <div class="header">
      <!--        <div id="burger"></div>-->
      <div id="logo">
        <h1 class="title">VidApp</h1>
      </div>
      <div id="search">
        <input id="myInput" placeholder="Search for titles" type="text">
      </div>
      <div id="user">
        <nuxt-link style="margin: 0" to="">Sign in</nuxt-link>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "AppHeader"
}
</script>
