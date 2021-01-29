<template>
  <div>
    <spinning-wheel
      :segments="segments"
      :skip="winners"
      @result="win"
    ></spinning-wheel>
    <p>
      {{ result }}
    </p>
    <p>Previous winners: {{ winners }}</p>
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
        { id: 4, slice: { fill: "orange" }, label: { text: "Orange1" } },
        { id: 5, slice: { fill: "orange" }, label: { text: "Orange2" } },
        { id: 6, slice: { fill: "orange" }, label: { text: "Orange3" } },
        { id: 7, slice: { fill: "orange" }, label: { text: "Orange4" } },
      ],
      // segments: [...new Array(360)].map((i, index) => ({ id: index })),
      winners: [],
    };
  },
  methods: {
    win(e) {
      this.winners.push(e.id);
      this.result = e;
    },
  },
};
</script>

<style></style>
