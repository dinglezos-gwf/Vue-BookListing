<template>
<div>
  <book-form @addBook='appendBook'></book-form>
  <h1>{{title}}</h1>
  <ul>
    <book-item v-for="book in books" :book="book" class="book-item"></book-item>
  </ul>
</div>
</template>

<script>
import BookItem from "./BookItem";
import BookForm from "./BookForm";

export default {
  name : "BookItem.vue",
  components: {
    BookItem,
    BookForm
  },
  data() {
    return {
      title : "All Books"
    }, {
      books:
        [
          {title: 'Self-Reliance', author: 'Ralph Waldo Emerson'},
          {title: 'American Gods', author: 'Neil Gaiman'},
          {title: 'Amusing Ourselves to Death', author: 'Neil Postman'}
        ]
    }
  },
  methods: {
    appendBook: function(bookTitle,bookAuthor) {
      this.books.push({ title: bookTitle, author: bookAuthor })
    }
  },
}
</script>

<style scoped>
h1,h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding:0;
}

</style>
