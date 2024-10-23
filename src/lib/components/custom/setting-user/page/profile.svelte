<script lang="ts">
  import * as Avatar from "$lib/components/ui/avatar/index.js";
  import { Input } from "$lib/components/ui/input/index.js";
  import { Label } from "$lib/components/ui/label/index.js";
</script>

<div class="grid space-y-5">
  <div class="flex flex-col space-y-2">
    <h4 class="scroll-m-20 text-2xl font-semibold tracking-tight">
      Profile
    </h4>
    <p class="text-muted-foreground text-sm">
      Edit your imformation profile.
    </p>
  </div>
  <Avatar.Root class="size-28">
    <Avatar.Image src="https://github.com/shadcn.png" alt="@shadcn" />
    <Avatar.Fallback>CN</Avatar.Fallback>
  </Avatar.Root>
  <div class="grid w-full max-w-sm items-center gap-1.5">
    <Label for="picture">Profile</Label>
    <Input id="picture" type="file" />
  </div>
  <div class="grid w-full max-w-sm items-center gap-1.5">
    <Label for="User">Username</Label>
    <Input type="User" id="User" placeholder="User" />
  </div>
</div>
