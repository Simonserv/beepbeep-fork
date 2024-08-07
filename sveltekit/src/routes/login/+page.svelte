<script>
    import BeepbeepLogo from "./BeepbeepLogo.svelte";
    import { Button, Card } from 'flowbite-svelte';
</script>

<!-- Logo + Name -->
<BeepbeepLogo/>

<!-- Let's get started -->
<h1 class="mt-10 text-white text-center text-4xl">
    Let's get started!
</h1>

<!--
    Sign in 
    - SocMed Options
    - --- OR ---
    - Sign in with Password
-->

<!-- `absolute m-auto left-0 right-0` is used for horizontally centering the card. -->
<Card class="absolute m-auto left-0 right-0 mt-4">
    <div class="grid space-y-4">
        <h5 class="text-xl text-center tracking-tight text-gray-900 dark:text-white">Sign in</h5>
        <Button size="sm" color="light" class="mx-10">Continue with Facebook</Button>
        <Button size="sm" color="light" class="mx-10">Continue with Google</Button>
        <Button size="sm" color="light" class="mx-10">Continue with Twitter</Button>

        <div class="inline-flex items-center justify-center w-full">
            <hr class="w-64 h-px my-8 bg-gray-200 border-0 dark:bg-gray-700">
            <span class="absolute px-3 font-medium text-gray-900 -translate-x-1/2 bg-white left-1/2 dark:text-white dark:bg-gray-800">OR</span>
        </div>

        <div class="grid space-y-1">
            <Button size="sm" class="mx-10">Sign in with password</Button>
            <h5 class="text-xs text-center tracking-tight">
                Don't have an account?
                <span class="text-orange-300">
                    <a href="/signup">Sign up</a>
                </span>
            </h5>
        </div>
    </div>
</Card>