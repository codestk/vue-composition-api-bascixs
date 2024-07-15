<template>
  <div class="PostsDetails">
    <h1>PostsDetails</h1>
    <p>parameter {{ $route.params.id }}</p>
    <p>
      <router-link to="/Posts">Back</router-link>
    </p>
  </div>
</template>

<script setup>
    this.$route
</script>
