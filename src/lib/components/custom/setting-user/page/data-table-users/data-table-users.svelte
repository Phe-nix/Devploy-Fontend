<script lang="ts">
  import {
    createTable,
    Render,
    Subscribe,
    createRender,
  } from "svelte-headless-table";
  import { readable } from "svelte/store";
  import {
    addPagination,
    addSortBy,
    addTableFilter,
  } from "svelte-headless-table/plugins";
  import * as Table from "$lib/components/ui/table";
  import DataTableActions from "./data-table-actions.svelte";
  import { Input } from "$lib/components/ui/input";

  type User = {
    id: string;
    date: string;
    status: "pending" | "processing" | "success" | "failed";
    email: string;
  };

  const data: User[] = [
    {
      id: "m5gr84i9",
      date: "12-12-2012",
      status: "success",
      email: "ken99@yahoo.com",
    },
    // ...
  ];

  const table = createTable(readable(data), {
    filter: addTableFilter({
      fn: ({ filterValue, value }) =>
        value.toLowerCase().includes(filterValue.toLowerCase()),
    }),
  });

  const columns = table.createColumns([
    table.column({
      accessor: "id",
      header: "ID",
      plugins: {
        filter: {
          exclude: true,
        },
      },
    }),
    table.column({
      accessor: "status",
      header: "Status",
      plugins: {
        filter: {
          exclude: true,
        },
      },
    }),
    table.column({
      accessor: "email",
      header: "Email",
    }),
    table.column({
      accessor: "date",
      header: "Date",
      plugins: {
        filter: {
          exclude: true,
        },
      },
    }),
    table.column({
      accessor: ({ id }) => id,
      header: "",
      cell: ({ value }) => {
        return createRender(DataTableActions, { id: value });
      },
      plugins: {
        filter: {
          exclude: true,
        },
      },
    }),
  ]);

  const { headerRows, pageRows, tableAttrs, tableBodyAttrs, pluginStates } =
    table.createViewModel(columns);

  const { filterValue } = pluginStates.filter;
</script>

<div class="rounded-md border">
  <div class="flex items-center p-4">
    <Input
      class="max-w-sm"
      placeholder="Filter emails..."
      type="text"
      bind:value={$filterValue}
    />
  </div>
  <Table.Root {...$tableAttrs}>
    <Table.Header>
      {#each $headerRows as headerRow}
        <Subscribe rowAttrs={headerRow.attrs()}>
          <Table.Row>
            {#each headerRow.cells as cell (cell.id)}
              <Subscribe attrs={cell.attrs()} let:attrs props={cell.props()}>
                <Table.Head {...attrs}>
                  <Render of={cell.render()} />
                </Table.Head>
              </Subscribe>
            {/each}
          </Table.Row>
        </Subscribe>
      {/each}
    </Table.Header>
    <Table.Body {...$tableBodyAttrs}>
      {#each $pageRows as row (row.id)}
        <Subscribe rowAttrs={row.attrs()} let:rowAttrs>
          <Table.Row {...rowAttrs}>
            {#each row.cells as cell (cell.id)}
              <Subscribe attrs={cell.attrs()} let:attrs>
                <Table.Cell {...attrs}>
                  <Render of={cell.render()} />
                </Table.Cell>
              </Subscribe>
            {/each}
          </Table.Row>
        </Subscribe>
      {/each}
    </Table.Body>
  </Table.Root>
</div>
