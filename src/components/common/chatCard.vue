<template>
  <v-card theme="dark" class="m-2">
    <div class="flex">
      <div class="w-1/3">
        <img :src="img" class="flex justify-around m-4 rounded-full w-20 h-20" alt="avatar" />
      </div>
      <div class="my-4">
        <p class="text-lg">{{ title }}</p>
        <p class="text-sm">{{ desc }}</p>
      </div>
    </div>
  </v-card>
</template>

<script>
export default {
  props: {
    img: { type: String, default: 'https://picsum.photos/200/300' },
    title: { type: String, default: 'Title of contact' },
    des: { type: String, default: 'Desc of message' }
  }
}
</script>

<style></style>
