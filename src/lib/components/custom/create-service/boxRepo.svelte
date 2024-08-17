<script lang="ts">
  // shadcn-svelte
  import * as Avatar from "$lib/components/ui/avatar";
  import { Button } from "$lib/components/ui/button";
</script>

<div
  class="flex items-center gap-2 border bg-card text-card-foreground shadow-sm rounded-sm p-2 relative"
>
  <Avatar.Root class="m-1">
    <Avatar.Image src="https://github.com/shadcn.png" alt="@shadcn" />
    <Avatar.Fallback>CN</Avatar.Fallback>
  </Avatar.Root>
  <p>Zela-fontend</p>
  <Button class="absolute right-0 m-2 font-semibold">Import</Button>
</div>
