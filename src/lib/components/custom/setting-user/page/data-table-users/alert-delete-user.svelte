<script lang="ts">
  import * as AlertDialog from "$lib/components/ui/alert-dialog";
  import { Button } from "$lib/components/ui/button/index.js";
  import { toast } from "svelte-sonner";
</script>

<AlertDialog.Root>
  <AlertDialog.Trigger>
    <Button
      variant="ghost"
      size="sm"
      class="font-semibold hover:text-[hsl(0,72%,51%)]"
    >
      <p>Delete</p>
    </Button>
  </AlertDialog.Trigger>
  <AlertDialog.Content>
    <AlertDialog.Header>
      <AlertDialog.Title>Are you absolutely sure to delete?</AlertDialog.Title>
      <AlertDialog.Description>
        This action cannot be undone. This will permanently delete your service.
      </AlertDialog.Description>
    </AlertDialog.Header>
    <AlertDialog.Footer>
      <AlertDialog.Cancel>Cancel</AlertDialog.Cancel>
      <AlertDialog.Action
        on:click={() => {
          toast.success("Delete success.");
        }}>Continue</AlertDialog.Action
      >
    </AlertDialog.Footer>
  </AlertDialog.Content>
</AlertDialog.Root>
