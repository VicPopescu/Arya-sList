<template>
	<section>
		<h1>Arya's List</h1>
		<to-kill-list :list="sortedData" v-on:delete="removeItem" v-on:save="saveItem"></to-kill-list>
	</section>
</template>
<script>
import ToKillList from "@/components/ToKillList.vue";
import TheListData from "@/data/aryasList.js";

export default {
	name: "AryasList",
	data() {
		return {
			toKillList: []
		};
	},
	mounted: function() {
		this.toKillList = TheListData;
	},
	computed: {
		sortedData() {
			return this.toKillList.sort((a, b) => a.Place - b.Place);
		}
	},
	components: {
		ToKillList
	},
	methods: {
		/**
		 * Remove item from list
		 */
		removeItem(item) {
			this.toKillList.splice(this.toKillList.indexOf(item), 1);
			this.sortList(this.toKillList);
		},
		/**
		 * Save item to list
		 */
		saveItem(item) {
			item.Id = this.toKillList.length + 1;
			if (!item.Place) {
				item.Place = this.toKillList.length + 1;
			}
			this.toKillList.push(item);
			this.sortList(this.toKillList);
		},
		/**
		 * Sort list by Place in list
		 */
		sortList(list) {
			list.map((item, index) => (item.Place = index + 1));
		}
	}
};
</script>
