<template>
  <v-app dark>
    <my-menu />
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import MyMenu from "~/components/MyMenu";
export default {
  comments: {
    MyMenu
  }
}
</script>
