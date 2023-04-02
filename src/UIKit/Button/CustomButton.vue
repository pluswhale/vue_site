<template>
  <button @click="onClick" :class="variant">
    {{ name }}
  </button>
</template>

<script>
export default {
  methods: {
    setClassName() {
      switch (variant) {
        case "standard":
          return "standard_btn";
        case "non-bg":
          return "non_bg_btn";
        default:
          return "standard";
      }
    },
  },
  props: {
    variant: {
      type: String,
      required: false,
    },
    name: {
      type: String,
      required: true,
    },
    onClick: {
      type: Function,
      required: false,
    },
  },
};
</script>

<style lang="scss" scoped>
.standard_btn {
  border-radius: 44px;
  background-color: #f42f54;
  color: white;
  border: none;
  min-width: 120px;
  font-size: 16px;
  padding: 12px 30px;
  line-height: 25px;
  text-transform: uppercase;
  text-align: center;
  cursor: pointer;
  white-space: nowrap;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  height: 66px;
  transition: all 0.3s;
  &:hover {
    background-color: transparent;
    border: 1px solid #f42f54;
  }
}

.non_bg_btn {
  border-radius: 44px;
  background-color: transparent;
  color: white;
  border: 2px solid #f42f54;
  min-width: 120px;
  font-size: 16px;
  padding: 12px 30px;
  line-height: 25px;
  text-transform: uppercase;
  text-align: center;
  cursor: pointer;
  white-space: nowrap;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  height: 45px;

  transition: all 0.4s;

  &:hover {
    background-color: #f42f54;
  }
}
</style>
