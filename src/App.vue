<template>
  <div class="container">
    <app-new-quote @quoteAdded="addQuote"></app-new-quote>
    <app-quote-grid
      :quotes="quotes"
      @quoteDeleted="deleteQuote"
    ></app-quote-grid>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">Info: Click on a Quote to delete it</div>
      </div>
    </div>
  </div>
</template>

<script>
import QuoteGrid from "./components/QuoteGrid.vue";
import NewQuote from "./components/NewQuote.vue";
export default {
  data: () => {
    return {
      quotes: ["Just a Quote"],
      maxQuotes: 10
    };
  },
  components: {
    appQuoteGrid: QuoteGrid,
    appNewQuote: NewQuote
  },
  methods: {
    addQuote(quote) {
      this.quotes.push(quote);
    },
    deleteQuote(index) {
      this.quotes.splice(index, 1);
    }
  }
};
</script>

<style></style>
