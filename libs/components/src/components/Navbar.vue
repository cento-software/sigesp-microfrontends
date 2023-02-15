<script setup lang="ts">
defineProps<{
  items: Array<{
    label: string
    href: string
  }>
}>()
</script>

<template>
  <header>
    <nav>
      <ul>
        <li v-for="item in items"><a :href="item.href">{{ item.label }}</a></li>
      </ul>
    </nav>
  </header>
</template>

<style scoped>
header {
  padding: .5rem 6rem;
  background-color: white;
  border-bottom: 1px solid #dae3e8;
}

a {
  text-decoration: none;
  color: #8a8a8a;

  transition-property: color;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  transition-duration: 150ms;
}

a:hover {
  color: #222;
}

ul {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 4rem;
}

li {
  list-style-type: none;
}
</style>
