<template>
  <el-select v-model="text"
             :size="size"
             :multiple="multiple"
             :filterable="filterable"
             :readonly="readonly"
             collapse-tags
             :clearable="disabled?false:clearable"
             :placeholder="placeholder"
             @click.native="handleClick"
             :multiple-limit="limit"
             :disabled="disabled">
    <el-option v-for="(item,index) in dic"
               :key="index"
               :disabled="item[disabledKey]"
               :label="item[labelKey]"
               :value="item[valueKey]"></el-option>
  </el-select>
</template>

<script>
import create from "core/create";
import props from "../../core/common/props.js";
import event from "../../core/common/event.js";
export default create({
  name: "select",
  mixins: [props(), event()],
  data() {
    return {};
  },
  props: {
    value: {},
    limit: {
      type: Number,
      default: 99
    },
    filterable: {
      type: Boolean,
      default: false
    }
  },
  watch: {
    text: {
      handler() {
        this.handleChange(this.text);
      },
      immediate: true
    }
  },
  created() {},
  mounted() {},
  methods: {}
});
</script>