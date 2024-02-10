<template>
    <div class="h-screen bg-gradient-to-br from-pink-200 via-rose-100 to-rose-200">
        <div class="relative">
            <img v-for="(img, index) in flyingDivs" :key="index" :ref="'img_' + index"
                src="https://cdn-icons-png.flaticon.com/128/14623/14623208.png" class="w-10 h-10 absolute" />
        </div>
    </div>
</template>
  
<script>
export default {
    data() {
        return {
            flyingDivs: [],
            screenWidth: 0,
            screenHeight: 0,
        };
    },
    mounted() {
        this.screenWidth = window.innerWidth;
        this.screenHeight = window.innerHeight;
        this.generateFlyingDivs();
        this.animateDivs();
    },
    methods: {
        generateFlyingDivs() {
            for (let i = 0; i < 50; i++) {
                const img = {
                    left: Math.random() * (this.screenWidth - 100),
                    top: Math.random() * (this.screenHeight - 100),
                    velocityX: Math.random() * 2 - 1,
                    velocityY: Math.random() * 2 - 1,
                };
                this.flyingDivs.push(img);
            }
        },
        animateDivs() {
            setInterval(() => {
                this.flyingDivs.forEach((img, index) => {
                    img.left += img.velocityX * 5;
                    img.top += img.velocityY * 5;

                    if (
                        img.left < -100 ||
                        img.left > this.screenWidth ||
                        img.top < -100 ||
                        img.top > this.screenHeight
                    ) {
                        // Remove image from array when it goes out of bounds
                        this.flyingDivs.splice(index, 1);
                        // Generate a new image to replace the removed one
                        this.generateNewImage();
                    } else {
                        // Update image position
                        this.$refs['img_' + index][0].style.left = img.left + 'px';
                        this.$refs['img_' + index][0].style.top = img.top + 'px';
                    }
                });
            }, 1000 / 60); // 60 FPS
        },
        generateNewImage() {
            const newImg = {
                left: Math.random() * (this.screenWidth - 100),
                top: Math.random() * (this.screenHeight - 100),
                velocityX: Math.random() * 2 - 1,
                velocityY: Math.random() * 2 - 1,
            };
            this.flyingDivs.push(newImg);
        },
    },
};
</script>
  
<style>
/* You can add additional styling if needed */
</style>
  