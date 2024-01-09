<script setup>
defineProps({
    newTask: Object,
});

const emit = defineEmits(["createTask"]);

function createTask() {
    console.log("SENDING EMIT");
    emit("createTask");
}
</script>

<template>
    <!-- <form
        @submit.prevent="createTask"
        class="bg-slate-800 flex flex-col gap-6 px-4 py-4 border border-slate-700 rounded-md text-slate-300"
    >
        <div>
            <h3 class="text-xl">Create Task</h3>
        </div>
        <div class="flex flex-col gap-2">
            <label for="" class="">Task name</label>
            <input
                v-model="newTask.name.value"
                type="text"
                class="bg-slate-700"
                placeholder="Example name"
            />
        </div>
        <div class="flex flex-row-reverse justify-end gap-2 items-center">
            <label for="">Completed</label>
            <input
                type="checkbox"
                v-model="newTask.completed"
                :checked="newTask.completed.value"
            />
        </div>
        <button
            :disabled="newTask.name.value.length ? 0 : !0"
            class="bg-slate-600 py-2 rounded-md font-bold text-md hover:bg-teal-600 disabled:bg-slate-700 disabled:text-slate-500 disabled:cursor-not-allowed"
        >
            Create task
        </button>
    </form> -->
    <h3>CREATE TASK MODAL</h3>

    <div
        class="absolute top-0 left-0 w-full h-full bg-slate-900 flex flex-col items-center justify-center"
    >
        <form
            @submit.prevent="createTask"
            class="bg-slate-700 flex flex-col p-4"
        >
            <input v-model="newTask.name" type="text" />
            <input
                v-model="newTask.completed"
                type="checkbox"
                :checked="newTask.completed"
            />
            <button
                class="bg-slate-600 py-2 px-4 rounded-md font-bold text-md hover:bg-teal-600 disabled:bg-slate-700 disabled:text-slate-500 disabled:cursor-not-allowed"
            >
                SUBMIT
            </button>
        </form>
    </div>
</template>
