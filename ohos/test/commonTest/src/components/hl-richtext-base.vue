<template>
  <BaseSameLayer
    :hosSameLayerArgs="hosSameLayerArgs"
    embedType="richtext"
  ></BaseSameLayer>
</template>

<script>
import BaseSameLayer from "./baseSameLayer.vue";

export default {
  name: "HlRichtext",
  components: {
    BaseSameLayer,
  },
  props: {
    hosUniqueProps: {
      type: Object,
      required: true,
    },
    text: {
      type: String,
      required: true,
    },
  },
  computed: {
    hosSameLayerArgs() {
      return {
        ...this.hosUniqueProps, // 鸿蒙原生组件独有属性
        text: this.text, // 多端支持公共属性
      };
    },
  },
  methods: {
    // 自定义拓展其它逻辑
  },
};
</script>
