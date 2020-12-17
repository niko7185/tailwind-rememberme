
<template>
    <ul class="list-none">
        <resource-item  v-for="(resource, index) in resources" :key="index"
          :id="index"
          :title="resource.title" 
          :description="resource.description" 
          :link="resource.url"></resource-item>
      </ul>
</template>

<script>
import ResourceItem from './ResourceItem.vue'

export default {
    components: {
        ResourceItem,
    },
    props: ["resources"]
}
</script>
