<script lang="ts">
    import { Button, Dropdown, DropdownItem } from "flowbite-svelte";
    import { DrawSquareOutline } from "flowbite-svelte-icons";
    import OpenLayersMap from "./OpenLayersMap.svelte";
</script>

<div class="overflow-hidden">
    <OpenLayersMap/>
    <Button size="xs" color="light" class="absolute left-4 top-16"><DrawSquareOutline/></Button>
    <Dropdown>
        <DropdownItem>Dashboard</DropdownItem>
        <DropdownItem>Settings</DropdownItem>
        <DropdownItem>Earnings</DropdownItem>
        <DropdownItem slot="footer">Sign out</DropdownItem>
    </Dropdown>
</div>