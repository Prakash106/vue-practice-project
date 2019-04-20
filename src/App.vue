<template>
  <div class>
    <div class="row">
      <app-navbar></app-navbar>
      <div class="col-12">
        <div class="container-fluid">
          <div class="row">
            <div class="col-6">
              <app-new-quote></app-new-quote>
            </div>
            <div class="col-6">
              <app-quotes></app-quotes>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Navbar from "./components/layouts/navbar";
import NewQuote from "./components/pages/newQuote";
import Quotes from "./components/pages/quotes";

export default {
  components: {
    "app-navbar": Navbar,
    "app-new-quote": NewQuote,
    "app-quotes": Quotes
  },
  data() {
    return {
      quoteCount: 0,
      maxCount: 0
    };
  },
  created() {
    
  }
};
</script>