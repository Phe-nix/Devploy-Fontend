<script lang="ts">
  // shadcn-svelte
  import { Input } from "$lib/components/ui/input/index.js";

  // SVG Icons
  import { Github } from "lucide-svelte";

  // import components
  import BoxRepo from "./BoxRepo.svelte";
</script>

<div class="flex flex-col px-5 space-y-2 items-center">
  <div class="flex flex-col space-y-3 w-1/2">
    <div
      class="flex gap-2 justify-center rounded-lg border text-card-foreground shadow-xl w-28 py-2 dark:bg-zinc-100 bg-zinc-950"
    >
      <Github class="dark:text-zinc-950 text-zinc-100" />
      <p class="dark:text-zinc-950 text-zinc-100">Phe-nix</p>
    </div>
    <Input type="email" placeholder="Search Projects..." />
    <div class="overflow-auto max-h-[250px]">
      <BoxRepo />
      <BoxRepo />
      <BoxRepo />
      <BoxRepo />
      <BoxRepo />
    </div>
  </div>
</div>
