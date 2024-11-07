<script lang="ts">
  import { Button, buttonVariants } from "$lib/components/ui/button/index.js";
  import * as Dialog from "$lib/components/ui/dialog/index.js";
  import { Input } from "$lib/components/ui/input/index.js";
  import { Label } from "$lib/components/ui/label/index.js";
</script>

<Dialog.Root>
  <Dialog.Trigger class={buttonVariants({ variant: "default" })}
    ><span class="">Invite User</span></Dialog.Trigger
  >
  <Dialog.Content class="sm:max-w-[425px]">
    <Dialog.Header>
      <Dialog.Title>Invite User</Dialog.Title>
      <Dialog.Description>
        Invite your friends. Click invite when you're done.
      </Dialog.Description>
    </Dialog.Header>
    <div class="grid gap-4 py-4">
      <div class="grid grid-cols-4 items-center gap-4">
        <Label for="email" class="text-right">Email</Label>
        <Input id="email" value="64070047@kmitl.ac.th" class="col-span-3" />
      </div>
    </div>
    <Dialog.Footer>
      <Button type="submit">invite</Button>
    </Dialog.Footer>
  </Dialog.Content>
</Dialog.Root>
