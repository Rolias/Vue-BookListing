<template>
  <div>
    <h1>{{title}}</h1>
    <ul>
      <book-item v-for="book in books" v-bind:key="book.title" :book="book"></book-item>
      <book-form @addBook="appendBook"></book-form>
    </ul>
  </div>
</template>

<script>
import BookItem from "./BookItem";
import BookForm from "./BookForm";
export default {
  name: "BookList",
  components: { BookItem, BookForm },
  data() {
    return {
      title: "All Books",
      books: [
        { title: "Dune", author: "Frank Herbert" },
        { title: "American Gods", author: "Neil Gaiman" },
        { title: "The Magicians", author: "Lev Grossman" },
        { title: "14", author: "Peter Clines" }
      ]
    };
  },
  methods: {
    appendBook(bookTitle, bookAuthor) {
      this.books.push({ title: bookTitle, author: bookAuthor });
    }
  }
};
</script>

<style lang="css">
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
</style>