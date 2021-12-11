<script lang="ts">
  import Button from "./lib/Button.svelte";
  import Scroll from "./lib/Scroll.svelte";

  let isShowVideos = false;
  let isLoadingIframe = false;
</script>

<div class="min-h-screen max-w-[1200px] mx-auto flex flex-col items-center">
  <h1
    class="text-center text-4xl my-6 underline decoration-indigo-500 decoration-wavy"
  >
    Hotel Del Luna ❤️
  </h1>
  <Scroll />
  <button
    class="bg-indigo-500 shadow-lg shadow-indigo-500/50 py-2 px-4 rounded-md text-white font-semibold "
    on:click={() => {
      isShowVideos = !isShowVideos;
      if (!isLoadingIframe) isLoadingIframe = true;
    }}
  >
    {#if isShowVideos}
      Hide Videos
    {:else}
      See Videos
    {/if}
  </button>
  {#if isShowVideos}
    <div class="flex flex-col gap-2 my-6 gap-y-8">
      {#if isLoadingIframe}
        <p>Loading ...</p>
      {/if}
      <iframe
        on:load={(_e) => {
          isLoadingIframe = false;
        }}
        class="w-[400px] aspect-square"
        src="https://www.youtube.com/embed/WGxTAv55rK4"
        title="iu-cute-moment"
        frameborder="0"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
        allowfullscreen
      />
      <iframe
        on:load={(_e) => {
          isLoadingIframe = false;
        }}
        class="w-[400px] aspect-square"
        src="https://www.youtube.com/embed/WGxTAv55rK4"
        title="iu-cute-moment"
        frameborder="0"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
        allowfullscreen
      />
      <iframe
        on:load={(_e) => {
          isLoadingIframe = false;
        }}
        class="w-[400px] aspect-square"
        src="https://www.youtube.com/embed/WGxTAv55rK4"
        title="iu-cute-moment"
        frameborder="0"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
        allowfullscreen
      />
    </div>
  {/if}
</div>
