<template>
  <v-container text-xs-center>
    <v-layout align-center justify-center column fill-height>
      <v-flex xs12 class="ma-4"
        ><h1>{{ counter }}</h1></v-flex
      >
      <v-flex xs12>
        <h1 class="display-2 font-weight-bold mb-3">{{ headLine }}</h1>
        <p class="subheading font-weight-regular">{{ subHeader }}</p>
      </v-flex>
      <v-flex v-show="!showEdit">
        <v-text-field
          label="Enter password"
          :append-icon="iconShow ? 'visibility_off' : 'visibility'"
          :type="iconShow ? 'password' : 'text'"
          @click:append="iconShow = !iconShow;"
          @keypress.enter="checkPassword();"
          v-model="password"
        >
        </v-text-field>
      </v-flex>
      <v-flex v-show="showEdit">
        <v-text-field v-model="headLine"></v-text-field>
        <v-text-field v-model="subHeader"></v-text-field>
        <v-btn @click="autoIncrease();">start counter</v-btn>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    counter: 0,
    headLine: "This is a simple counter",
    subHeader: "This is sub Header",
    showEdit: false,
    password: "",
    iconShow: true
  }),
  methods: {
    autoIncrease: function() {
      let timer = setInterval(this.increase, Math.random() * 2000);
    },
    increase: function() {
      this.counter++;
    },
    checkPassword: function() {
      if (this.password === "chert") {
        this.showEdit = true;
      }
    }
  }
};
</script>

<style></style>
