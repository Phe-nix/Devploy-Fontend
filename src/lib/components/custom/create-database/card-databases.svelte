<script lang="ts">
  // shadcn-svelte
  import * as Avatar from "$lib/components/ui/avatar/index.js";
  import { Label } from "$lib/components/ui/label/index.js";

  export let name = "";
  export let img = "";

</script>

<div class="flex flex-col items-center space-y-4">
    <Avatar.Root>
        <Avatar.Image src="{img}" alt="@shadcn" />
        <Avatar.Fallback>CN</Avatar.Fallback>
      </Avatar.Root>
    <Label>{name}</Label>
</div>
