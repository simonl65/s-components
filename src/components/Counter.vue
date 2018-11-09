<template>
    <div class="counter">
        <div :reset="reset" class="count--current"
        >{{ currentCount }}</div>
            <button class="btn col-6 btn-danger" @click="dec">-</button>
            <button class="btn col-6 btn-success" @click="inc">+</button>
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
    }
  },

  watch: {
    reset() {
      console.log("reset received");
      this.currentCount = 0;
    }
  }
};
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
