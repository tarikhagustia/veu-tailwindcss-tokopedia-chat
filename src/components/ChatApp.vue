<template>
  <div class="lg:w-1/2 my-10 ml-auto mr-auto rounded-lg bg-white shadow-2xl">
    <div class="flex mb-4">
      <div class="w-1/3 border-r-2">
        <div class="border-b-2 p-2 shadow-bottom">
          <h2 class="font-bold mb-2">Chat</h2>
          <input
            class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
            id="username"
            type="text"
            v-model="filter"
            placeholder="Cari Penjual "
          />
        </div>
        <div class="p-1 overflow-y-auto max-h-full h-64">
          <div class="shop flex p-2 rounded-full mb-2 cursor-pointer" :class="{'bg-green-200': item.selected}" v-for="(item, key) in filteredPeoples" :key="key" @click="onSelected(item)">
            <img class="h-10 w-10 mr-2 my-auto rounded-full mx-0" :src="item.logo" />
            <div>
              <h2 class="text-sm text-gray-600">{{item.name}}</h2>
              <span class="text-xs text-green-500 bg-green-300 p-1 rounded color:green">{{item.label}}</span>
            </div>
          </div>
        </div>
      </div>
      <div class="w-2/3 h-12">
        <ChatNavVue :people="selectedPeople"/>
        <ChatBox v-if="displayChatBox"/>
        <ChatEmptyBox v-if="!displayChatBox"/>
      </div>
    </div>
  </div>
</template>

<script>
import ChatNavVue from './ChatNav.vue'
import ChatBox from './ChatBox.vue'
import ChatEmptyBox from './ChatEmptyBox.vue'

const peoples = [
  { name: 'Dinamo Shop', logo: 'https://i.pravatar.cc/100', label: 'Penjual', selected: false },
  { name: 'Almira Shop', logo: 'https://i.pravatar.cc/100', label: 'Penjual', selected: false },
  { name: 'Anjay Shop', logo: 'https://i.pravatar.cc/100', label: 'Penjual', selected: false },
  { name: 'Lorem Shop', logo: 'https://i.pravatar.cc/100', label: 'Penjual', selected: false },
  { name: 'Lorem Shop', logo: 'https://i.pravatar.cc/100', label: 'Penjual', selected: false },
  { name: 'Lorem Shop', logo: 'https://i.pravatar.cc/100', label: 'Penjual', selected: false },
  { name: 'Lorem Shop', logo: 'https://i.pravatar.cc/100', label: 'Penjual', selected: false },
  { name: 'Lorem Shop', logo: 'https://i.pravatar.cc/100', label: 'Penjual', selected: false },
  { name: 'Lorem Shop', logo: 'https://i.pravatar.cc/100', label: 'Penjual', selected: false },
  { name: 'Lorem Shop', logo: 'https://i.pravatar.cc/100', label: 'Penjual', selected: false },
  { name: 'Lorem Shop', logo: 'https://i.pravatar.cc/100', label: 'Penjual', selected: false },
  { name: 'Lorem Shop', logo: 'https://i.pravatar.cc/100', label: 'Penjual', selected: false },
  { name: 'Lorem Shop', logo: 'https://i.pravatar.cc/100', label: 'Penjual', selected: false },
  { name: 'Lorem Shop', logo: 'https://i.pravatar.cc/100', label: 'Penjual', selected: false },
  { name: 'Lorem Shop', logo: 'https://i.pravatar.cc/100', label: 'Penjual', selected: false },
  { name: 'Lorem Shop', logo: 'https://i.pravatar.cc/100', label: 'Penjual', selected: false },
  { name: 'Dinamo Shop', logo: 'https://i.pravatar.cc/100', label: 'Penjual' }
]
export default {
  components: {
    ChatNavVue,
    ChatBox,
    ChatEmptyBox
  },
  data () {
    return {
      filter: '',
      peoples,
      selectedPeople: {},
      displayChatBox: false
    }
  },
  computed: {
    filteredPeoples () {
      return this.peoples.filter(value => {
        return value.name.toLowerCase().includes(this.filter.toLowerCase())
      })
    }
  },
  methods: {
    onSelected (item) {
      this.peoples.forEach(val => {
        val.selected = false
      })
      item.selected = true
      this.selectedPeople = item
      this.displayChatBox = true
    }
  }
}
</script>
