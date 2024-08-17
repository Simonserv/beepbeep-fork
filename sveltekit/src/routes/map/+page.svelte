<script lang="ts">
    import { Avatar, Button, ButtonGroup, Dropdown, DropdownItem } from "flowbite-svelte";
    import { DrawSquareOutline, PlusOutline, WalletOutline } from "flowbite-svelte-icons";
    import OpenLayersMap from "./OpenLayersMap.svelte";
</script>

<div class="overflow-hidden h-screen relative flex z-0">
    <OpenLayersMap/>

    <div class="grid grid-cols-2">
        <!-- Top left drawer-->
        <Button size="xs" color="light" class="absolute left-4 top-4"><DrawSquareOutline/></Button>
        <Dropdown>
            <DropdownItem>Dashboard</DropdownItem>
            <DropdownItem>Settings</DropdownItem>
            <DropdownItem>Earnings</DropdownItem>
            <DropdownItem slot="footer">Sign out</DropdownItem>
        </Dropdown>

        <!-- Top right button group -->
        <ButtonGroup class="*:!ring-primary-700 absolute right-4 top-4">
            <Button size="xs">
                <div class="flex space-x-4 rtl:space-x-reverse">
                    <Avatar size="xs" src="https://s3-alpha.figma.com/hub/file/4338730091/25fd46ec-d7b2-4052-830e-674d22fe7f8c-cover.png" />
                </div>
            </Button>
            <Button size="xs" color="light" disabled >1020</Button>
            <Button size="xs" color="light"><PlusOutline/></Button>
            <Button size="xs" color="primary"><WalletOutline/></Button>
        </ButtonGroup>
    </div>
</div>