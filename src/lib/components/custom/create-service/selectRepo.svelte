<script lang="ts">
  // shadcn-svelte
  import { Input } from "$lib/components/ui/input/index.js";
  import { ScrollArea } from "$lib/components/ui/scroll-area/index.js";

  // SVG Icons
  import { Github } from "lucide-svelte";

  // import components
  import BoxRepo from "./boxRepo.svelte";
  import DialogImportRepo from "./dialog-importRepo.svelte";
  import SelectAccGithub from "./select-acc-github.svelte";

  export let isSelectRepo: any;
</script>

<div class="flex flex-col px-5 space-y-2 items-center">
  <div class="flex flex-col space-y-3 md:w-1/2 w-full">
    <SelectAccGithub/>
    <!-- <div
      class="flex gap-2 justify-center rounded-lg border text-card-foreground shadow-xl w-28 py-2 dark:bg-zinc-100 bg-zinc-950"
    >
      <Github class="dark:text-zinc-950 text-zinc-100" />
      <p class="dark:text-zinc-950 text-zinc-100">Phe-nix</p>
    </div> -->
    <Input type="email" placeholder="Search Projects..." />
    <ScrollArea class="h-72 w-full rounded-md">
      <BoxRepo bind:isSelectRepo />
    </ScrollArea>
    <!-- <div class="overflow-y-hidden max-h-[250px]">
      <BoxRepo />
      <BoxRepo />
      <BoxRepo />
      <BoxRepo />
      <BoxRepo />
    </div> -->
  </div>
</div>
<div class="py-8">
  <DialogImportRepo />
</div>
