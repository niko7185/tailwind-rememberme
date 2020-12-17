
<template>
    <li class="rounded-md my-4 bg-gray-50 px-4 py-4 transition-shadow hover:shadow-xl
                dark:bg-gray-700 dark:text-white"> 
        <a :href="link">
            <div class="flex justify-between items-center">
                <h2 class="text-lg font-bold opacity-70">{{ title }}</h2>
                <button @click.prevent="deleteResource(id)" class="opacity-40 px-1 border-2 font-bold 
                 border-black rounded-full flex items-center dark:border-white
                 hover:border-red-500 hover:text-red-500 hover:opacity-100">x</button>
            </div>
            <p class="opacity-70">{{ description }}</p>

        </a>
    </li>
</template>

<script>
export default {
    props: {
        title: {
            type: String,
            required: true,
        },
        description: {
            type: String,
            required: true,
        },
        link: {
            type: String,
            required: true,
        },
        id: {
            type: Number,
            required: true,
        }
    },
    inject: ["deleteResource"]
}
</script>
