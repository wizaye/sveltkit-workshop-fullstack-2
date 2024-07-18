<script lang="ts">
  import { PrivateKey } from '@bsv/sdk';

  let WIF: string;
  let address: string;

  function createKeys() {
    const privKey = PrivateKey.fromRandom();
    WIF = privKey.toWif();
  //   console.log("Private Key WIF format is ", WIF);
    address = privKey.toAddress();
  //   console.log("Your bitcoin address is ", address);
  }
</script>

<section class="flex flex-col items-center mt-20 space-y-4">
  <div class="text-center">
    <p class="text-lg font-semibold">Private Key WIF format is:</p>
    <p class="text-sm text-gray-700">{WIF}</p>
    <p class="text-lg font-semibold mt-4">Your Bitcoin Address is:</p>
    <p class="text-sm text-gray-700">{address}</p>
  </div>
  <button class="bg-black text-white px-4 py-2 rounded" on:click={createKeys}>
    Generate New Wallet Keys
  </button>
</section>
