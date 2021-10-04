<template>
	<b-list-group-item>
		<span v-if="toDo.done" class="done">{{ toDo.text }}</span>
		<span v-else>{{ toDo.text }}</span>
		<span v-if="toDo.done" class="float-end">&#128077;</span>
		<b-button
			v-else
			class="float-end"
			v-model="markAsDone"
			pill
			variant="outline-success"
			@click="markToDoItemAsDone()"
			>&#10003;</b-button
		>
	</b-list-group-item>
</template>

<script>
export default {
	name: "toDoItem",
	props: {
		toDo: {
			type: Object,
			required: true
		}
	},
	methods: {
		markToDoItemAsDone() {
			this.$emit("item-completed", this.toDo);
		}
	}
};
</script>

<style>
.done {
	text-decoration: line-through;
}
</style>
