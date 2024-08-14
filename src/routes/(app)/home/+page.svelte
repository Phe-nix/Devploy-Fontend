<script lang="ts">
  // import shadcn-svelte
  import * as Card from "$lib/components/ui/card/index.js";
  import * as Tabs from "$lib/components/ui/tabs";
  import { Input } from "$lib/components/ui/input/index.js";

  // import components
  import EmptyProjects from "$lib/components/custom/Emtpy-projects.svelte";
  import Cardprojects from "$lib/components/custom/Card-projects.svelte";
  import ModalCreateProjects from "$lib/components/custom/Modal-create-projects.svelte";
  import TeamPage from "$lib/components/custom/tabs/teams/Team-page.svelte";
  import SettingPage from "$lib/components/custom/setting-user/SettingPage.svelte";

  // SVG Icons
  import { Plus } from "lucide-svelte";
  let check = "";

  const tabs = [
    {
      name: "projects",
      label: "Projects",
      description: "Mannage your projects.",
    },
    {
      name: "teams",
      label: "Teams",
      description: "Mannage your teams.",
    },
    {
      name: "setting",
      label: "Setting",
      description: "Mannage your setting.",
    },
  ];

  const projects = [
    {
      id: 1,
      name: "Project 1",
      description: "Description 1",
    },
    {
      id: 2,
      name: "Project 2",
      description: "Description 2",
    },
    {
      id: 3,
      name: "Project 3",
      description: "Description 3",
    },
  ];
</script>

<div>
  <div class="flex flex-col">
    {#each tabs as tab}
    {#if tab.name === check}
      <h2
        class="scroll-m-20 pb-2 text-4xl font-semibold tracking-tight transition-colors first:mt-0"
      >
        {tab.label}
      </h2>
      <p class="text-sm text-muted-foreground">{tab.description}</p>
    {/if}
    {/each}
  </div>
  <Tabs.Root bind:value={check} class="w-full py-6">
    <Tabs.List class="grid w-full grid-cols-3">
      <Tabs.Trigger value="projects">Projects</Tabs.Trigger>
      <Tabs.Trigger value="teams">Teams</Tabs.Trigger>
      <Tabs.Trigger value="setting">Setting</Tabs.Trigger>
    </Tabs.List>
    <Tabs.Content value="projects">
      <Card.Root>
        <Card.Header>
          <form class="flex w-full max-w-5xl mx-auto space-x-4">
            <Input
              class="shadow-lg p-4"
              type="text"
              placeholder="🔍 Search something..."
            />
            <ModalCreateProjects />
          </form>
        </Card.Header>
        <Card.Content
          class="flex flex-row gap-3 flex-wrap items-center justify-center xl:justify-start"
        >
          {#if projects === undefined}
            <EmptyProjects />
          {:else}
            {#each projects as project}
              <Cardprojects {project} />
            {/each}
          {/if}
        </Card.Content>
      </Card.Root>
    </Tabs.Content>
    <Tabs.Content value="teams">
      <TeamPage />
    </Tabs.Content>
    <Tabs.Content value="setting">
      <SettingPage />
    </Tabs.Content>
  </Tabs.Root>
</div>
