<template>
  <div class="card shadow-sm">
   <img :src="imageUrl" class="card-img-top" alt="...">

    <div class="card-body">
      <p class="card-text">{{shortenedContent}}</p>
      <div class="d-flex justify-content-between align-items-center">
        <div class="btn-group">
          <button type="button" class="btn btn-sm btn-outline-secondary">View</button>
          <button type="button" class="btn btn-sm btn-outline-secondary">Edit</button>
        </div>
        <small class="text-muted">9 mins</small>
      </div>
    </div>
  </div>
</template>
<script>
import { toRefs, computed } from 'vue'

export default {

  props: {
    title: String,
    content: String,
    imageUrl: String
  },

  setup(props, context) {
    console.log(props.title)
    const {title, content, imageUrl} = toRefs(props)
    const shortenedContent = computed(() => {
      if(content.value?.length < 501)
        return content.value

      return content.value?.substring(0, 500) + " ..."
    })

    return {
      title,
      content,
      shortenedContent,
      imageUrl
    }
  }

}
</script>
<style scoped>
.card-text{
  text-align: justify;
}
</style>
