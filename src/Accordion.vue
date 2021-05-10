<style scoped>
.accordion-header {
  cursor: pointer;
  display: flex;
}

.accordion-header div:first-child {
  flex-grow: 1;
  align-self: center;
}

.accordion-symbol {
  flex-grow: 0;
  padding-left: 0.5rem;
  padding-right: 0.5rem;
  align-self: center;
}

.accordion-content {
  transition: 1.5s ease all;
}
</style>

<template>
  <div class="accordion" :style="accordionStyle" :class="accordionClass">
    <div class="accordion-header" :style="headerStyle" :class="headerClass" @click="isOpened = !isOpened">
      <div>
        <slot name="header"></slot>
      </div>

      <span class="accordion-symbol" v-html="correctSymbol" :style="symbolStyle" :class="symbolClass"></span>
    </div>

    <div class="accordion-content" :style="contentStyle" :class="contentClass" v-show="isOpened">
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
    accordionClass: [String, Object],
    headerStyle: {
      type: [String, Object],
      default: "padding: .5rem;"
    },
    headerClass: [String, Object],
    symbolStyle: {
      type: [String, Object],
      default: "font-size: 1.5rem; font-weight: 700; vertical-align: middle;"
    },
    symbolClass: [String, Object],
    contentStyle: {
      type: [String, Object],
      default: "width: 98%; margin: auto; padding: .5rem;"
    },
    contentClass: [String, Object],
    symbolOpened: {
      type: String,
      default: "&or;"
    },
    symbolClosed: {
      type: String,
      default: "&gt;"
    },
    opened: Boolean
  },
  data() {
    return {
      isOpened: this.opened
    };
  },
  computed: {
    correctSymbol() {
      return this.isOpened ? this.symbolOpened : this.symbolClosed;
    }
  }
};
</script>
