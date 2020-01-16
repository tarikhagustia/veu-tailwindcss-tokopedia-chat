<template>
  <div class="clearfix">
    <div
    class="rounded-lg py-3 px-2 text-gray-600 my-2 clearfix text-xs" :class="{'float-right bg-gray-300': me, 'float-left border': !me}">
    {{msg}}
    <span class="ml-2 text-xs text-gray-500">{{date}}</span>
  </div>
  </div>
</template>

<script>
export default {
  props: {
    me: {
      type: Boolean,
      default: true
    },
    msg: {
      type: String,
      default: 'Message here',
      required: true
    },
    date: {
      type: String,
      default: '01:00',
      required: true
    }
  }
}
</script>
