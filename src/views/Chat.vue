

<template>
  <div class="bg-white text-center text-black my-3 rounded-lg font-mono">
    <p class="text-3xl bg-gradient-to-r from-blue-500 to-purple-600 p-2 rounded-lg text-left text-white">Let's chat!</p>
    <div class="p-2">

        <p class="text-xl font-bold m-4 p-3">Please fill in the information form below to continue</p>

        <div class="p-3">
            <input type="text" placeholder="Name" class="text-2xl border-4 p-1
            border-t-blue-500 border-l-blue-500 border-r-purple-500 border-b-purple-500 rounded-full">
        </div>


        <div class="p-3">
            <input type="text" placeholder="Email" class="text-2xl border-4 p-1
            border-t-blue-500 border-l-blue-500 border-r-purple-500 border-b-purple-500 rounded-full" >
        </div>

        <div class="">
            <select name="select" id="select" class="border-4 border-t-blue-500 border-l-blue-500 border-r-purple-500 border-b-purple-500  text-2xl p-2 rounded-full px-5 m-4">
                <option value="0" class="text-black">Select Option:</option>
                <option value="1" class="text-black">Option 1 </option>
                <option value="2" class="text-black">Option 2 </option>
            </select>

        </div>
        
        <button class="bg-gradient-to-r from-blue-500 to-purple-600 rounded-full text-white text-2xl p-3 px-6 m-6">Start Chat</button>

        <p>Powered by C</p>
    </div>
    
  </div>
</template>

<script>
export default {

}
</script>

<style>

</style>