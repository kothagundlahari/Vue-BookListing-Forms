<template>
  <form v-on:submit.prevent="bookSubmit(bookData)" class="" action="#" method="post">
    <input v-model="bookData.bookTitle" type="text" name="title" value="" placeholder="Book Title">
    <input v-model="bookData.bookAuthor" type="text" name="author" value="" placeholder="Book Author">
    <button type="submit" name="button">Add Book</button>
    <div>
      <label for="finishedReading">Finished Reading<input type="checkbox"  v-model="bookData.finishedReading" id="finishedReading"></label>
    </div>
    <div>
      <label for="borrowed">Borrowed<input type="radio" v-model="bookData.ownership" id="borrowed"></label>
      <label for="bought">Bought<input type="radio" v-model="bookData.ownership" id="bought"></label>
    </div>
  </form>
</template>

<script>
  export default {
    name: "BookForm",
    props: ["books"],
    data() {
      return {
        bookData: {
          bookTitle: "",
          bookAuthor: "",
          finishedReading: false,
          ownership: []
        }

      };
    },
    methods: {
      bookSubmit(bookData) {
        this.$emit("addBook", bookData);
      }
    }
  };
</script>

<style>
</style>
