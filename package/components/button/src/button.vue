<template>
  <div
    :class="['button', handleTypeStyle() ,disabled ? 'disabled' : '' ]"
    @click="$emit('click')"
    :disabled="disabled"
    :type="type"
  >
    <slot/>
  </div>
</template>
<script>
export default {
  name: "pj-button",
  props: {
    disabled: {
      type: Boolean,
      required: false
    },
    type: {
      type: String,
      required: false,
      default: "primary"
    }
  },
  computed: {},
  methods: {
    handleTypeStyle() {
      if (this.$props.type === "primary") {
        return "primary";
      } else if (this.$props.type === "submit") {
        return "submit";
      } else if (this.$props.type === "default") {
        return "";
      }
    }
  },
  watch: {
    disabled: function() {
      return this.$props.disabled;
    }
  }
};
</script>
<style lang="less" scoped>
.button {
  color: #333;
  border-radius: 5px;
  font-size: 12px;
  padding: 0 16px;
  line-height: 30px;
  min-width: 80px;
  height: 30px;
  background: #fff;
  text-align: center;
  box-sizing: border-box;
  border: solid 1px #dee1e5;
  cursor: pointer;
  display: inline-block;
}
.button:hover {
  box-shadow: 0px 5px 15px 0px rgba(57, 71, 95, 0.22);
}

.primary {
  background: linear-gradient(to right, #3ca8e6, #4a7ce3);
  border: none;
  color: #fff;
}
.submit {
  background: linear-gradient(90deg, #ff9344 0%, #ff6b3e 100%),
    linear-gradient(#f86f2f, #f86f2f);
  border: none;
  color: #fff;
  -webkit-appearance: none !important;
  -moz-appearance: none !important;
}
.disabled {
  width: 82px;
  color: #fff;
  background: rgb(199, 196, 206);
  border: 1px solid #d9d9d9;
  text-shadow: none;
  box-shadow: none;
  cursor: not-allowed;
}
.disabled:hover {
  box-shadow: none;
}
</style>
