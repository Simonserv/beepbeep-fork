<script>
    import "../app.css";
    import { Navbar, NavBrand, NavLi, NavUl, NavHamburger } from 'flowbite-svelte';
</script>

<Navbar>
    <NavBrand href="/">
        <!-- <img src="/images/flowbite-svelte-icon-logo.svg" class="me-3 h-6 sm:h-9" alt="Flowbite Logo" /> -->
        <span class="self-center whitespace-nowrap text-xl font-semibold dark:text-white">Beepbeep</span>
    </NavBrand>

    <NavHamburger/>

    <NavUl>
        <NavLi href="/">Home</NavLi>
        <NavLi href="/map">Map</NavLi>
    </NavUl>
</Navbar>