<script lang="ts">
    //import shadcn-svelte
    import * as Avatar from "$lib/components/ui/avatar";
</script>

<Avatar.Root>
    <Avatar.Image src="https://github.com/shadcn.png" alt="@shadcn" />
    <Avatar.Fallback>CN</Avatar.Fallback>
  </Avatar.Root>