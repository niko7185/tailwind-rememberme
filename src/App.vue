<template>
  <main>
    <article class="mx-auto max-w-lg">
      <section class="flex justify-between py-8 dark:text-white">
        <h1 class="opacity-60">REMEMBER ME</h1>
        <blue-button @click="showForm = true"><span class="font-bold">+</span> Add</blue-button>
      </section>
      <section v-if="showForm" class="rounded-md my-4 bg-gray-50 px-4 py-4 dark:bg-gray-700 dark:text-white">
        <resource-form @send-input="addResource"></resource-form>
      </section>
      <ResourceList :resources="resources" />
      <dashed-button @click="showForm = true">Add resource</dashed-button>
      
    </article>
  </main>
</template>

<script>
import ResourceList from './components/ResourceList.vue';
import ResourceForm from './components/ResourceForm.vue';
import BlueButton from './components/Buttons/BlueButton.vue';
import DashedButton from './components/Buttons/DashedButton.vue';

export default {
  name: 'App',
  components: {
    ResourceList,
    BlueButton,
    DashedButton,
    ResourceForm,
  },
  data() {
    return {
      resources: [
        { title: "Official Guide", description: "The official Vue.js documentation.", url: "https://vuejs.org/" },
        { title: "Google", description: "Learn to google...", url: "https://www.google.com/" },
      ],
      showForm: false,
    };
  },
  methods: {
    addResource(resource) {

      if (!resource.title || !resource.description || !resource.url) {
        return;
      }

      this.resources.push(resource);

      this.showForm = false;
    },
    removeResource(index) {
      this.resources.splice(index, 1);
    }
  },
  provide() {
    return {
      deleteResource: this.removeResource,
    };
  },
}
</script>
