<template>
  <h1>Posts</h1>
  <ul class="catalog_body">
    <li :key="post.id" v-for="post in state.posts" class="container">
      <span class="title">{{ post.id }} - {{ post.title }} </span>
      <span class="body">{{ post.body }}</span>
      <span @click="removePost(post.id)" class="deleteBtn">x</span>
    </li>
  </ul>
  <form @submit="(event) => event.preventDefault()" class="addpost_form">
    <h1>Add Post</h1>
    <label>
      Title
      <input
        :value="formState.title"
        @input="(event) => (formState.title = event.target.value)"
        id="title"
    /></label>

    <label>
      Body
      <input
        :value="formState.body"
        @input="(event) => (formState.body = event.target.value)"
        id="body"
    /></label>
    <CustomButton :onClick="addPost" name="Add post" variant="standard_btn" />
  </form>
</template>

<script setup lang="ts">
import { reactive } from "vue";
import { IPost } from "@/components/MiniComponents/Catalog/catalog.interface";
import CustomButton from "@/UIKit/Button/CustomButton.vue";

const formState: { title: string; body: string } = reactive({
  title: "",
  body: "",
});

const state: { posts: IPost[] } = reactive({
  posts: [
    {
      id: 1,
      userId: 1,
      title:
        "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
      body: "quia et suscipit\\nsuscipit recusandae consequuntur expedita et cum\\nreprehenderit molestiae ut ut quas totam\\nnostrum rerum est autem sunt rem eveniet architecto",
    },
    {
      id: 2,
      userId: 1,
      title: "qui est esse",
      body: "est rerum tempore vitae\\nsequi sint nihil reprehenderit dolor beatae ea dolores neque\\nfugiat blanditiis voluptate porro vel nihil molestiae ut reiciendis\\nqui aperiam non debitis possimus qui neque nisi nulla",
    },
  ],
});
const removePost = (id: number) => {
  state.posts = state.posts.filter((post) => post.id !== id);
};
const addPost = () => {
  if (formState.title && formState.body) {
    state.posts.push({
      id: state.posts.length + 1,
      userId: 1,
      title: formState.title,
      body: formState.body,
    });
    formState.title = "";
    formState.body = "";
  } else {
    return;
  }
};
</script>

<style lang="scss" scoped>
.addpost_form {
  display: flex;
  gap: 10px;
  flex-direction: column;

  label {
    display: flex;
    align-items: center;
    color: white;
    input {
      background: transparent;
      outline: none;
      border: 1px solid #f42f54;
      border-radius: 12px;
      color: white;
      height: 32px;
      padding: 10px;
      margin-left: 2%;
    }
  }
}
h1 {
  /* Fallback: Set a background color. */
  background-color: red;

  /* Create the gradient. */
  background-image: linear-gradient(45deg, #f3ec78, #af4261);

  /* Set the background size and repeat properties. */
  background-size: 100%;
  background-repeat: repeat;

  /* Use the text as a mask for the background. */
  /* This will show the gradient as a text color rather than element bg. */
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
.catalog_body {
  display: flex;
  flex-direction: column;
  gap: 20px;
  width: 60vw;
  justify-content: center;
  align-items: center;

  .container {
    display: flex;
    align-items: center;
    border: 1px solid white;
    padding: 20px;

    .postId {
      color: blueviolet;
    }

    .title {
      color: #42b983;
      font-size: 16px;
      font-weight: 700;
      border-right: 1px solid white;
      margin-right: 20px;
    }

    .body {
      color: white;
      font-size: 14px;
      font-weight: 400;
    }

    .deleteBtn {
      color: red;
      font-size: 10px;
      cursor: pointer;
    }
  }
}
</style>
