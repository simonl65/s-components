<template>
    <div class="counter">
        <div class="count--current"
        >
            {{ currentCount }}
        </div>
        <button @click="dec" class="btn col-6 btn-danger">-</button>
        <button @click="inc" class="btn col-6 btn-success">+</button>
        <hr>
        <button @click="resetCounter" class="btn btn-block btn-secondary">RESET</button>
    </div>
</template>

<script>
export default {
  name: "counter",

  data() {
    return {
      currentCount: 0
    };
  },

  props: ["reset"],

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
  },

  watch: {
    /**
     * When the "reset" signal CHANGES, reset the counter.
     */
    reset() {
      console.log("reset received");
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
