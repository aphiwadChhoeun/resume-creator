<script>
    import profilePic from "../assets/profile.jpg";
</script>

<div class="flex flex-row">
    <div class="pr-4 w-40 h-40 flex place-items-center print:invisible print:w-0 print:h-0 print:p-0">
        <img src={profilePic} alt="Yong Gao Picture" class="aspect-square rounded-full object-fill" />
    </div>

    <h1 class="text-5xl print:text-3xl self-center uppercase">
        <slot />
    </h1>
</div>
