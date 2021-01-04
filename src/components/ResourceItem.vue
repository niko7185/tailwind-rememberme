
<template>
    <li class="rounded-md my-4 bg-gray-50 px-4 py-4 transition-shadow hover:shadow-xl
                dark:bg-gray-700 dark:text-white dark:hover:bg-gray-500"> 
        <a :href="link">
            <div class="flex justify-between items-center">
                <h2 class="text-lg font-bold opacity-70">{{ title }}</h2>
                <button @click.prevent="deleteResource(id)" class="opacity-40 px-1 flex items-center
                  hover:text-red-500 hover:opacity-100">
                    <svg xmlns="http://www.w3.org/2000/svg"   
                        viewBox="0 0 24 24" fill="none" stroke="currentColor" 
                        stroke-width="2" stroke-linecap="round" stroke-linejoin="round" 
                        class="feather feather-x-circle w-4">
                            <circle cx="12" cy="12" r="10">
                            </circle>
                            <line x1="15" y1="9" x2="9" y2="15"></line>
                            <line x1="9" y1="9" x2="15" y2="15"></line>
                    </svg>
                 </button>
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
