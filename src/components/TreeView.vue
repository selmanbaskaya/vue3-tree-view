<script setup>
import { ref } from "vue"
import TreeView from "@/components/TreeView.vue";

const props = defineProps(['label', 'nodes'])

const childVisibility = ref(false)
</script>

<template>
    <div
      class="label"
      @click="childVisibility = !childVisibility"
    >
        <font-awesome-icon
          class="icon"
          :icon="childVisibility ? 'fa-solid fa-minus' : 'fa-solid fa-plus'"
        />
        <span class="label-text">{{ label }}</span>
    </div>
    <div
      class="child"
      v-if="childVisibility"
    >
        <TreeView
          v-for="child in nodes"
          :label="child.label"
          :nodes="child.nodes"
        />
    </div>
</template>

<style lang="scss" scoped>
.label {
    margin: 5px 10px;
    color: grey-5;
}

.label-text {
    margin: 10px;
}

.child {
    margin-left: 20px;
}
</style>