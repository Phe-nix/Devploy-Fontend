<script lang="ts">
  import Ellipsis from "lucide-svelte/icons/ellipsis";
  import * as Popover from "$lib/components/ui/popover";
  import EditUserDetail from "./edit-user-detail.svelte";
  import AlertDeleteUser from "./alert-delete-user.svelte";
  export let id: string;
</script>

<Popover.Root>
  <Popover.Trigger class="rounded-lg">
    <Ellipsis class="h-4 w-4" />
  </Popover.Trigger>
  <Popover.Content class="w-18">
    <div class="flex flex-col items-center text-center z-40">
      <EditUserDetail/>
      <AlertDeleteUser/>
    </div>
  </Popover.Content>
</Popover.Root>
