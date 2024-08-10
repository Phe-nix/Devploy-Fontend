<script lang="ts">
  // import shadcn-svelte
  import { Button } from "$lib/components/ui/button/index.js";
  import * as Popover from "$lib/components/ui/popover";
  import * as Avatar from "$lib/components/ui/avatar";
  import { Badge } from "$lib/components/ui/badge";
  import { badgeVariants } from "$lib/components/ui/badge";

  // SVG Icons
  import { Package } from "lucide-svelte";
  import { Ellipsis } from "lucide-svelte";
  import { PackageMinus } from "lucide-svelte";
  import { PackageSearch } from "lucide-svelte";
  import { Github } from "lucide-svelte";
  import { goto } from "$app/navigation";

  // prop data
  export let project;
</script>

<button
  on:click={() => {
    goto(`/home/project/${project.id}`);
  }}
>
  <div
    class="transition duration-300 hover:ring-zinc-600 hover:ring-1 p-8 flex space-x-5 items-center max-w-xs w-72 border bg-card text-card-foreground shadow-sm rounded-lg relative"
  >
    <Package class="size-10" />
    <div class="flex flex-col space-y-2">
      <h1 class="text-xl font-bold">{project.name}</h1>
      <p class="text-sm text-muted-foreground">Description 1</p>
    </div>
    <Popover.Root>
      <Popover.Trigger
        class="absolute top-0 right-0 p-2 hover:bg-zinc-900 rounded-lg"
      >
        <Ellipsis />
      </Popover.Trigger>
      <Popover.Content class="w-32">
        <div class="flex flex-col items-center text-center">
          <Button
            variant="ghost"
            class="flex space-x-2 font-semibold text-emerald-700"
          >
            <PackageSearch />
            <p>Edit</p>
          </Button>
          <Button
            variant="ghost"
            class="flex space-x-2 font-semibold text-destructive"
          >
            <PackageMinus />
            <p>Delete</p>
          </Button>
        </div>
      </Popover.Content>
    </Popover.Root>
  </div>
</button>
