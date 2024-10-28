<script>
  import DataTableUsers from "./data-table-users.svelte";
</script>

<div class="py-8 px-4 space-y-4">
  <div class="flex flex-col">
    <h2
      class="scroll-m-20 pb-2 text-3xl font-semibold tracking-tight transition-colors first:mt-0"
    >
      All Users
    </h2>
    <p class="text-muted-foreground text-sm">List all users that was used Devploy.</p>
  </div>
  <div class="container mx-auto py-8 max-h-60">
    <DataTableUsers />
  </div>
</div>
