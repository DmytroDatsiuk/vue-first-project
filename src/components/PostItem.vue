<template>
  <div class="post">
    <div>
      <div>{{ post.id }}</div>
      <div>Кількість лайків - {{ $store.getters.doubleLikes }}</div>
      <div><strong>Назва: </strong>{{ post.title }}</div>
      <div><strong>Опис: </strong>{{ post.body }}</div>
    </div>
    <div class="post__btns">
      <my-button
        style="margin-right: 10px"
        @click="$router.push(`/posts/${post.id}`)"
        >Відкрити</my-button
      >
      <my-button style="color: red" @click="$emit('remove', post)"
        >Видалити</my-button
      >
    </div>
  </div>
</template>

<script>
export default {
  props: {
    post: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped>
.post {
  padding: 15px;
  border: 2px solid skyblue;
  border-radius: 5px;
  margin-top: 15px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.post__btns {
  display: flex;
  /* align-items: center; */
}
</style>
