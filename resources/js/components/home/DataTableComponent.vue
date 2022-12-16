<template>
    <div class="p-6">
        <DataTable
            class="display"
            :columns="columns"
            ajax="api/users"
            ref="table"
            :options="{
                select: true,
                serverSide: true,
            }"
        >
            <thead>
            <tr>
                <th>ID</th>
                <th>Name</th>
                <th>Email</th>
                <th>Action</th>
            </tr>
            </thead>
            <tbody>
            </tbody>
        </DataTable>
    </div>
</template>

<script>
import DataTable from 'datatables.net-vue3'
import DataTablesLib from 'datatables.net';

DataTable.use(DataTablesLib);

export default {
    name: 'DataTableComponent',
    components: {DataTable},
    data(){
        return {
            columns: [
                {"data": "id"},
                {"data": "name"},
                {"data": "email"},
                {"data": "action", "sortable": false},
            ],
        }
    },
}
</script>

<style>
@import 'datatables.net-dt';
</style>
