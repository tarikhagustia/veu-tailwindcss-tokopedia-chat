<template>
  <div class="shadow h-16 p-2">
    <div class="flex" v-if="Object.keys(people).length > 0">
      <img class="h-10 w-10 mr-2 my-auto rounded-full mx-0" :src="people.logo" />
      <div class="">
        <h2 class="text-gray-700">{{people.name}} <span class="inline bg-green-200 text-green-500 text-sm p-1 rounded-lg">{{people.label}}</span></h2>
        <small class="text-gray-500">Terakhir online 6 menit yang lalu</small>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    people: {
      type: Object,
      default: () => {
        return {}
      }
    }
  }
}
</script>
