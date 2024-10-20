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

  export let service;

</script>

<div class="relative">
  <Popover.Root>
    <Popover.Trigger
      class="absolute z-50 top-0 right-0 p-2 hover:bg-zinc-900 rounded-lg"
    >
      <Ellipsis />
    </Popover.Trigger>
    <Popover.Content class="w-32">
      <div class="flex flex-col items-center text-center z-40">
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
  <button
    class="z-0"
    on:click={() => {
      goto(`/services/${service.id}`);
    }}
  >
    <div
      class="transition duration-300 hover:ring-zinc-600 hover:ring-1 p-6 max-w-xs w-80 border bg-card text-card-foreground shadow-sm rounded-lg relative"
    >
      <div class="flex space-x-5 items-center">
        <Avatar.Root>
          <Avatar.Image src={service.img} />
          <Avatar.Fallback>CN</Avatar.Fallback>
        </Avatar.Root>
        <div class="flex flex-col items-start space-y-2">
          <h1 class="text-xl font-bold">{service.name}</h1>
          <p class="text-sm text-muted-foreground">
            Create at {service.time} minutes ago
          </p>
        </div>
      </div>
      <div class="mt-4 text-left">
        <a
          href={"https://github.com/" + service.linkGit}
          class={badgeVariants({ variant: "default" })}
        >
          <div class="p-1 flex items-center space-x-2">
            <Github class="size-5" />
            <p>{service.linkGit}</p>
          </div>
        </a>
      </div>
    </div>
  </button>
</div>
