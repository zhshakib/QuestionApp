<template>
  <div class="bg-white p-12 rounded-lg shadow-lg w-full mt-8">
    <div>
      <p class="text-2xl font-bold">{{ title }}</p>
      <label for="a" class=" block mt-4 border border-gray-300 rounded-lg py-2 px-6 text-lg">
        <input v-for="choice, key in choices" :key="key" type="radio" class=" hidden"> {{choice}}
      </label>

    </div>
  </div>
</template>

<script>
;
export default {
  name: 'Question',
  props: ['title', 'choices']
  
}
</script>
