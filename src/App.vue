<template>
  <div class="container">
    <div class="row">
        <Counter
            :reset="reset"
            class="col-sm-6 my-2 counter"
        />
        <Counter
            :reset="reset"
            class="col-sm-6 my-2 counter"
        />
    </div>
    <div class="row">
        <button
            @click="resetAll"
            class="btn btn-block btn-danger"
        >RESET ALL</button>
    </div>
  </div>
</template>

<script>
import Counter from "./components/Counter.vue";

export default {
  components: {
    Counter
  },

  data() {
    return {
      reset: null
    };
  },

  methods: {
    resetAll() {
      console.log("reset sent");
      this.reset = !this.reset;
    }
  }
};
</script>

<style lang="scss" scoped>
</style>
