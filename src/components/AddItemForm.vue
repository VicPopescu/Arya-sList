<template>
	<div class="row">
		<h4>Add new target</h4>
		<form class="col s12 mb20" v-on:submit.prevent="addNewitem">
			<div class="row">
				<div class="input-field col s6">
					<input v-model="form.Name" id="first_name" type="text" class="validate">
					<label for="first_name">Full Name</label>
				</div>
				<div class="input-field col s6">
					<input v-model="form.ProfileUrl" id="last_name" type="text" class="validate">
					<label for="last_name">Profile Image Url</label>
				</div>
			</div>
			<div class="row">
				<div class="input-field col s6">
					<input v-model="form.Place" id="place" type="number" class="validate">
					<label for="place">Place in list</label>
				</div>
			</div>
			<button class="waves-effect waves-light btn" type="submit">Save changes</button>
		</form>
	</div>
</template>

<script>
export default {
	name: "add-item-form",
	data() {
		return {
			form: {
				Id: "",
				Name: "",
				ProfileUrl: "",
				Place: ""
			}
		};
	},
	methods: {
		addNewitem() {
			this.$emit("save", this.form);
			this.form = {
				Id: "",
				Name: "",
				ProfileUrl: "",
				Place: ""
			};
		}
	}
};
</script>

