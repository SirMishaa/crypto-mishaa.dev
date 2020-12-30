<template>
  <div>
    <nav class="text-center">
      <h1
        class="animate-bounce mb-4 text-4xl font-extrabold leading-10 tracking-tight text-gray-900 sm:text-5xl sm:leading-none md:text-6xl mt-12"
      >
        Crypto<span class="text-red-600">Mishaa</span>
      </h1>
      <a
        class="text-sm font-bold tracking-wide text-gray-500 sm:text-base lg:text-sm xl:text-base"
        href="https://mishaa.dev"
        target="_blank"
        >A tool for analyzing crypto currency transactions</a
      >
    </nav>
    <main class="max-w-4xl sm:w-full mx-auto my-10">
      <ul class="flex justify-center border-b-2">
        <li class="ml-auto">
          <a
            style="font-size: 0.7rem"
            class="text-sm text-gray-800 px-4 uppercase border-b-2 border-red-600"
            href="#"
            >Standard</a
          >
        </li>
        <li>
          <a
            style="font-size: 0.7rem"
            class="text-sm text-gray-500 cursor-not-allowed px-4 uppercase"
            href="#"
            >Advanced</a
          >
        </li>
        <li class="ml-auto">
          <a
            style="font-size: 0.7rem"
            class="text-sm text-gray-500 cursor-not-allowed px-4 uppercase"
            href="#"
            >About</a
          >
        </li>
      </ul>
      <div class="flex items-center h-16 my-4">
        <input
          v-model="addressInput"
          style="font-size: 1rem"
          class="my-4 w-full custom--input p-4 h-full"
          type="text"
          placeholder="Transaction, address"
        />
        <button
          class="flex justify-center items-center text-white p-2 bg-red-600 h-full"
        >
          >
        </button>
      </div>
      <transition name="fade">
        <div v-if="addressInput" class="bg-red-100 w-full p-3 custom--card">
          <small class="text-red-500"
            >Un peu de patience, le serveur ne semble pas être encore
            disponible.</small
          >
        </div>
      </transition>
      <article class="w-full shadow-md rounded px-12 py-8">
        <h2 class="font-bold text-xl mb-8 text-gray-800">
          Informations about transaction
        </h2>
        <div class="custom--grid">
          <span class="my-2 py-2">Transaction ID</span>
          <span style="color: #888888" class="my-2 p-2"
            >e108b18463b56d00c8fd7c45eb7471552bb79c6f01815516fd10e9b683b786bc</span
          >
          <span class="my-2 py-2">Fees</span>
          <span style="color: #888888" class="my-2 p-2">0.00000501 LTC </span>

          <span class="my-2 py-2">Confirmations</span>
          <span style="color: #888888" class="my-2 p-2"
            >10 (Anything over 6 confirmations is considered completed and
            irreversible)</span
          >

          <span class="my-2 py-2">Relayed By:</span>
          <span style="color: #888888" class="my-2 p-2"
            >116.203.61.61:9333</span
          >

          <span class="my-2 py-2">Block hash</span>
          <span class="my-2 p-2 text-blue-400"
            >908c06d993af7f25395bd6597606c31b80b29b2c06833e42a00435bcbfad7da0</span
          >
        </div>
      </article>
    </main>
  </div>
</template>

<script>
export default {
  data() {
    return {
      addressInput: '',
    }
  },
}
</script>

<style>
.nav--title {
  font-size: 2rem;
}
.custom--input {
  outline: none;
  @apply shadow-md;
  /*box-shadow: 15px 20px 25px -5px rgba(0, 0, 0, 0.1),
    15px 10px 10px -5px rgba(229, 62, 62, 0.1);*/
  transition: all 0.1s ease-in-out;
  border: 1px solid rgba(255, 255, 255, 1);
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.2s ease-in-out;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
.custom--grid {
  display: grid;
  grid-template-columns: 1fr 1.5fr;
  grid-auto-columns: auto;
}
.custom--input:hover {
  border: 1px solid rgba(220, 220, 220, 0.5);
}
.custom--input:focus {
  @apply shadow-xl;
  outline: none;
  border: 1px solid rgba(220, 220, 220, 0.5);
  /*box-shadow: 15px 20px 25px -5px rgba(0, 0, 0, 0.1),
    15px 17px 10px -5px rgba(229, 62, 62, 0.1);*/
  /*border: 1px solid rgba(0, 0, 0, 0.05);*/
}
</style>
