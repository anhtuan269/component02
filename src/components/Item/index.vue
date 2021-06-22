<template lang="pug" >
.relative.bg-white.p-2.items-center.mb-3.border.rounded-xl.shadow-md.mx-auto(class="lg:mb-7",:class="classSeting.items" )

  .image.relative.rounded-xl.object-cover(:class="classSeting.imageWidth")

    img.rounded-lg.mr-2.w-full( class="lg:rounded-xl lg:object-cover", :class="classSeting.height", src="@/assets/image/police-scale.webp", alt="" )

  .content.p-5.text-left(:class="classSeting.contentWidth")

    .new-link.text-left
      a.bg-violet(href="#") {{ item.new }}

    .title.mb-5
      a.text-black.text-lg.font-bold(class="lg:text-xl", href="#")
        | {{ item.title }}

    p.text-sm(class="lg:mb-8", :class="classSeting.description") {{ item.description }}

    div(:class="classSeting.authContent")

      .avatar.flex.items-center.justify-center.mr-5( :class="classSeting.avatarBackgound" )

        img.rounded-full.w-10( :class="classSeting.avatar", src="@/assets/image/jane-smith.webp", alt="" )

    .info(class="lg:inline-block", :class="classSeting.auth")

      h3.name.text-gray-500.font-weight.text-xs.font-bold( class="lg:text-sm lg:mb-2 lg:text-left" )
        | {{ item.name }}

      .time.text-xs.text-gray-400.flex(class="lg:text-sm")

        span
          | {{ item.day }}
          sup.text-gray-600.text-sm(:class="classSeting.sup") .
        span.ml-4(:class="classSeting.clock")
          img.w-5.mr-2(src="@/assets/image/clock1.svg", alt="")
          span {{ item.time }}
</template>

<script>
export default {
  props: {
    item: {
      type: Object,
    },

    image_position: {
      
      validation(value) {
        return ["top", "left", "right", "bottom"].indexOf(value) !== -1;
      }
    },
  },
  computed: {
    classSeting() {
      var allsetting = {
        left: {
          items: "flex  xl:max-w-5xl",
          imageWidth: "w-5/12",
          height: " lg:h-72 ",
          avatarBackgound: " hidden lg:flex ",
          sup: "hidden lg:inline-block lg:ml-3",
          authContent: "  lg:flex lg:items-center ",
          clock: " hidden lg:flex  ",
          contentWidth: " w-7/12",
          avatar: " hidden lg:flex lg:items-center  lg:justify-center ",
          description: " hidden lg:block",
          auth: "flex justify-between items-center lg:inline-block ",
        },
        top: {
          items: "lg:max-w-md",
          imageWidth: "w-full",
          height: "",
          avatarBackgound: "inline-block",
          sup: "ml-3",
          authContent: "flex items-center",
          clock: "flex ",
          contentWidth: "w-full",
          avatar: " flex justify-center items-center  ",
          description: " mb-5",
          auth: "",
        },
         right: {
          items: "flex flex-row-reverse  xl:max-w-5xl",
          imageWidth: "w-5/12",
          height: " lg:h-72 ",
          avatarBackgound: " hidden lg:flex ",
          sup: "hidden lg:inline-block lg:ml-3",
          authContent: "  lg:flex lg:items-center ",
          clock: " hidden lg:flex  ",
          contentWidth: " w-7/12",
          avatar: " hidden lg:flex lg:items-center  lg:justify-center ",
          description: " hidden lg:block",
          auth: "flex justify-between items-center lg:inline-block ",
        },
         bottom: {
          items: " flex flex-col-reverse lg:max-w-md",
          imageWidth: "w-full",
          height: "",
          avatarBackgound: "inline-block",
          sup: "ml-3",
          authContent: "flex items-center",
          clock: "flex ",
          contentWidth: "w-full",
          avatar: " flex justify-center items-center  ",
          description: " mb-5",
          auth: "",
         }
      };
      return allsetting[this.image_position] || allsetting.top;
    },
  },
};
</script>

<style>
.new-link {
  margin-bottom: 10px;
}
.new-link a {
  font-size: 0.75rem;
  border-radius: 0.5rem;
  background-color: #e9d8fd;
  color: #2d3748;
  padding: 0.25rem 0.8rem;
  -webkit-transition: all 0.3s ease-in-out;
  transition: all 0.3s ease-in-out;
}
.new-link a:hover {
  color: #e2e8f0;
  background-color: #718096;
}
.avatar {
  width: 48px;
  height: 48px;
  border-radius: 50%;
  background: #e2e8f0;
}
</style>