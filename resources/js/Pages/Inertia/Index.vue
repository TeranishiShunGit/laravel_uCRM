<script setup>
    import { Link } from '@inertiajs/inertia-vue3';
    import { ref } from 'vue';
    defineProps({
        blogs: Array
    })
</script>

<template>
    <div v-if="$page.props.flash.message" style="color:red">{{ $page.props.flash.message }}</div>
    <ul>
        <li v-for="blog in blogs" :key="blog.id">
            件名: 
            <Link :href="route('inertia.show', {id: blog.id})" class="text-blue-400">{{ blog.title }}</Link>
            本文: {{ blog.content }}
        </li>
    </ul>
</template>