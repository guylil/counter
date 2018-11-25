<template>
  <v-app>
    <v-toolbar app>
      <v-toolbar-title class="headline text-uppercase">
        The <span>Cost</span>
        <!--
          <span class="font-weight-light"> for more details &ndash;&gt;</span>
        -->
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn flat href="https://zehut.org.il/" target="_blank">
        <span class="mr-2">Zehut</span>
      </v-btn>
    </v-toolbar>

    <v-content>
      <Counter />
    </v-content>
  </v-app>
</template>

<script>
import Counter from "./components/Counter";

export default {
  name: "App",
  components: {
    Counter
  },
  data() {
    return {
      //
    };
  }
};
</script>
