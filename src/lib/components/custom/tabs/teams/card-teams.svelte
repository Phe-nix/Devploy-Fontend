<script lang="ts">
  // shadcn-svelte
  import * as Card from "$lib/components/ui/card";
  import * as Avatar from "$lib/components/ui/avatar/index.js";
  import { Button } from "$lib/components/ui/button/index.js";
  import * as DropdownMenu from "$lib/components/ui/dropdown-menu/index.js";

  // icons
  import { Ellipsis } from "lucide-svelte";
</script>

<div class="mx-auto md:max-w-5xl md:w-full overflow-hidden">
  <Card.Root class="pt-5">
    <Card.Content class="flex items-center justify-between gap-x-2">
      <div class="flex items-center gap-x-2">
        <Avatar.Root class="mr-2 h-8 w-8">
          <Avatar.Image src="https://avatar.vercel.sh/$DDoc.png" />
          <Avatar.Fallback>SC</Avatar.Fallback>
        </Avatar.Root>
        <div>
          <h1 class="font-semibold">Team1</h1>
          <p class="text-muted-foreground text-sm">Owner</p>
        </div>
      </div>
      <DropdownMenu.Root>
        <DropdownMenu.Trigger asChild let:builder>
          <Button variant="ghost" builders={[builder]}>
            <Ellipsis />
          </Button>
        </DropdownMenu.Trigger>
        <DropdownMenu.Content class="w-36">
          <DropdownMenu.Group>
            <DropdownMenu.Item>View</DropdownMenu.Item>
            <DropdownMenu.Item>Manage</DropdownMenu.Item>
            <DropdownMenu.Item>Copy Invite URL</DropdownMenu.Item>
            <DropdownMenu.Item class="text-red-500"
              >Leave Team</DropdownMenu.Item
            >
          </DropdownMenu.Group>
        </DropdownMenu.Content>
      </DropdownMenu.Root>
    </Card.Content>
  </Card.Root>
</div>
