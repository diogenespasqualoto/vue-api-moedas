<template>
  <div class="container grid-lg my-2 py2 text-dark">
    <div class="card">
      <div class="card-header">
        <div class="h4">Exibindo as moedas!</div>
      </div>
      <div class="card-body"><HelloWorld :quotes="quotes" /></div>
    </div>
  </div>
</template>

<script>
import api from "@/servidor/api.js";
import HelloWorld from "./components/HelloWorld.vue";
import { onMounted, reactive, toRefs } from "vue";

export default {
  name: "App",
  components: {
    HelloWorld,
  },

  setup() {
    const data = reactive({
      quotes: {},
    });
    onMounted(async () => {
      const response = await api.all();
      data.quotes = response.data;
    });

    return {...toRefs(data)}
  },
};
</script>

<style>
.container
.h4 {
  text-align: center;
  margin-bottom: 10px;
}
.card {
  box-shadow: 0 0 2em black;
}
</style>
