<template>
  <button @click="age++">年龄+1</button>
  {{name}}
  {{word.i}}
</template>

<script>

import { watch, reactive,toRefs,toRef } from "vue";
export default {
  name: 'App',
  setup() {
    const person = reactive({
      name: 'chen',
      age: 23,
      word: {
        i: 'hello',
        j: 'world'
      }
    });
    watch(person, (n, o) => {
      console.log(toRefs(person));
    })

    return {
      ...toRefs(person)
    }

  }


}
</script>
