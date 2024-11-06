<script lang="ts">
  import {
    createTable,
    Render,
    Subscribe,
    createRender,
  } from "svelte-headless-table";
  import { readable } from "svelte/store";
  import { addPagination } from "svelte-headless-table/plugins";
  import { Button } from "$lib/components/ui/button";
  import * as Table from "$lib/components/ui/table";
  import DataTableUsersAction from "./data-table-users-action.svelte";

  type Users = {
    id: string;
    email: string;
    firstName: string;
    lastName: string;
    role: "Owner" | "Admin" | "Member";
  };

  const data: Users[] = [
    {
      id: "1",
      email: "64070047@kmitl.ac.th",
      firstName: "Thavith",
      lastName: "Javisooth",
      role: "Owner",
    },
    {
      id: "2",
      email: "64070011@kmitl.ac.th",
      firstName: "Khemmathiti",
      lastName: "Wangsaptawee",
      role: "Owner",
    },
    {
      id: "3",
      email: "64070000@kmitl.ac.th",
      firstName: "Somjai",
      lastName: "Mairu",
      role: "Member",
    },
    {
      id: "4",
      email: "gugokgik@kmitl.ac.th",
      firstName: "Poppy",
      lastName: "Peepop",
      role: "Admin",
    },
  ];

  const table = createTable(readable(data), {
    page: addPagination({
        initialPageSize: 5,
    }),
  });

  const columns = table.createColumns([
    table.column({
      accessor: "id",
      header: "ID",
    }),
    table.column({
      accessor: "email",
      header: "Email",
    }),
    table.column({
      accessor: "firstName",
      header: "First Name",
    }),
    table.column({
      accessor: "lastName",
      header: "Last Name",
    }),
    table.column({
      accessor: "role",
      header: "Role",
    }),
    table.column({
      accessor: ({ id }) => id,
      header: "Actions",
      cell: ({ value }) => {
        return createRender(DataTableUsersAction);
      },
    }),
  ]);

  const { headerRows, pageRows, tableAttrs, tableBodyAttrs, pluginStates } =
    table.createViewModel(columns);

  const { hasNextPage, hasPreviousPage, pageIndex } = pluginStates.page;
</script>

<div>
  <div class="rounded-md border">
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
  <div class="flex items-center justify-end space-x-4 py-4">
    <Button
      variant="outline"
      size="sm"
      on:click={() => ($pageIndex = $pageIndex - 1)}
      disabled={!$hasPreviousPage}>Previous</Button
    >
    <Button
      variant="outline"
      size="sm"
      disabled={!$hasNextPage}
      on:click={() => ($pageIndex = $pageIndex + 1)}>Next</Button
    >
  </div>
</div>
