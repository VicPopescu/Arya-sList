<template>
	<div class="aryas-list container">
		<add-item-form v-on:save="addNewitem"></add-item-form>
		<ul class="collection mb20">
			<li class="collection-item valign-wrapper" v-for="item in list" :key="item.Id">
				<div class="left-side valign-wrapper">
					<span class="item-place mr20">{{ item.Place }}</span>
					<img :src="item.ProfileUrl || defaultImgUrl">
					<span class="item-name">{{ item.Name || defaultName }}</span>
				</div>
				<button class="waves-effect waves-light btn" @click="removeItem(item)">Remove</button>
			</li>
		</ul>
	</div>
</template>

<script>
import AddItemForm from "./AddItemForm";
export default {
	name: "to-kill-list",
	props: {
		list: Array
	},
	components: {
		AddItemForm
	},
	data() {
		return {
			defaultImgUrl:
				"https://www.wwf.org.uk/sites/default/files/styles/content_slide_image/public/2016-10/Original_WW22776.jpg?h=66ac411f&itok=2Fh0YA7h",
			defaultName: "The no name penguin"
		};
	},
	methods: {
		removeItem(item) {
			this.$emit("delete", item);
		},
		addNewitem(item) {
			this.$emit("save", item);
		}
	}
};
</script>
<style lang="scss" scoped>
* {
	text-align: left;
}
.container {
	padding-bottom: 60px;
}
.collection-item {
	height: 80px;
	display: flex;
	justify-content: space-between;
	position: relative;
}
.left-side {
	height: 100%;
	.item-place {
		font-size: 18px;
	}
	.item-name {
		margin-left: 10px;
		font-size: 20px;
	}
	img {
		height: 100%;
		width: 80px;
		object-fit: cover;
	}
}
</style>
