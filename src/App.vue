<script setup>
import { ref } from "vue";
import TreeView from "@/components/TreeView.vue";

const root = ref({
  label: "Level 1",
  nodes: [
    {
      label: "Level 1.1",
      nodes: [
        {
          label: "Level 1.1.1"
        }
      ]
    },
    {
      label: "Level 1.2",
      nodes: [
        {
          label: "Level 1.2.1",
          nodes: [
            {
              label: "Level 1.2.1.1"
            },
            {
              label: "Level 1.2.1.2",
              nodes: [
                {
                  label: "Level 1.2.1.2.1"
                }   
              ]
            }
          ]
        },
        {
          label: "Level 1.2.2",
          nodes: [
            {
              label: "Level 1.2.2.1"
            }
          ]
        }
      ]
    },
    {
      label: "Level 1.3",
      nodes: [
        {
          label: "Level 1.3.1"
        },
        {
          label: "Level 1.3.2"
        }
      ]
    }
  ]
});
</script>

<template>
  <TreeView
    :label="root.label"
    :nodes="root.nodes" 
  />
</template>

<style scoped></style>
