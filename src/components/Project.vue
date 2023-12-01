<script setup>
    defineProps([
        'name',
        'description',
        'repo',
        'lang',
        'stars',
    ])
    const langMap = new Map();
    langMap.set('rust', 'badge-accent')
    langMap.set('python', 'badge-warning')
    langMap.set('lua', 'badge-secondary')
    langMap.set('vue', 'badge-success')
    langMap.set('go', 'badge-info')
    langMap.set('dart', 'badge-primary')
</script>

<template>
    <div class="card flex m-4 bg-base-200 shadow-xl">
        <div class="card-body flex">
            <a :href="repo" target="_blank"><h2 class="card-title">{{name}}</h2></a>
            <p>{{description}}</p>
            <div class="flex">
                <div :class="langMap.get(lang)" class="badge badge-xl badge-outline mt-2">{{lang}}</div>
                <button v-if="stars > 0" class="btn bg-base-200 shadow-xl justify-right btn-sm ml-auto">
                    <a :href="repo" target="_blank">{{stars}}
                        <div class="badge badge-secondary">★</div></a>
                </button>
            </div>
        </div>
    </div>
</template>
