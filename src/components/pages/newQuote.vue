<template>
	<div>
		<div class="card">
			<div class="card-body">
			<h6 class="card-subtitle mb-2 text-muted">Quote</h6>
			<div class="form-group">
				<textarea rows="4" class="form-control" v-model="quote"></textarea>
			</div>
			<div class="text-right">
				<button @click="quote=''" class="btn btn-default mr-3">Clear</button>
				<button @click="addQuote()" class="btn btn-primary">Add Quote</button>
			</div>
			</div>
		</div>
	</div>
</template>

<script>
	
	import { eventBus } from '../../main.js';

	export default {
		data: function() {
			return {
				quote: ''
			}
		},
		methods: {
			addQuote: function() {
				eventBus.$emit('quoteAdded', this.quote);
				this.quote = '';
			}
		}
	};
</script>

