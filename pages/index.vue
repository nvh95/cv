<template>
  <NotionRenderer :blockMap="blockMap" fullPage />
</template>

<script>
export default {
  data: () => ({ blockMap: null }),
  async asyncData({ $notion }) {
    // use Notion module to get Notion blocks from the API via a Notion pageId
    const blockMap = await $notion.getPageBlocks(
      "e643118bf60d4125a323f67092c05573"
    );

    return { blockMap };
  },
};
</script>

<style>
@import "@/styles/vue-notion-overrides.css";
@import "vue-notion/src/styles.css"; /* optional Notion-like styles */
</style>
