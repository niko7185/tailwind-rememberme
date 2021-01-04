
<template>
    <form @submit.prevent="sendInput" class="relative">
        <label for="title" class="mr-1">Title:</label>
        <input id="title" type="text" name="title" class="shadow-md mb-4" />
        <label for="description" class="block">Description:</label>
        <textarea id="description" name="description" rows="4" cols="40" class="resize-none shadow-md w-full mb-4"></textarea>
        <label for="url" class="mr-1">Url:</label>
        <input id="url" type="url" name="url" class="shadow-md " />
        <blue-button class="absolute right-1">Submit</blue-button>
    </form>
</template>

<script>
import BlueButton from './Buttons/BlueButton.vue';

export default {
    components: {
        BlueButton,
    },
    emits: ["send-input"],
    methods: {
        sendInput(e) {
            const newResource = {
                title: e.currentTarget.title.value,
                description: e.currentTarget.description.value,
                url: e.currentTarget.url.value,
            };

            this.$emit("send-input", newResource);
        }
    }
}
</script>

