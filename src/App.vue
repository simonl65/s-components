<template>
  <div class="container">
    <div class="row">
      <div class="col-sm-6 my-2">
        <Counter
          :reset="reset"
          class="first-counter"
        />
      </div>
      <div class="col-sm-6 my-2">
        <Counter :reset="reset" />
      </div>
      <div class="col-sm-6 my-2">
        <Counter :reset="reset" />
      </div>
      <div class="col-sm-6 my-2">
        <Counter :reset="reset" />
      </div>
    </div>
    <div class="row">
      <button
        class="btn btn-block btn-primary"
        @click="resetAll"
      >RESET ALL</button>
    </div>
  </div>
</template>

<script>
import Counter from "@/components/Counter";

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

<style lang="scss">
body {
  font-family: Arial, Lato, sans-serif;
}

.row div .counter {
  border: 1px solid $BrightYellow;
  border-radius: 10px;

  &:first-child {
    background: red;
  }

  &:not(.first-counter) {
    background: greenyellow;
    border: 2px dashed red;
  }

  /*
    Change inner padding of all .counter.col-*:
  */
  // &[class*="col-"] {
  //   padding-left: 20px;
  //   padding-right: 20px;
  // }
}
</style>
