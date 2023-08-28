<template>
	<div id="app">
		<img alt="Vue logo" src="./assets/logo.png" />

		<button @click="sendMessage" class="btn btn-info">
			Send Child A Message
		</button>
		<Child :parentmessage="parentmessage" @finished="finished"></Child>
	</div>
</template>

<script>
import Child from "./components/Child.vue";

export default {
	name: "App",
	components: {
		Child,
	},
	data: function () {
		return {
			parentmessage: "",
		};
	},
	methods: {
		sendMessage() {
			this.parentmessage = "<b>Message From Parent:</b> Do Your Homework";
		},
		finished() {
			this.parentmessage = "";
		},
	},
};
</script>

<style>
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
	margin-top: 60px;
}
</style>
