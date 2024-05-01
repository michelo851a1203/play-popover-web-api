<script setup lang="ts">
import { shallowRef } from 'vue';
const currentID = shallowRef<string>("cooll");
const isOpenModal = shallowRef<boolean>(false)
const trigger = (event: ToggleEvent): void => {
  isOpenModal.value = event.newState === "open";
};

const coolREsult = (event: ToggleEvent): void => {
  console.log(event);
};

</script>

<template>
  <button px-3 py-2 rounded-xl bg-blue-400 :popovertarget="currentID">click</button>
  {{ isOpenModal }}
  <section @toggle="coolREsult" @beforetoggle="trigger" popover :id="currentID" bg-gray-400 rounded-md px-10 py-8 box-border  w="2/3" h="60" shadow-lg>
    <button @click="console.log('hello')">click</button>
    cool
  </section>
</template>
