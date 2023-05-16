<template>
  <div class="flex m-5 p-4">
    <div class="w-1/3">
      <div v-for="(card, index) in chats" :data="card" :key="index">
        <ChatCard :title="chats[index]?.title" :desc="chats[index]?.description" />
      </div>
    </div>
    <div class="w-2/3">
      <ChatDescription class="fixed" />
    </div>
  </div>
</template>

<script>
import ChatCard from '../components/common/chatCard.vue'
import ChatDescription from '../components/common/chatDescription.vue'
export default {
  components: { ChatCard, ChatDescription },
  data() {
    return {
      chats: [
        { title: 'qwertyu 1', description: 'wertyuiopkajslkw' },
        { title: 'qwertyu 2', description: 'qweqwdsdfasfgsd' },
        { title: 'qwertyu 3', description: 'gfkfgjkgh' },
        { title: 'qwertyu 4', description: 'fjkghkuyikuikuikyu' },
        { title: 'qwertyu 4', description: 'uyikyuikyuikyiukt' }
      ]
    }
  }
}
</script>

<style></style>
