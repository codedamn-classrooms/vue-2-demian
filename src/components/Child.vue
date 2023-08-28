<template>
	<div id="app">
		<div
			v-if="parentmessage"
			class="card-text alert alert-warning"
			v-html="parentmessage"
		></div>
		<button v-if="parentmessage" @click="ok" class="btn btn-success">
			Ok
		</button>
	</div>
</template>

<script>
export default {
	name: "Child",
	props: {
		parentmessage: String,
	},
	components: {},
	methods: {
		ok() {
			this.$emit("finished");
		},
	},
};
</script>
