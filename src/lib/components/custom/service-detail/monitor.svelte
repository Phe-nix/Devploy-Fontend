<script lang="ts">
  import { onMount } from "svelte";
  import { Progress } from "$lib/components/ui/progress/index.js";
</script>

<div class="my-5">
  <div class="flex flex-col space-y-2">
    <h4 class="scroll-m-20 text-2xl font-semibold tracking-tight">Monitor</h4>
    <p class="text-muted-foreground text-sm">Watch the usage of application.</p>
  </div>
  <div class="flex gap-6 my-4">
    <div class="flex flex-col w-1/2 gap-1">
      <p>CPU</p>
      <p class="text-muted-foreground text-sm">Used: 50%</p>
      <Progress value={50} max={100} class="w-full" />
    </div>
    <div class="flex flex-col w-1/2 gap-1">
      <p>Memory</p>
      <p class="text-muted-foreground text-sm">Used: 5 GB / Limit: 7.72 GB</p>
      <Progress value={50} max={100} class="w-full" />
    </div>
  </div>
</div>
