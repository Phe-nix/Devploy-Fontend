<script lang="ts">
  import * as Avatar from "$lib/components/ui/avatar";
  import { Button } from "$lib/components/ui/button/index.js";
  import { Trash2 } from "lucide-svelte";
</script>

<div class="space-y-12">
  <div class="flex flex-col space-y-4">
    <div class="flex flex-col space-y-2">
      <h4 class="scroll-m-20 text-2xl font-semibold tracking-tight">
        Workspaces
      </h4>
      <p class="text-muted-foreground text-sm">
        The workspace that are associated with your Devploy account.
      </p>
    </div>
    <div
      class="flex justify-between bg-card border-[1px] p-4 rounded-lg my-2 items-center"
    >
      <div class="flex gap-3">
        <Avatar.Root>
          <Avatar.Image src="https://github.com/shadcn.png" alt="@shadcn" />
          <Avatar.Fallback>CN</Avatar.Fallback>
        </Avatar.Root>
        <div class="flex flex-col">
          <p>Name</p>
          <p class="text-muted-foreground text-sm">Owner</p>
        </div>
      </div>
      <div class="flex space-x-4">
        <Button>Edit</Button>
        <Button variant="secondary">Delete</Button>
      </div>
    </div>
  </div>
  <div class="flex flex-col space-y-4">
    <div class="flex">
      <div class="flex flex-col space-y-2">
        <h4 class="scroll-m-20 text-2xl font-semibold tracking-tight">
          Invited
        </h4>
        <p class="text-muted-foreground text-sm">
          The workspace that have invite you.
        </p>
      </div>
    </div>
    <div
      class="flex justify-between bg-card border-[1px] p-4 rounded-lg my-2 items-center"
    >
      <div class="flex gap-3">
        <Avatar.Root>
          <Avatar.Image src="https://github.com/shadcn.png" alt="@shadcn" />
          <Avatar.Fallback>CN</Avatar.Fallback>
        </Avatar.Root>
        <div class="flex flex-col">
          <p>Name</p>
          <p class="text-muted-foreground text-sm">@64070011</p>
        </div>
      </div>
      <div class="flex space-x-4">
        <Button>Accpet</Button>
        <Button variant="secondary">
          <Trash2 class="size-5"/>
        </Button>
      </div>
    </div>
  </div>
</div>
