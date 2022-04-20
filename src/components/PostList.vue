<template>
  <section class="card-grid">
    <PostListItem :content="content" :title="name" :imageUrl="coverUrl"></PostListItem>
    <PostListItem :content="content" :title="name" :imageUrl="coverUrl"></PostListItem>
    <PostListItem :content="content" :title="name" :imageUrl="coverUrl"></PostListItem>
    <PostListItem :content="content" :title="name" :imageUrl="coverUrl"></PostListItem>
  </section>
</template>
<style>
.card-grid{
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1em;
  padding: 1em;
}
</style>
<script>

import PostListItem from './PostListItem.vue'

const name ='post name'
const content = "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum."
const coverUrl = 'https://startbootstrap.github.io/startbootstrap-clean-blog/assets/img/home-bg.jpg'

export default {
  components: {
    PostListItem
  },
  setup(props) {
    
    return {
      name,
      content,
      coverUrl
    }
  }
}
</script>