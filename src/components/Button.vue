<template>
  <button class="k-btn" :style="styles">
    <span
      class="k-progress__bar"
      :style="loadStyles"
      :class="loading ? 'loading' : null"
    />
    <span class="k-button__text"> {{ title }}</span>
  </button>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";

@Options({
  computed: {
    loadStyles() {
      return {
        transitionDuration: this.loadingTime,
        background: this.bgProgress,
        borderRadius: this.borderRadius,
      };
    },
    styles() {
      return {
        "--background-hover": this.hoverBackground,
        "--background": this.background,
        "--text-color": this.textColor,
        "--text-hover-color": this.textHoverColor,
        fontSize: this.textSize,
        borderRadius: this.borderRadius,
      };
    },
  },
  props: {
    title: {
      type: String,
      default: "Button",
    },
    loading: {
      type: Boolean,
      default: false,
    },
    loadingTime: {
      type: Number,
      default: 1,
    },
    bgProgress: {
      type: String,
      default: "#5c95ff",
    },
    hoverBackground: {
      type: String,
      default: "#3483facc",
    },
    textColor: {
      type: String,
      default: "#FFF",
    },
    textHoverColor: {
      type: String,
      default: "#FFF",
    },
    background: {
      type: String,
      default: "#3483fa",
    },
    fontSize: {
      type: String,
      default: "16px",
    },
    borderRadius: {
      type: String,
      default: "4px",
    },
  },
})
export default class HelloWorld extends Vue {
  title!: string;
  loading!: boolean;
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.k-btn {
  all: unset;
  position: relative;
  background: var(--background);
  color: var(--text-color);
  font-weight: 600;
  padding-top: 16px;
  padding-bottom: 16px;
  border-radius: 4px;
  width: 250px;
  cursor: pointer;
}
.k-button__text {
  position: relative;
  padding-left: 32px;
  padding-right: 32px;
}
.k-progress__bar {
  top: 0;
  left: 0;
  transition-property: all;
  transition-duration: 1s;
  transition-timing-function: ease;
  transition-delay: 0s;
  position: absolute;
  width: 0;
  height: 100%;
}
.loading {
  width: 100%;
}
.k-btn:hover {
  background-color: var(--background-hover);
  color: var(--text-hover-color);
}
</style>
