<script lang="ts">
  // shadcn-svelte
  import * as DropdownMenu from "$lib/components/ui/dropdown-menu";
  import { Button } from "$lib/components/ui/button/index.js";
  import { flyAndScale } from "$lib/utils";

  // SVG Icons
  import { Computer } from "lucide-svelte";
  import { Server } from "lucide-svelte";
  import { Database } from "lucide-svelte";
</script>

<DropdownMenu.Root>
  <DropdownMenu.Trigger>
    <Button class="gap-3 font-normal">
      <Computer class="size-6" />
      Create Services
    </Button>
  </DropdownMenu.Trigger>
  <DropdownMenu.Content transition={flyAndScale} sideOffset={8}>
    <DropdownMenu.Group>
      <DropdownMenu.Item>
        <a class="flex gap-3 items-center" href="/home/project/1/new/service">
          <Server class="size-4" />
          Appications
        </a>
      </DropdownMenu.Item>
      <DropdownMenu.Item>
        <a class="flex gap-3 items-center" href="/home/project/1/new/database">
            <Database class="size-4" />
            Databases
        </a>
      </DropdownMenu.Item>
    </DropdownMenu.Group>
  </DropdownMenu.Content>
</DropdownMenu.Root>
