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

  // SVG Icons
  import { Plus } from "lucide-svelte";

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
  <!-- <div class="flex flex-col">
    <h2
      class="scroll-m-20 pb-2 text-3xl font-semibold tracking-tight transition-colors first:mt-0"
    >
      Projects
    </h2>
    <p class="text-sm text-muted-foreground">Mannage your projects.</p>
  </div> -->
  <Tabs.Root value="projects" class="w-full py-10">
    <Tabs.List class="grid w-full grid-cols-4">
      <Tabs.Trigger value="projects">Projects</Tabs.Trigger>
      <Tabs.Trigger value="monitor">Monitor</Tabs.Trigger>
      <Tabs.Trigger value="teams">Teams</Tabs.Trigger>
      <Tabs.Trigger value="setting">Setting</Tabs.Trigger>
    </Tabs.List>
    <Tabs.Content value="projects">
      <Card.Root>
        <Card.Header>
          <form class="flex flex-col w-full max-w-5xl mx-auto space-y-4">
            <div class="flex justify-between">
              <div>
                <h2 class="text-3xl font-semibold tracking-tight transition-colors first:mt-0">
                  Projects
                </h2>
                <p class="text-muted-foreground text-sm">Mannage your projects.</p>
              </div>
              <ModalCreateProjects />
            </div>
            <Input
              class="shadow-lg p-4"
              type="text"
              placeholder="🔍 Search something..."
            />
          </form>
        </Card.Header>
        <Card.Content
          class="flex flex-row gap-3 flex-wrap items-center justify-center xl:justify-start"
        >
          {#if projects === undefined}
            <EmptyProjects />
          {:else}
            {#each projects as project}
              <Cardprojects
                {project}
              />
            {/each}
          {/if}
        </Card.Content>
      </Card.Root>
    </Tabs.Content>
    <Tabs.Content value="monitor">
      <Card.Root>
        <Card.Header>
          <form class="flex w-full max-w-5xl mx-auto items-center space-x-2">
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
              <Cardprojects
                {project}
              />
            {/each}
          {/if}
        </Card.Content>
      </Card.Root>
    </Tabs.Content>
    <Tabs.Content value="teams">
      <TeamPage />
    </Tabs.Content>
  </Tabs.Root>
</div>
