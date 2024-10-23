<script lang="ts">
  import DataTable from "./data-table-users.svelte";
  import ModalCrateUser from "./modal-crate-user.svelte";
</script>

<div class="container mx-auto space-y-5">
  <div class="flex items-center justify-between">
    <div class="flex flex-col space-y-2">
      <h4 class="scroll-m-20 text-2xl font-semibold tracking-tight">Users</h4>
      <p class="text-muted-foreground text-sm">Mannage and delete users.</p>
    </div>
    <ModalCrateUser />
  </div>
  <DataTable />
</div>
