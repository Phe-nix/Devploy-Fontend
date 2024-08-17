<script lang="ts">
  // shadcn-svelte
  import { Button } from "$lib/components/ui/button";
  import * as Dialog from "$lib/components/ui/dialog/index.js";
  import { Input } from "$lib/components/ui/input/index.js";
  import { Label } from "$lib/components/ui/label/index.js";
  import { flyAndScale } from "$lib/utils";

  // SVG Icons
  import { Github } from "lucide-svelte";
  import { ArrowRight } from "lucide-svelte";

  export let isprivateRepo;
  export let isSignedInGithub;
  let showDialog = false;
</script>

<div class="flex flex-col items-center space-y-6">
  <img
    class="hidden dark:block rounded-full size-32"
    src="https://assets-global.website-files.com/61d1b6e84887f53fef1dcdf2/631b45e07d98cfb364e5951f_github-white.png"
    alt="Logo github"
  />
  <img
    class="dark:hidden rounded-full size-32"
    src="https://cdn.icon-icons.com/icons2/2428/PNG/512/github_black_logo_icon_147128.png"
    alt="Logo github"
  />
  <Button on:click={() => {
    isSignedInGithub = true;
  }}>Connecting with Github</Button>
</div>
<div class="py-8">
  <Dialog.Root bind:open={showDialog}>
    <Dialog.Trigger class="text-muted-foreground text-xs md:text-sm flex items-center gap-1">
      Import with Public Repository from GitHub
      <ArrowRight class="size-4" />
    </Dialog.Trigger>
    <Dialog.Content transition={flyAndScale} class="sm:max-w-[425px]">
      <Dialog.Header class="pb-6">
        <Dialog.Title>Import a GitHub Repository</Dialog.Title>
        <Dialog.Description>
          Import your project from a private repository on GitHub.
        </Dialog.Description>
      </Dialog.Header>
      <div class="flex w-full flex-col gap-2">
        <Label for="url"
          >Enter <span class="font-semibold">the URL of a Github repository</span>
          to deploy it :</Label
        >
        <Input
          type="url"
          id="url"
          placeholder="https://some-provider.come/some.organization/some-project"
        />
      </div>
      <Dialog.Footer class="flex flex-row sm:justify-between justify-between items-center">
        <Button on:click={() => {
          showDialog = false;
        }}>Back</Button>
        <Button type="submit" on:click={() => {
          showDialog = false;
          isprivateRepo = true;
        }}>Let Built</Button>
      </Dialog.Footer>
    </Dialog.Content>
  </Dialog.Root>
</div>
