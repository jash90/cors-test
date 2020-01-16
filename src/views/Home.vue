<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <button @click="greet">
      <H1>Test</H1>
    </button>

    <H1></H1>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "home",
  components: {},
  data() {
    return {
      msg: "Hello"
    };
  },
  methods: {
    greet() {
      fetch("http://smarthome.raccoonsoftware.pl/conditions")
        .then(response => response.json())
        .then(responseJson => {
          msg = JSON.stringify(responseJson);
        })
        .catch(error => {
          console.error(error);
        });
    }
  }
};
</script>
