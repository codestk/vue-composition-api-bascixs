<template>
  <div class="AboutView">
    <h1>Posts</h1>

    <ul>
      <li><router-link to="/PostsDetails/id1">Post1</router-link></li>
      <li><router-link to="/PostsDetails/id2">Post2</router-link></li>
      <li><router-link to="/PostsDetails/id3">Post3</router-link></li>
    </ul>
    <textarea v-Autofocus></textarea>
  </div>
</template>

<script setup>
import { vAutofocus } from "@/directives/vAutofocus";
</script>
