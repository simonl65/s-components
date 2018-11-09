<template>
  <div class="container">
    <div class="row">
        <Counter
            ref="Counter1"
            class="col-sm-6 my-2 counter"
        />
        <Counter
            ref="Counter2"
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
      this.$refs.Counter1.resetCount();
      this.$refs.Counter2.resetCount();
    }
  }
};
</script>

<style lang="scss" scoped>
</style>
