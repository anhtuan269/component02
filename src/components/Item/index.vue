<template>
  <div
    class="relative bg-white p-2 items-center mb-3 border rounded-xl shadow-md lg:mb-7 mx-auto"
    :class="items"
  >
    <div class="image relative rounded-xl object-cover" :class="imageWidth">
      <img
        class=" rounded-lg mr-2 w-full lg:rounded-xl lg:object-cover"
        :class="height"
        src="@/assets/image/police-scale.webp"
        alt=""
      />
    </div>

    <div class="content p-5 text-left" :class="contentWidth">
      <div class="new-link text-left">
        <a class="bg-violet" href="#">{{ item.new }} </a>
      </div>

      <div class="title mb-5">
        <a class="text-black text-lg font-bold lg:text-xl" href="#">
          {{ item.title }}
        </a>
      </div>

      <p class="lg:mb-8 text-sm" :class="description">{{ item.description }}</p>

      <div class="" :class="authContent">
        <div class="avatar flex items-center justify-center mr-5"
        :class="avatarBackgound"
        >
          <img
            class=" rounded-full w-10"
            :class="avatar"
            src="@/assets/image/jane-smith.webp"
            alt=""
          />
        </div>

        <div class="info lg:inline-block" :class="auth"> 
          <h3 class=" name text-gray-500 font-weight text-xs font-bold lg:text-sm lg:mb-2 lg:text-left ">
            {{ item.name }}
          </h3>

          <div class="time text-xs text-gray-400 lg:text-sm flex">
            <span>
              {{ item.day }}
              <sup class="text-gray-600 text-sm"
              :class="sup"
              >.</sup>
            </span>

            <span class="ml-4" :class="clock">
              <img class="w-5 mr-2" src="@/assets/image/clock1.svg" alt="" />
              <span> {{ item.time }}</span>
            </span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    item: {
      type: Object,
    },
    vertical: {
      type: Boolean,
    },
  },
  computed: {

    items() {
      if (this.vertical === true) {
        return " flex  xl:max-w-5xl";
      } else {
        return "lg:max-w-md";
      }
    },
    imageWidth() {
      if (this.vertical === true) {
        return " w-5/12 ";
      } else {
        return "w-full";
      }
    },
    height() {
        if (this.vertical === true) {
        return " lg:h-72 ";
      } else {
        return "";
      }
    },
     avatarBackgound() {
      if (this.vertical === true) {
        return " hidden lg:flex ";
      } else {
        return "inline-block";
      }
    },
     sup() {
      if (this.vertical === true) {
        return " hidden lg:inline-block lg:ml-3 ";
      } else {
        return "ml-3";
      }
    },
    authContent() {
      if (this.vertical === true) {
        return "  lg:flex lg:items-center ";
      } else {
        return "flex items-center";
      }
    },
    clock() {
      if (this.vertical === true) {
        return " hidden lg:flex  ";
      } else {
        return "flex ";
      }
    },
    contentWidth() {
      if (this.vertical === true) {
        return " w-7/12";
      } else {
        return "w-full";
      }
    },
    avatar() {
      if (this.vertical === true) {
        return " hidden lg:flex lg:items-center  lg:justify-center ";
      } else {
        return " flex justify-center items-center  ";
      }
    },
    description() {
      if (this.vertical === true) {
        return " hidden lg:block";
      } else {
        return " mb-5";
      }
    },
    auth() {
      if (this.vertical === true) {
        return "flex justify-between items-center lg:inline-block ";
      } else {
        return "";
      }
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