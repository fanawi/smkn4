<template>
    <div class="paddingX bg-base-200 text-base-content p-10">
        <footer class="footer">
            <nav>
                <h6 class="footer-title">Location</h6>
                <iframe
                    src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3957.2131162969818!2d108.254474!3d-7.329945299999999!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x2e6f59eeb6bda36f%3A0xa9e724a275da6c2d!2sSMK%20Negeri%204%20Tasikmalaya!5e0!3m2!1sid!2sid!4v1735548537847!5m2!1sid!2sid"
                    width="400" height="300" style="border:0;" allowfullscreen="" loading="lazy"
                    referrerpolicy="no-referrer-when-downgrade"></iframe>
            </nav>
            <nav>
                <h6 class="footer-title">Contact</h6>
                <div class="flex justify-center items-center gap-1 border-l-2 border-[#11224e] ps-5">
                    <Icon name="ion:ios-telephone" size="1.5rem" />
                    <a title="Nomor Telepon Sekolah" href="tel:+62265312059"
                        class="hover:text-[#264595]">+62-265-312-059</a>
                </div>
                <div class="flex justify-center items-center gap-1 border-l-2 border-[#11224e] ps-5">
                    <Icon name="material-symbols:mail" size="1.5rem" />
                    <a title="Email Sekolah" href="info@smkn4-tsm.sch.id"
                        class="hover:text-[#2c52b3]">info@smkn4-tsm.sch.id</a>
                </div>
            </nav>
            <nav>   
                <h6 class="footer-title">Link eksternal</h6>
                <a class="link link-hover">Kemendikbud</a>
                <a class="link link-hover">Dapodikdasmen</a>
                <a class="link link-hover">PSMK</a>
                <a class="link link-hover">Disdik Jabar</a>
            </nav>
        </footer>
        <footer class="footer bg-base-200 text-base-content border-base-300 border-t ">
            <aside class="grid-flow-col items-center mt-5">
                <p>
                    © Copyright 2025 SMKN 4 TASIKMALAYA
                </p>
            </aside>
            <nav class="md:place-self-center md:justify-self-end">
                <div class="grid grid-flow-col gap-4">
                    <div class="Alternatif flex items-center  border-[#11224e] ps-5 gap-5">
                        <div class="Sosmed flex justify-center items-center gap-5">
                            <a title="Facebook" href="http://"
                                class="group rounded-full border border-[#264595] shadow-md w-10 h-10 flex justify-center items-center transition-all duration-150 hover:bg-[#3b5998]">
                                <Icon name="line-md:facebook" size="1.5rem" class="group-hover:text-white" />
                            </a>
                            <a title="Tiktok" href="http://"
                                class="group rounded-full border border-[#264595] shadow-md w-10 h-10 flex justify-center items-center transition-all duration-150 hover:bg-[#000000]">
                                <Icon name="ic:sharp-tiktok" size="1.5rem" class="group-hover:text-white" />
                            </a>
                            <a title="YouTube" href="http://"
                                class="group rounded-full border border-[#264595] shadow-md w-10 h-10 flex justify-center items-center transition-all duration-150 hover:bg-[#b60101]">
                                <Icon name="mynaui:brand-youtube-solid" size="1.5rem" class="group-hover:text-white" />
                            </a>
                            <a title="Instagram" href="http://"
                                class="group rounded-full border border-[#264595] shadow-md w-10 h-10 flex justify-center items-center transition-all duration-150 hover:bg-[#f46f30]">
                                <Icon name="hugeicons:instagram" size="1.5rem" class="group-hover:text-white" />
                            </a>
                            <a title="X" href="http://"
                                class="group rounded-full border border-[#264595] shadow-md w-10 h-10 flex justify-center items-center transition-all duration-150 hover:bg-[#000000]">
                                <Icon name="hugeicons:new-twitter" size="1.5rem" class="group-hover:text-white" />
                            </a>
                        </div>
                    </div>
                </div>
            </nav>
        </footer>
    </div>
</template>

<script setup>

</script>

<style scoped></style>