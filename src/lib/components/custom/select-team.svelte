<script lang="ts">
	import { ChevronsUpDown } from 'lucide-svelte';
	import { Check } from 'lucide-svelte';
	import { CirclePlus } from 'lucide-svelte';

	import { tick } from "svelte";
	import { cn } from "$lib/utils.js";
	import * as Avatar from "$lib/components/ui/avatar/index.js";
	import { Button } from "$lib/components/ui/button/index.js";
	import * as Command from "$lib/components/ui/command/index.js";
	import * as Dialog from "$lib/components/ui/dialog/index.js";
	import { Input } from "$lib/components/ui/input/index.js";
	import { Label } from "$lib/components/ui/label/index.js";
	import * as Popover from "$lib/components/ui/popover/index.js";
	import * as Select from "$lib/components/ui/select/index.js";

	let className: string | undefined | null = undefined;
	export { className as class };

	const groups = [
		{
			label: "Workspaces",
			teams: [
				{
					label: "Workspace 1",
					value: "workspace1",
				},
				{
					label: "Workspace 2",
					value: "workspace2",
				},
			],
		},
	];

	type Team = (typeof groups)[number]["teams"][number];

	let open = false;
	let showTeamDialog = false;

	let selectedTeam: Team = groups[0].teams[0];

	function closeAndRefocusTrigger(triggerId: string) {
		open = false;

		tick().then(() => document.getElementById(triggerId)?.focus());
	}
</script>

<Dialog.Root bind:open={showTeamDialog}>
	<Popover.Root bind:open let:ids>
		<Popover.Trigger asChild let:builder>
			<Button
				builders={[builder]}
				variant="outline"
				role="combobox"
				aria-expanded={open}
				aria-label="Select a team"
				class={cn("md:w-[200px] justify-between w-[150px]", className)}
			>
				<Avatar.Root class="mr-2 h-5 w-5">
					<Avatar.Image
						src="https://avatar.vercel.sh/${selectedTeam.value}.png"
						alt={selectedTeam.label}
					/>
					<Avatar.Fallback>SC</Avatar.Fallback>
				</Avatar.Root>
                <p class="text-sm font-bold text-gray-400">
                    {selectedTeam.label}
                </p>
				<ChevronsUpDown class="ml-auto h-4 w-4 shrink-0 opacity-50" />
			</Button>
		</Popover.Trigger>
		<Popover.Content class="w-[200px] p-0 outline-none">
			<Command.Root>
				<Command.Input class="outline-none" placeholder="Search team..." />
				<Command.List>
					<Command.Empty>No Workspace found.</Command.Empty>
					{#each groups as group}
						<Command.Group heading={group.label}>
							{#each group.teams as team}
								<Command.Item
									onSelect={() => {
										selectedTeam = team;
										closeAndRefocusTrigger(ids.trigger);
									}}
									value={team.label}
									class="text-sm"
								>
									<Avatar.Root class="mr-2 h-5 w-5">
										<Avatar.Image
											src="https://avatar.vercel.sh/${team.value}.png"
											alt={team.label}
										/>
										<Avatar.Fallback>SC</Avatar.Fallback>
									</Avatar.Root>
									{team.label}
									<Check
										class={cn(
											"ml-auto h-4 w-4",
											selectedTeam.value !== team.value && "text-transparent"
										)}
									/>
								</Command.Item>
							{/each}
						</Command.Group>
					{/each}
				</Command.List>
				<Command.Separator />
				<Command.List>
					<Command.Group>
						<Command.Item
							onSelect={() => {
								open = false;
								showTeamDialog = true;
							}}
						>
							<CirclePlus class="mr-2 h-5 w-5" />
							Create Workspace
						</Command.Item>
					</Command.Group>
				</Command.List>
			</Command.Root>
		</Popover.Content>
	</Popover.Root>
	<Dialog.Content>
		<Dialog.Header>
			<Dialog.Title>Create team</Dialog.Title>
			<Dialog.Description>
				Add a new workspace to manage products and customers.
			</Dialog.Description>
		</Dialog.Header>
		<div>
			<div class="space-y-4 py-2 pb-4">
				<div class="space-y-2">
					<Label for="name">name</Label>
					<Input id="name" placeholder="Acme Inc." />
				</div>
			</div>
		</div>
		<Dialog.Footer>
			<Button variant="outline" on:click={() => (showTeamDialog = false)}>Cancel</Button>
			<Button type="submit">Continue</Button>
		</Dialog.Footer>
	</Dialog.Content>
</Dialog.Root>