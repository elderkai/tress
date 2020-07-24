<template>
  <div>
    <trees-compt :list="trees"></trees-compt>
  </div>
</template>

<script>
import TreesCompt from "./TreesCopt";

export default {
  components: {
    TreesCompt
  },
  data() {
    return {
      trees: [
        {
          table: 1,
          nodes: [
            { table: 11 },
            { table: 12, nodes: [{ table: 121 }, { table: 122 }] }
          ]
        },
        {table:2}
      ]
    };
  }
};
</script>

