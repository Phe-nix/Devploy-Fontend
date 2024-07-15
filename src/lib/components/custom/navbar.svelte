<script lang="ts">
    // import components
    import SelectTeam from "./select-team.svelte";
</script>


<div class="w-full py-3 mb-6 px-80 border bg-card text-card-foreground shadow-sm">
    <div class="flex flex-row justify-between">
        <div class="flex flex-row items-center space-x-20">
            <h1 class="text-2xl font-bold">Logo</h1>
            <p class="text-sm text-muted-foreground">Docs</p>
        </div>
        <div class="flex flex-row items-center">
            <SelectTeam />
        </div>
    </div>
</div>