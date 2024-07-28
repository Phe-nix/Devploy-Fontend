<script lang="ts">
  // shadcn-svelte
  import { Button } from "$lib/components/ui/button";

  // SVG Icons
  import { Github } from 'lucide-svelte';
  
  // import components
  import DialogGithub from "./DialogGithub.svelte";

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
  <Button>Connecting with Github</Button>
</div>
<div class="py-8">
    <DialogGithub />
</div>