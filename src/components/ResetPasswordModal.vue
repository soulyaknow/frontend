<template>
    <div class="fixed inset-0 bg-gray-900 bg-opacity-60 items-center justify-center font-poppins z-40" v-if="modalStore.resetPasswordModal">
      <div class="relative p-5 bg-white md:max-w-[30rem] max-w-full mx-auto md:mt-52 mt-32 border-4 border-sky-950 rounded-xl max-h-[50rem] overflow-y-auto">
            <h1 class="text-[25px] font-bold"><span class="border-b-2 border-sky-900">Res</span>et Password</h1>
            <div class="flex flex-col mt-4 w-full h-full">
                <div class="pb-4">
                    <label for="fname" class="font-semibold">New Password</label>
                    <input type="text" placeholder="Enter Your New Password...." class="capitalize border rounded w-full h-10 pl-2">
                </div>
                <div class="pb-4">
                    <label for="mname" class="font-bold">Repeat New Password</label>
                    <input type="text" placeholder="Repeat Your New Password...." class="capitalize border rounded w-full h-10 pl-2">
                </div>
            </div>
            <div>
                Not Matched
            </div>
            <div class="flex justify-end mt-4 items-center gap-5">
                <button class="bg-sky-950 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded" @click="modalStore.showResetPasswordModal">
                    Close
                </button>
                <button @click="handleSave" class="bg-sky-950 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded disabled:bg-sky-900">
                    Save 
                </button>
            </div>

            <transition-group name="fade">
            <ActionSpinnerAnimation key=1 v-if="showActionSpinner"/>
            <ActionModal key=2 v-if="showActionModal"/>
            </transition-group>
        </div>
    </div>
</template>
<script setup>
import {ref} from "vue"
import { userModalStore } from '../stores/modalStore';
import ActionSpinnerAnimation from "./ActionSpinnerAnimation.vue";
import ActionModal from "./ActionModal.vue";

const showActionSpinner = ref(false);
const showActionModal = ref(false);

const password = ref('');
const newpassword = ref('')

const modalStore = userModalStore();


const handleSave = ()=>{
    if(password.value !== newpassword.value){

    }
}

</script>

<style scoped>
</style>