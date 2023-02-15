<script lang="ts" setup>
import { Sidemenu as SIGRHSidemenu } from '@sigesp/sigrh-web';

const props = defineProps<{
    modulo?: string
}>()

const sidemenuDataMap: Record<string, any> = {
    'sigrh': SIGRHSidemenu
}

const sidemenuData = sidemenuDataMap[props.modulo ?? ""]
</script>

<template>
    <aside v-if="sidemenuData !== undefined">
        <nav>
            <ul>
                <li v-for="item in sidemenuData.items"><a :href="item.href">{{ item.label }}</a></li>
            </ul>
        </nav>
    </aside>
</template>


<style scoped>
aside {
    background-color: white;
    border-right: 1px inset #dae3e8;
}

a {
    text-decoration: none;
    color: #222;

    padding: .8rem;
    margin: 0 1rem;
    border-radius: .5rem;
    display: block;

    transition-property: background-color;
    transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
    transition-duration: 150ms;
}

a:hover {
    background-color: #dae3e8;
    color: #2e4653;
}

ul {
    display: flex;
    flex-direction: column;
    gap: 1rem;
    padding: unset;
}

li {
    list-style-type: none;
    display: block;
}
</style>