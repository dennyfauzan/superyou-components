<template>
  <div id="chip" :style="inlineStyles" :class="type">
    <slot name="icon-left"></slot>
    <slot></slot>
    <slot name="icon-right"></slot>
  </div>
</template>

<script>
export default {
  name: "BaseChip",
  props: {
    type: {
      type: String,
      default: "default"
    },
    inlineStyles: {
      type: [Object, String]
    }
  }
};
</script>

<style lang="scss" scoped>
#chip {
  font-size: 12px;
  border-radius: 12px;
  color: #fff;
  background-color: lightgray;
  min-height: 16px;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 8px 12px;
  width: min-content;

  & > .text {
    white-space: nowrap;
    @media screen and (max-width: 600px) {
      white-space: inherit;
    }
  }

  & > .icon-left {
    margin-right: 7px;
  }

  & > .icon-right {
    margin-left: 7px;
  }

  &.outline {
    font-size: 12px;
    border: 2px solid #00aaae;
    background-color: #fff;
    border-radius: 8px;
    color: #091b30;
    text-align: center;
    padding: 4px 10px;
    transition: all 0.4s ease-in;
    &:hover {
      background-color: #00aaae;
      color: #fff;
    }
  }

  &.register {
    background-color: #0d294a;
    color: #fff;
  }
  &.in-progress {
    background-color: #f5a623;
    color: #fff;
  }
  &.investigation {
    background-color: #e2d100;
    color: #fff;
  }
  &.active {
    background-color: #06a65e;
    color: #fff;
  }
  &.rejected {
    background-color: hsl(353, 98%, 41%);
    color: #fff;
  }
  &.failed {
    background-color: hsl(353, 98%, 41%);
    color: #fff;
  }
  &.success {
    background-color: #00aaae;
    color: #fff;
  }
  &.waiting,
  &.init {
    background-color: #bebebe;
    color: #fff;
  }
}
</style>