<template>
  <div>{{ count }} {{ object.foo }}</div>
</template>

<script>
import { ref, reactive, watchEffect } from "vue";

export default {
  props: {
    name: {
      type: String,
      default: "007"
    }
  },
  setup(props, context) {
    console.log(props)
    console.log(context)

    watchEffect(() => {
      console.log(`name is:` + props.name)
    })

    const count = ref(0)
    const object = reactive({ foo: "bar" })

    // 暴露给模板
    return {
      count,
      object
    }
  }
};
</script>
