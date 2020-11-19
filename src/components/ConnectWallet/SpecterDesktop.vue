<template>
  <card-widget header="Instructions to connect Specter Desktop to your Umbrel">
    <div class="px-3 px-lg-4 pb-3">
      <ol class="pl- connect-wallet-steps">
        <li class="connect-wallet-step">
          Make sure Tor is up and running on your system.
          <b-link v-b-modal.tor-modal>Click here</b-link> for instructions.
        </li>
        <li class="connect-wallet-step">
          Open Specter Desktop and click
          <span class="font-weight-bold">"Configure Node"</span>.
        </li>
        <li class="connect-wallet-step">
          Disable <span class="font-weight-bold">"Auto-detect"</span>.
        </li>
        <li class="connect-wallet-step">
          In the <span class="font-weight-bold">"Username"</span> enter umbrel.
        </li>
        <li class="connect-wallet-step">
          In the <span class="font-weight-bold">"Password"</span>, enter
          9wQN3UbG7hp3L2MB2Mz8gsC0V9ezQdJiUcyt2Wu_CIw.
        </li>
        <li class="connect-wallet-step">
          In the <span class="font-weight-bold">"Host"</span>, enter
          http://ubrouzrcygw4vx6tfmpnywv43jjcfo4nsnvywacjmrcqkabopsd5rvid.onion
        </li>
        <li class="connect-wallet-step">
          In the <span class="font-weight-bold">"Port"</span>, enter 8332.
        </li>
        <li class="connect-wallet-step">
          Click <span class="font-weight-bold">"Test"</span> to verify if
          Specter is able to connect to your Umbrel.
        </li>
        <li class="connect-wallet-step">
          After verifying, click <span class="font-weight-bold">"Save"</span>.
        </li>
        <li class="connect-wallet-step">
          Congratulations! You have successfully connected Specter Desktop to
          your Umbrel.
        </li>
      </ol>
    </div>
    <b-modal id="tor-modal" title="Tor">
      <p class="my-4">Hello from modal!</p>
    </b-modal>
  </card-widget>
</template>

<script>
import CardWidget from "@/components/CardWidget";

export default {
  components: {
    CardWidget,
  },
};
</script>