<script lang="ts">
  import Card from "./Card.svelte";

  type SnapPosition = "center" | "start" | "end" | undefined;

  export const snapPosition: SnapPosition = "center";

  const imgList: string[] = [
    "https://c.tenor.com/p6XoqKKnS_kAAAAd/hotel-del-luna-iu.gif",
    "https://c.tenor.com/OICw6IV0jEEAAAAd/iu-manwol.gif",
    "https://c.tenor.com/GfPRpxcJT_UAAAAC/iu-lee-ji-eun.gif",
    "https://c.tenor.com/-GZz3-J6_KEAAAAC/iu-lee-jieun.gif",
    "https://c.tenor.com/ZpQsPgwBgekAAAAC/iu-funny-face.gif",
  ];
</script>

<div class="flex snap-x overflow-x-auto w-full gap-6 pb-8">
  {#if snapPosition === "center"}
    <div class="snap-center shrink-0 w-[300px]" />
  {/if}

  {#each imgList as src}
    <div class="snap-center shrink-0">
      <Card {src} />
    </div>
  {/each}
  {#if snapPosition === "center"}
    <div class="snap-center shrink-0 w-[300px]" />
  {/if}
</div>
