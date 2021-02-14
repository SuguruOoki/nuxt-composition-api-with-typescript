<template>
<div>
  <p>{{ state.messageTwo }}</p>
  <div v-for="item in items" :key="item.id" class="flex">
    <p>{{ item.title }}</p>
    <p>{{ item.description }}</p>
    <p>{{ item.isFinished }}</p>
  </div>
</div>
</template>

<script lang="ts">
import { defineComponent, ref, reactive } from '@vue/composition-api'

type ToDoItem = {
  title: string
  description: string
  isFinished: boolean
}

export default defineComponent({
  setup() {
    const items = ref<ToDoItem[]>([
      {
        title: 'Welcome',
        description: 'descriptionTest1',
        isFinished: false
      },
      {
        title: 'Welcome2',
        description: 'descriptionTest2',
        isFinished: true
      },
      {
        title: 'Welcome3',
        description: 'descriptionTest3',
        isFinished: true
      },
    ])
    const state = reactive<{ messageOne: string }>({
      messageOne: "Hello"
    });
    const messageTwo = ref<string>("こんにちは");

    return {
      state,
      messageTwo,
      items
    };
  },
})
</script>
<style>
.NuxtLogo {
  animation: 1s appear;
  margin: auto;
}

@keyframes appear {
  0% {
    opacity: 0;
  }
}
</style>
