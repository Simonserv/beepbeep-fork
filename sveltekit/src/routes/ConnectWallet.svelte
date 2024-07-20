<script lang="ts">
    // import { AnchorProvider, Program, web3 } from "@coral-xyz/anchor";
    import { Button } from 'flowbite-svelte';
    
    const getProvider = () => { // gets instance of wallet from Phantom
        const { 
          phantom: { solana },
        } = window as any;
        return solana;
    };

    let address:string;

    const onConnectWallet = async () => {
        const provider = getProvider();

        try {
          const resp = await provider.connect();
          address = resp.publicKey.toString();
        } catch (e) {
          alert(e);
        }
    };

</script>

{#if address}
    <Button on:click={onConnectWallet}>{address}</Button>
{:else}
    <Button on:click={onConnectWallet}>Connect Wallet</Button>
{/if}
