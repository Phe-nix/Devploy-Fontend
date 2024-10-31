<script lang="ts">
  import * as Avatar from "$lib/components/ui/avatar/index.js";
  import { Input } from "$lib/components/ui/input/index.js";
  import { Label } from "$lib/components/ui/label/index.js";

  let username = "Phe-nix"
</script>

<div class="grid space-y-5">
  <div class="flex flex-col space-y-2">
    <h4 class="scroll-m-20 text-2xl font-semibold tracking-tight">
      Profile
    </h4>
    <p class="text-muted-foreground text-sm">
      Show your imformation profile.
    </p>
  </div>
  <Avatar.Root class="size-28">
    <Avatar.Image src="https://github.com/identicons/{username}.png" alt="@shadcn" />
    <Avatar.Fallback>CN</Avatar.Fallback>
  </Avatar.Root>
  <div class="grid w-full max-w-sm items-center gap-1.5">
    <Label for="User">Username</Label>
    <Input type="text" id="User" placeholder="User" disabled value="64070047"/>
  </div>
  <div class="grid w-full max-w-sm items-center gap-1.5">
    <Label for="User">Email</Label>
    <Input type="email" id="Email" placeholder="Email" disabled value="64070047@kmitl.ac.th"/>
  </div>
</div>
