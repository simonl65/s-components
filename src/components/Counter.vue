<template>
  <div class="counter">
    <div
      class="count--current"
    >
      {{ currentCount }}
    </div>
    <button
      class="btn col-6 btn-danger"
      @click="dec"
    >-</button>
    <button
      class="btn col-6 btn-success"
      @click="inc"
    >+</button>
    <hr>
    <button
      class="btn btn-block btn-secondary"
      @click="resetCounter"
    >RESET</button>
  </div>
</template>

<script>
export default {
  name: "Counter",

  props: {
    reset: {
      type: Number,
      default: Date.now()
    }
  },

  data() {
    return {
      currentCount: 0
    };
  },

  watch: {
    /**
     * When the "reset" signal CHANGES, reset the counter.
     */
    reset() {
      console.log("reset received");
      _reset(this);
    }
  },

  methods: {
    inc() {
      this.currentCount++;
    },

    dec() {
      this.currentCount--;
    },

    resetCounter() {
      _reset(this);
    }
  }
};

function _reset(t) {
  t.currentCount = 0;
}
</script>

<style lang="scss" scoped>
.counter {
  text-align: center;
  border: 1px solid #ccc;
  border-radius: 5px;
  padding: 1rem;
  padding-top: 0;
}

.count--current {
  font-size: 3rem;
}
</style>
