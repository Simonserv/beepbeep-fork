<script lang="ts">
    import { Avatar, Button, ButtonGroup, Card, Dropdown, DropdownItem } from "flowbite-svelte";
    import { IconMapPinFilled } from "@tabler/icons-svelte";
    import { IconArrowsUpDown, IconShape, IconDotsVertical, IconPlus, IconWallet } from "@tabler/icons-svelte";

    import OpenLayersMap from "./OpenLayersMap.svelte";

    const BUTTON_GRID = {
        "Restaurant": "resto-icon",
        "Gym": "gym-icon",
        "Hospital": "hospital-icon",
        "Mall": "mall-icon",
        "Pet Shop": "pet-icon",
        "Beach": "beach-icon",
        "Library": "library-icon",
        "See more": "seemore-icon",
    }

    let source_location_first = true;

    function switch_location_inputs() {
        source_location_first = !source_location_first;
        console.log(source_location_first);
    }
</script>

<div class="overflow-hidden h-screen relative flex z-0">
    <OpenLayersMap/>

    <div class="grid grid-cols-2">
        <!-- Top left drawer-->
        <Button size="xs" color="light" class="absolute left-4 top-4"><IconShape/></Button>
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
            <Button size="xs" color="light"><IconPlus/></Button>
            <Button size="xs" color="primary"><IconWallet/></Button>
        </ButtonGroup>
    </div>


    <!--
        Buttom navigation card with:
        + start/end point
        + current location buttons
        + suggested travel destination
    -->
    <Card class="absolute m-auto bottom-4 left-0 right-0 mt-4">
        <div class="grid grid-cols-[1fr_3fr_1fr] mb-8">
            <!-- Left side -->
            <div class="grid grid-rows-3 justify-center">
                <Button pill={true} class="!w-fit !h-fit !p-2" ><IconMapPinFilled class="h-4 w-4" /></Button>
                <div class=""> <IconDotsVertical /> </div>
                <Button pill={true} class="!w-fit !h-fit !p-2"><IconMapPinFilled class="h-4 w-4" /></Button>
            </div>

            <!-- Middle side -->
            <div class="grid grid-rows-3">
                {#if source_location_first}
                <Button pill={true} color="alternative" size="xs">
                    <div class="text-xs">
                        <span>Where to?</span>
                        <span>Choose destination</span>
                    </div>
                </Button>
                <div></div>
                <Button pill={true} color="alternative" size="xs">
                    <div class="text-xs">
                        <span>Choose starting location</span>
                    </div>
                </Button>
                {:else}
                <Button pill={true} color="alternative" size="xs">
                    <div class="text-xs">
                        <span>Choose starting location</span>
                    </div>
                </Button>
                <div></div>
                <Button pill={true} color="alternative" size="xs">
                    <div class="text-xs">
                        <span>Where to?</span>
                        <span>Choose destination</span>
                    </div>
                </Button>
                {/if}
            </div>

            <!-- Right side -->
            <div class="grid grid-rows-3">
                <div></div>
                <button on:click={switch_location_inputs}> <IconArrowsUpDown on:click={switch_location_inputs} /> </button>
                <div></div>
            </div>
        </div>

        <div class="inline-flex items-center justify-center w-full mb-4">
            <hr class="w-full h-px bg-gray-200 border-0 dark:bg-gray-700"/>
        </div>

        <div>
            Suggested Travel Destinations
        </div>

        <div class="grid grid-rows-2 grid-cols-4">
            {#each Object.entries(BUTTON_GRID) as [name, icon]}
            <div class="grid grid-rows-2">
                <Button color="alternative" size="xs">{icon}</Button>
                {name}
            </div>
            {/each}
        </div>
    </Card>

</div>