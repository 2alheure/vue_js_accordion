
<style>
.accordion-content {
  transition: 1.5s ease all;
}
</style>

<template>
  <div class="accordion" :style="accordionStyle">
    <div
      class="accordion-header cursor-pointer flex"
      :style="titleStyle"
      @click="opened = !opened"
    >
      <div class="transparent flex-grow">
        <slot name="header"></slot>
      </div>

      <span
        class="transparent flex-grow-0 px-2"
        v-html="correctSymbol"
		:style="symbolStyle"
      ></span>
    </div>

    <div class="accordion-content" :style="contentStyle" v-show="opened">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: "accordion",
  props: {
	accordionStyle: {
	type: [String, Object],
	default: "text-align: left; background-color: inherit; color: inherit;"
	},
    title: String,
    titleStyle: {
      type: [String, Object],
      default: "padding: .5rem;"
    },
    symbolStyle: {
      type: [String, Object],
      default: "font-size: 1.25rem; font-weight: 700; vertical-align: middle;"
    },
    contentStyle: {
      type: [String, Object],
      default: "width: 98%; margin: auto; padding: .5rem;"
    },
    whenOpened: {
      type: String,
      default: "&or;"
    },
    whenClosed: {
      type: String,
      default: "&gt;"
    }
  },
  data() {
    return {
      opened: true
    };
  },
  computed: {
    correctSymbol() {
      return this.opened ? this.whenOpened : this.whenClosed;
    }
  }
};
</script>			