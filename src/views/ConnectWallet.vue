<template>
  <div class="p-sm-2">
    <div class="my-3 pb-2">
      <div>
        <h1>connect wallet</h1>
        <p>
          Connect your Bitcoin or Lightning wallet to your Umbrel
        </p>
      </div>
    </div>
    <b-row>
      <b-col cols="12" md="4" xl="3">
        <b-form-select
          :value="wallet"
          :options="options"
          @change="selectWallet"
          class="mb-4"
        ></b-form-select>
      </b-col>
    </b-row>
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  data() {
    return {
      selected: null,
      options: [
        { value: null, text: "Select your wallet", disabled: true },
        {
          label: "Bitcoin",
          options: [
            { value: "bitboxapp", text: "BitBoxApp" },
            {
              value: "blockstream-green-android",
              text: "Blockstream Green (Android)"
            },
            { value: "bluewallet-android", text: "BlueWallet (Android)" },
            { value: "specter-desktop", text: "Specter Desktop" }
          ]
        },
        {
          label: "Bitcoin (Custom)",
          options: [
            { value: "bitcoin-core-p2p", text: "Bitcoin Core P2P" },
            { value: "bitcoin-core-rpc", text: "Bitcoin Core RPC" },
            { value: "electrum-server", text: "Electrum Server" }
          ]
        },
        {
          label: "Lightning",
          options: [
            { value: "zap-android", text: "Zap (Android)" },
            { value: "zap-desktop", text: "Zap (Desktop)" },
            { value: "zap-ios", text: "Zap (iOS)" }
          ]
        }
      ]
    };
  },
  computed: {
    wallet() {
      return this.$route.meta.wallet || null;
    }
    // ...mapState({
    //   version: state => state.system.version,
    //   onionAddress: state => state.system.onionAddress,
    //   availableUpdate: state => state.system.availableUpdate,
    //   updateStatus: state => state.system.updateStatus,
    //   backupStatus: state => state.system.backupStatus
    // }),
  },
  created() {},
  methods: {
    selectWallet(wallet) {
      this.$router.push(`/connect/${wallet}`);
    }
  },
  watch: {},
  components: {}
};
</script>

<style lang="scss" scoped></style>
