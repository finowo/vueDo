<template>
	<div>
		<b-card header="To-Do List" header-tag="header">
			<b-list-group>
				<toDoItem
					v-for="item in list"
					:key="item.id"
					:toDo="item"
					@item-completed="markToDoItemAsDone"
				/>
			</b-list-group>
			<template v-slot:footer>
				<input
					type="text"
					v-model="toDoText"
					v-on:keyup.enter="addNewToDoItem()"
				/>
				<b-button
					class="float-end"
					variant="primary"
					@click="addNewToDoItem()"
					>Add</b-button
				>
			</template>
		</b-card>
	</div>
</template>

<script>
import toDoItem from "@/components/toDoItem.vue";

export default {
	name: "toDoList",
	components: {
		toDoItem
	},
	data() {
		return {
			list: [
				{ id: 1, text: "Eat the Cat", done: false },
				{ id: 2, text: "Clean the House", done: true },
				{ id: 3, text: "Hoover the bedroom", done: false }
			],
			toDoText: ""
		};
	},
	methods: {
		addNewToDoItem() {
			if (!this.toDoText) {
				alert("man default js alerts are annoying lmao");
				return;
			}
			const newId =
				Math.max.apply(
					null,
					this.list.map(x => x.id)
				) + 1;
			this.list.push({ id: newId, text: this.toDoText, done: false });
			this.toDoText = "";
		},
		markToDoItemAsDone(toDo) {
			const toDoIndex = this.list.indexOf(toDo);
			this.list[toDoIndex].done = true;
		}
	}
};
</script>

<style></style>
