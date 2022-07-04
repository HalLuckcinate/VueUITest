
<template>
  <div class=" bg-white font-mono text-black rounded-lg text-center">
    <p class=" bg-gradient-to-r from-blue-500 to-purple-600 text-2xl rounded-lg  text-white text-left p-3">Online call</p>

    <div class=" mt-4 text-center text-2xl font-bold pt-3">This chat has ended</div>

    <div class=" mt-4 text-center text-xl  pt-3">Thanks for chatting with us. Please review your previous call</div>

    <div class="p-5 flex space-x-8 items-center place-content-center mt-4 pb-5">
      <div class=" m-2  text-2xl flex-col px-2 font-mono">
        <p class="bg-green-600 rounded-full p-3">Icon 1</p>
        <p class="text-green-500">Like</p>
      </div>
      <div class=" m-2 rounded-md text-2xl flex-col px-2 font-mono">
        <p class="bg-red-600 rounded-full p-3">Icon 2</p>
        <p class="text-red-500">Dislike</p>
      </div>
  
    </div>
    <div class="mt-10">
      <a class=" text-2xl font-serif font-bold text-blue-500 mt-6 underline underline-offset-4" href="#">Report a problem</a>
      <p class=" p-5 mt-5">Made by C</p>

    </div>

  </div>

</template>

<script>
export default {
 name: "app"
}
</script>

<style>

</style>