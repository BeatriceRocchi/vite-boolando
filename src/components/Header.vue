<script>
export default {
  data() {
    return {
      menuList: [
        {
          link: "#",
          title: "Donna",
        },
        {
          link: "#",
          title: "Uomo",
        },
        {
          link: "#",
          title: "Bambini",
        },
      ],
      iconList: [
        {
          style: "fa-regular",
          type: "fa-user",
        },
        {
          style: "fa-regular",
          type: "fa-heart",
        },
        {
          style: "fa-solid",
          type: "fa-bag-shopping",
        },
      ],
    };
  },
};
</script>

<template>
  <header>
    <div class="container">
      <nav>
        <ul class="menu">
          <li v-for="(item, id) in menuList" :key="id">
            <a :href="item.link">{{ item.title }}</a>
          </li>
        </ul>
      </nav>
      <img src="../assets/img/boolean-logo.png" alt="Logo boolean" />
      <div>
        <i
          v-for="(icon, id) in iconList"
          :key="id"
          :class="[icon.style, icon.type]"
        ></i>
      </div>
    </div>
  </header>
</template>

<style lang="scss" scoped>
@use "../assets/scss/partials/variables" as *;

header {
  background-color: $color-primary;
  color: $color-white;
  font-size: $font-m;
  height: 50px;
  width: 100%;
  position: fixed;
  z-index: 100;
  box-shadow: 0 3px 5px rgba($color-black, 0.4);

  .container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 100%;

    .menu {
      display: flex;
      justify-content: space-between;

      li {
        padding-right: 10px;

        &:hover {
          text-decoration: underline;
        }
      }
    }

    img {
      height: 25px;
    }

    i {
      padding-left: 10px;
    }
  }
}
</style>
