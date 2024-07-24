<script lang="ts">
  // import components
  import SelectTeam from "./Select-team.svelte";
  import AvatartSettingProfile from "./Avatar-setting-profile.svelte";
  import DarkLightMode from "./Dark-light-mode.svelte";

  // import shadcn-svelte
  import { Button } from "$lib/components/ui/button";
</script>

<div
  class="max-xl:hidden w-full py-2 mb-6 px-80 border-b bg-card text-card-foreground shadow-sm"
>
  <div class="flex flex-row justify-between">
    <div class="flex flex-row items-center space-x-20">
      <h1 class="text-2xl font-bold">Logo</h1>
      <Button variant="ghost" class="text-sm font-medium text-muted-foreground"
        >Docs</Button
      >
    </div>
    <div class="flex flex-row items-center space-x-5">
      <SelectTeam />
      <AvatartSettingProfile />
      <DarkLightMode />
    </div>
  </div>
</div>


<!--Reponsive-->
<div
  class="xl:hidden w-screen py-2 mb-6 border-b bg-card text-card-foreground shadow-sm"
>
  <div class="flex flex-row items-center mx-2 justify-between">
    <div class="flex flex-row items-center space-x-1">
      <SelectTeam />
      <Button variant="ghost" class="text-sm font-medium text-muted-foreground"
        >Docs
      </Button>
    </div>
    <AvatartSettingProfile />
  </div>
</div>
