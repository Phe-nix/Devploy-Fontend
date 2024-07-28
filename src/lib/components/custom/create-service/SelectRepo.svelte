<script lang="ts">
  // shadcn-svelte
  import { Input } from "$lib/components/ui/input/index.js";
  import { Search } from "lucide-svelte";

  // SVG Icons
  import { Github } from "lucide-svelte";
</script>

<div class="flex flex-col px-5 gap-y-2">
  <div
    class="flex gap-2 justify-center rounded-lg border text-card-foreground shadow-xl w-32 py-2 dark:bg-zinc-100 bg-zinc-950"
  >
    <Github class="dark:text-zinc-950 text-zinc-100" />
    <p class="dark:text-zinc-950 text-zinc-100">Phe-nix</p>
  </div>
  <Input type="email" placeholder="Search Projects..." class="w-1/2">
    <Search class="absolute size-12"/>
  </Input>
</div>
