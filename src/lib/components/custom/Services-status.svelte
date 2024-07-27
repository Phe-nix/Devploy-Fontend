<script lang="ts">
  // import shadcn-svelte
  import { Tooltip } from "bits-ui";
  import { flyAndScale } from "$lib/index.js";
  // import SVG
  import { Earth } from "lucide-svelte";

  // props
  export let status = "not-started";
</script>

{#if status === "not-started"}
  <Tooltip.Root openDelay={0}>
    <Tooltip.Trigger>
      <div class="relative">
        <div class="absolute top-0 right-0">
          <span class="relative flex h-3 w-3">
            <span
              class="animate-ping absolute inline-flex h-full w-full rounded-full bg-gray-500 opacity-75"
            ></span>
            <span class="relative inline-flex rounded-full h-3 w-3 bg-gray-600"
            ></span>
          </span>
        </div>
        <Earth class="size-8" />
      </div>
    </Tooltip.Trigger>
    <Tooltip.Content
      transition={flyAndScale}
      transitionConfig={{ y: 8, duration: 150 }}
      sideOffset={8}
    >
      <div class="bg-background">
        <Tooltip.Arrow class="rounded-[2px] border-l border-t border-dark-10" />
      </div>
      <div
        class="flex items-center justify-center rounded-xl border border-dark-10 bg-background p-3 text-sm font-medium shadow-popover outline-none"
      >
        It's not started yet 🥺
      </div>
    </Tooltip.Content>
  </Tooltip.Root>
{:else if status === "error"}
  <Tooltip.Root openDelay={0}>
    <Tooltip.Trigger>
      <div class="relative">
        <div class="absolute top-0 right-0">
          <span class="relative flex h-3 w-3">
            <span
              class="animate-ping absolute inline-flex h-full w-full rounded-full bg-destructive opacity-75"
            ></span>
            <span
              class="relative inline-flex rounded-full h-3 w-3 bg-destructive"
            ></span>
          </span>
        </div>
        <Earth class="size-8" />
      </div>
    </Tooltip.Trigger>
    <Tooltip.Content
      transition={flyAndScale}
      transitionConfig={{ y: 8, duration: 150 }}
      sideOffset={8}
    >
      <div class="bg-background">
        <Tooltip.Arrow class="rounded-[2px] border-l border-t border-dark-10" />
      </div>
      <div
        class="flex items-center justify-center rounded-xl border border-dark-10 bg-background p-3 text-sm font-medium shadow-popover outline-none"
      >
        Oh no! Something wrong 😭
      </div>
    </Tooltip.Content>
  </Tooltip.Root>
{:else if status === "running"}
  <Tooltip.Root openDelay={0}>
    <Tooltip.Trigger>
      <div class="relative">
        <div class="absolute top-0 right-0">
          <span class="relative flex h-3 w-3">
            <span
              class="animate-ping absolute inline-flex h-full w-full rounded-full bg-green-600 opacity-75"
            ></span>
            <span
              class="relative inline-flex rounded-full h-3 w-3 bg-green-600"
            ></span>
          </span>
        </div>
        <Earth class="size-8" />
      </div>
    </Tooltip.Trigger>
    <Tooltip.Content
      transition={flyAndScale}
      transitionConfig={{ y: 8, duration: 150 }}
      sideOffset={8}
    >
      <div class="bg-background">
        <Tooltip.Arrow class="rounded-[2px] border-l border-t border-dark-10" />
      </div>
      <div
        class="flex items-center justify-center rounded-xl border border-dark-10 bg-background p-3 text-sm font-medium shadow-popover outline-none"
      >
        Service is running 😎
      </div>
    </Tooltip.Content>
  </Tooltip.Root>
{/if}
