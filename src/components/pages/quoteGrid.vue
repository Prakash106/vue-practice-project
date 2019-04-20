<template>
  <div class="col-12 m-2">
    <div class="card">
      <div class="card-body">
        <p class="card-title">
          <slot name="quote"></slot>
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
	.card:hover {
		background: red;
		cursor: pointer;
	}
</style>