<script lang="ts">
  // shadcn-svelte
  import * as Breadcrumb from "$lib/components/ui/breadcrumb/index.js";
  import * as Card from "$lib/components/ui/card/index.js";
  import { Input } from "$lib/components/ui/input/index.js";
  import * as Tabs from "$lib/components/ui/tabs";

  // import components
  import EmptyProjects from "$lib/components/custom/emtpy-projects.svelte";
  import CardServicesDatabases from "$lib/components/custom/card-services-databases.svelte";
  import DropdownCreateService from "$lib/components/custom/button-create-service.svelte";
  import SettingPage from "$lib/components/custom/setting-user/settingPage.svelte";

  import { pushState, replaceState } from "$app/navigation";
  import { page } from "$app/stores";
  import { Database } from "lucide-svelte";
  // SVG Icons

  // let service = [
  //   {
  //     name: "Zela-Frontend",
  //     time: "21",
  //     img: "https://github.com/Phe-nix.png",
  //     linkGit: "Phe-nix/zela",
  //   },
  // ];

  function showApp() {
    replaceState("/home", {
      showApp: true,
    });
  }

  function showDatabase() {
    replaceState("/home/databases", {
      showDatabase: true,
    });
  }

  function showSetting() {
    replaceState("/home/setting", {
      showSetting: true,
    });
  }

  let services = {
    app: [
      {
        id: "1",
        name: "Zela-Frontend",
        time: "21",
        img: "https://github.com/Phe-nix.png",
        linkGit: "Phe-nix/zela",
        stack: "Svelte",
      },
    ],
    database: [
      {
        id: "1",
        name: "Zela-database",
        time: "21",
        stack: "MongoDB",
      },
    ],
  };
</script>

<div>
  <div class="py-6 flex justify-between items-center">
    <h2
      class="scroll-m-20 pb-2 text-3xl font-semibold tracking-tight transition-colors first:mt-0"
    >
      Team Name
    </h2>
    {#if $page.state.showApp}
      <DropdownCreateService type="application" />
    {:else if $page.state.showDatabase}
      <DropdownCreateService type="database" />
    {:else if $page.state.showSetting}
      <DropdownCreateService type="shit"/>
    {/if}
  </div>
  <Tabs.Root value="app" class="w-full py-6">
    <Tabs.List class="grid w-full grid-cols-3">
      <Tabs.Trigger
        value="app"
        on:click={() => {
          showApp();
        }}>Applications</Tabs.Trigger
      >
      <Tabs.Trigger
        value="database"
        on:click={() => {
          showDatabase();
        }}>Databases</Tabs.Trigger
      >
      <Tabs.Trigger
        value="setting"
        on:click={() => {
          showSetting();
        }}>Setting</Tabs.Trigger
      >
    </Tabs.List>
    <Tabs.Content value="app">
      <Card.Root>
        <Card.Header>
          <form class="flex w-full max-w-5xl mx-auto items-center space-x-2">
            <Input
              class="shadow-lg p-4"
              type="text"
              placeholder="🔍 Search something..."
            />
          </form>
        </Card.Header>
        <Card.Content>
          {#if services == undefined}
            <EmptyProjects type="service" />
          {:else}
            <div class="my-2">
              <h2
                class="scroll-m-20 pb-4 text-3xl font-semibold tracking-tight transition-colors first:mt-0"
              >
                Applications ({services.app.length})
              </h2>
              <div
                class="flex flex-row gap-3 flex-wrap items-center justify-center xl:justify-start"
              >
                {#each services.app as service}
                  <CardServicesDatabases {service} />
                {/each}
              </div>
            </div>
          {/if}
        </Card.Content>
      </Card.Root>
    </Tabs.Content>
    <Tabs.Content value="database">
      <Card.Root>
        <Card.Header>
          <form class="flex w-full max-w-5xl mx-auto items-center space-x-2">
            <Input
              class="shadow-lg p-4"
              type="text"
              placeholder="🔍 Search something..."
            />
          </form>
        </Card.Header>
        <Card.Content>
          {#if services == undefined}
            <EmptyProjects type="service" />
          {:else}
            <div class="py-4">
              <h2
                class="scroll-m-20 pb-4 text-3xl font-semibold tracking-tight transition-colors first:mt-0"
              >
                Databases ({services.database.length})
              </h2>
              <div
                class="flex flex-row gap-3 flex-wrap items-center justify-center xl:justify-start"
              >
                {#each services.database as service}
                  <CardServicesDatabases {service} />
                {/each}
              </div>
            </div>
          {/if}
        </Card.Content>
      </Card.Root>
    </Tabs.Content>
    <Tabs.Content value="setting">
      <SettingPage />
    </Tabs.Content>
  </Tabs.Root>
</div>
