<template>
  <div class="row">
    <div class="col-12">
      <div class="col-12">
        <app-progress-bar :quotesCount="quotes.length" :maxCount="maxQuoteCount"></app-progress-bar>
      </div>
    </div>
    <app-quote v-for="(quote, index) in quotes" :key="index" @click.native="deleteQuote(index)">
      <p slot="quote">{{quote}}</p>
    </app-quote>
  </div>
</template>

<script>
import Quote from "./quoteGrid.vue";
import { eventBus } from "../../main.js";
import ProgressBar from "../layouts/progress";

export default {
  components: {
    "app-quote": Quote,
    "app-progress-bar": ProgressBar
  },
  data: function() {
    return {
      quotes: [],
      maxQuoteCount: 10
    };
  },
  methods: {
    deleteQuote: function(index) {
      this.quotes.splice(index, 1);
      eventBus.$emit("deleteQuote", index);
    }
  },
  created() {
    eventBus.$on("quoteAdded", data => {
      if (this.quotes.length == 10) {
			alert("It's around 10 quotes");
      } else {
      	this.quotes.push(data);
		}
    });
  }
};
</script>

