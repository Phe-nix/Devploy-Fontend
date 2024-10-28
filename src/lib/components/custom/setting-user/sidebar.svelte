<script lang="ts">
  import { cubicInOut } from "svelte/easing";
  import { crossfade } from "svelte/transition";
  import { cn } from "$lib/utils.js";
  import { page } from "$app/stores";
  import { Button } from "$lib/components/ui/button";

  let className: string | undefined | null = undefined;
  export let items: { icon: string; title: string }[];
  export { className as class };
  export let nowPageSide: string;
  const [send, receive] = crossfade({
    duration: 250,
    easing: cubicInOut,
  });

  let isActive: boolean = true;
  let title: string = nowPageSide;
  const active = (text: string) => {
    title = text;
    nowPageSide = text;
  };
</script>

<div
  class={cn("flex space-x-2 lg:flex-col lg:space-x-0 lg:space-y-1", className)}
>
  {#each items as item}
    <Button
      on:click={() => {
        active(item.title);
      }}
      variant="ghost"
      class={cn(
        !isActive && "hover:underline",
        "relative justify-start hover:bg-transparent"
      )}
      data-sveltekit-noscroll
    >
      {#if isActive && title === item.title}
        <div
          class="bg-muted absolute inset-0 rounded-md"
          in:send={{ key: "active-sidebar-tab" }}
          out:receive={{ key: "active-sidebar-tab" }}
        />
      {/if}
      <div class="relative flex items-center gap-x-2 font-semibold text-base">
        {@html item.icon}
        {item.title}
      </div>
    </Button>
  {/each}
</div>
