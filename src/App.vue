<template>
  <div>
    <spinning-wheel :segments="segments" @result="saveResult"></spinning-wheel>
    <p>
      {{ result }}
    </p>
  </div>
</template>

<script>
import SpinningWheel from "./components/SpinningWheel";

export default {
  components: {
    SpinningWheel,
  },
  data() {
    return {
      result: null,
      segments: [
        { id: 1, slice: { fill: "green" }, label: { text: "Apple" } },
        { id: 2, slice: { fill: "red" }, label: { text: "Mango" } },
        { id: 3, slice: { fill: "orange" }, label: { text: "Orange" } },
      ],
    };
  },
  methods: {
    saveResult(e) {
      this.result = e;
    },
  },
};
</script>

<style></style>
