<script setup>
defineProps({
    newTask: Object,
    displayCreateModal: Boolean,
});

const emit = defineEmits(["createTask", "hideCreateModal"]);

function createTask() {
    emit("createTask");
}

function hideCreateModal() {
    emit("hideCreateModal");
}
</script>

<template>
    <h3>CREATE TASK MODAL</h3>

    <div
        v-if="displayCreateModal"
        class="absolute top-0 left-0 w-full h-full bg-slate-900 flex flex-col items-center justify-center"
    >
        <button
            class="bg-red-600 py-2 px-4 rounded-md font-bold text-md hover:bg-red-700"
            @click="hideCreateModal"
        >
            Exit
        </button>
        <form
            @submit.prevent="createTask"
            class="bg-slate-700 flex flex-col p-8 rounded-md gap-4"
        >
            <div class="flex flex-col gap-2">
                <label for="">Name</label>
                <input
                    v-model="newTask.name"
                    type="text"
                    placeholder="New Task"
                />
            </div>
            <div class="flex gap-2">
                <label for="">Completed</label>
                <input
                    v-model="newTask.completed"
                    type="checkbox"
                    :checked="newTask.completed.value"
                />
            </div>
            <div class="flex flex-row">
                <button
                    class="bg-slate-600 w-full py-2 px-4 rounded-md font-bold text-md hover:bg-teal-600 disabled:bg-slate-700 disabled:text-slate-500 disabled:cursor-not-allowed"
                    type="submit"
                >
                    SUBMIT
                </button>
            </div>
        </form>
    </div>
</template>
