<template>
  <div class="relative">
    <div class="h-64 p-2 overflow-y-auto p-10" id="chat">
      <p class="mx-auto text-center text-xs text-gray-500 mb-2">1 Jan 2020</p>
      <ChatText
        v-for="(item, key) in chats"
        :key="key"
        :msg="item.message"
        :me="item.me"
        :date="item.date"
      />
    </div>
    <div
      class="border absolute mt-1 flex p-2 inset-x-0 bottom-0 h-12 bg-white"
      style="bottom: -24px"
    >
      <input
        class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-500 leading-tight focus:outline-none focus:shadow-outline text-xs"
        id="username"
        type="text"
        v-model="msg"
        placeholder="Cari Penjual "
      />
      <button
        class="bg-green-500 rounded px-2 text-xs text-gray-100 hover:none mx-2"
        @click="sendMessage"
      >Kirim</button>
    </div>
  </div>
</template>

<script>
import ChatText from './ChatText'

const chats = [
  { me: true, message: 'Hi gan, ga jawab PKI!', date: '01:01pm' },
  { me: false, message: 'Iya gmna gan :)', date: '01:01pm' },
  { me: true, message: 'Jual spatu ga?', date: '01:01pm' },
  { me: false, message: 'Silahkan kak ada sepatu Bakiak import dari zimbabwe :)', date: '01:01pm' },
  { me: true, message: 'Maaf kak saya sudah punya pacar :)', date: '01:01pm' },
  { me: false, message: "Gini banget jualan :')", date: '01:01pm' }
]

export default {
  components: {
    ChatText
  },
  data () {
    return {
      chats,
      msg: ''
    }
  },
  mounted () {
    let container = document.querySelector('#chat')
    container.scrollTop = (container.scrollHeight + 100)
    console.log(container.scrollTop)
  },
  methods: {
    sendMessage () {
      let container = document.querySelector('#chat')
      container.scrollTop = (container.scrollHeight + 100)
      this.chats.push({
        me: true,
        message: this.msg,
        date: '02:00pm'
      })
      this.msg = ''
    }
  }
}
</script>
