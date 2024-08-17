<script lang="ts">
  // import components
  import SelectTeam from "./select-team.svelte";
  import AvatartSettingProfile from "./avatar-setting-profile.svelte";
  import DarkLightMode from "./dark-light-mode.svelte";

  // import shadcn-svelte
  import { Button } from "$lib/components/ui/button";
  import * as Sheet from "$lib/components/ui/sheet";

  // icon
  import { Menu } from "lucide-svelte";
</script>

<div
  class="max-xl:hidden w-full py-2 mb-6 px-80 border-b bg-card text-card-foreground shadow-sm"
>
  <div class="flex flex-row justify-between">
    <div class="flex flex-row items-center space-x-20">
      <a href="/home" class="text-2xl font-bold">Logo</a>
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
    <div class="flex flex-row items-center space-x-4">
      <Sheet.Root>
        <Sheet.Trigger>
          <Menu />
        </Sheet.Trigger>
        <Sheet.Content side="left">
          <div class="flex flex-col z-50 gap-2 p-2 shadow-lg inset-y-0 left-0 h-full w-3/4 sm:max-w-sm pr-0">
            <a href="/home" class="text-foreground/60 flex items-center">Logo Devploy</a>
            <div class="relative overflow-hidden my-4 h-[calc(100vh-8rem)] pb-10 pl-6" data-scroll-area-root style="overflow: hidden;">
              <a href="/home" class="font-semibold">Docs</a>
            </div>
          </div>
        </Sheet.Content>
      </Sheet.Root>
      <SelectTeam />
    </div>
    <AvatartSettingProfile />
  </div>
</div>
