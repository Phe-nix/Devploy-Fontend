<script lang="ts">
  import { Button, buttonVariants } from "$lib/components/ui/button/index.js";
  import * as Dialog from "$lib/components/ui/dialog/index.js";
  import { Input } from "$lib/components/ui/input/index.js";
  import { Label } from "$lib/components/ui/label/index.js";
  import { toast } from "svelte-sonner";

  import { Plus } from "lucide-svelte";

  let dialogOpen = false;
</script>

<Dialog.Root bind:open={dialogOpen}>
  <Dialog.Trigger class={buttonVariants({ variant: "default" })}>
    <div class="flex items-center gap-2">
      <Plus class="size-5" />
      Create User
    </div>
  </Dialog.Trigger>
  <Dialog.Content class="sm:max-w-[425px]">
    <Dialog.Header>
      <Dialog.Title>Create user</Dialog.Title>
      <Dialog.Description>
        Make create new user. Click crate when you're done.
      </Dialog.Description>
    </Dialog.Header>
    <div class="grid gap-4 py-4">
      <div class="grid grid-cols-4 items-center gap-4">
        <Label for="email" class="text-right">Email</Label>
        <Input id="email" value="64070047@kmitl.ac.th" class="col-span-3" />
      </div>
      <div class="grid grid-cols-4 items-center gap-4">
        <Label for="username" class="text-right">Username</Label>
        <Input id="username" value="@Phe-nix" class="col-span-3" />
      </div>
    </div>
    <Dialog.Footer>
      <Button
        type="submit"
        on:click={() => {
          dialogOpen = false;
          toast.success("User has been created");
        }}>Save changes</Button
      >
    </Dialog.Footer>
  </Dialog.Content>
</Dialog.Root>
