
<template>
    <form action="">
        <h3>Title</h3>
        <input type="text" class="shadow-md" @input="sendInput($event, 'title')" />
        <h3>Description</h3>
        <textarea name="description" cols="30"  @input="sendInput($event, 'description')" class="resize-none shadow-md"></textarea>
        <h3>Url</h3>
        <input type="url" class="shadow-md"  @input="sendInput($event, 'url')" />
    </form>
</template>

<script>
export default {
    props: {
        resource: {
            type: Object,
            required: true,
        }
    },
    emits: ["send-input"],
    methods: {
        sendInput(e, key) {
            const newResource = this.resource;
            newResource[key] = e.target.value;

            this.$emit("send-input", newResource);
        }
    }
}
</script>

