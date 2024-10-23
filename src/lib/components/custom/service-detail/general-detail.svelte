<script lang="ts">
  import { Button } from "$lib/components/ui/button/index.js";
  import { RefreshCcw } from "lucide-svelte";
  import { Hammer } from "lucide-svelte";
  import { CirclePlay } from "lucide-svelte";
</script>

<div class="my-4 flex flex-col space-y-5">
  <h3 class="scroll-m-20 text-2xl font-semibold tracking-tight">
    Deploy Setting
  </h3>
  <div class="flex gap-3">
    <Button size="sm">Deploy</Button>
    <Button size="sm" variant="secondary" class="gap-1.5">
      Reload
      <RefreshCcw class="size-4" />
    </Button>
    <Button size="sm" variant="secondary" class="gap-1.5">
      Rebuild
      <Hammer class="size-4" />
    </Button>
    <Button size="sm" variant="secondary" class="gap-1.5">
      Start
      <CirclePlay class="size-4"/>
    </Button>
  </div>
</div>
