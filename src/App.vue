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
            class="btn btn-block btn-primary"
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
    /**
     * Update the reset "signal" so all watching components know to reset their
     * counters when this signal changes.
     */
    resetAll() {
      console.log("reset sent");
      this.reset = Date.now();
    }
  }
};
</script>

<style lang="scss" scoped>
</style>
