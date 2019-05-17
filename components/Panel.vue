<template>
  <transition name="slide-left">
    <div class="generic-panel">
      <slot></slot>
    </div>
  </transition>
</template>

<style lang="scss">
.generic-panel {
  position: fixed;
  display: flex;
  width: 100%;
  z-index: 1081;
  top: 0;
  left: 0;
  height: 100vh;
  background-color: #fff;
  max-width: 15rem;
  box-shadow: 1px 0 3px 1px rgba(0, 0, 0, 0.2);
}

.slide {
  &-left {
    &-enter,
    &-leave-to {
      transform: translateX(-100%);
    }
  }

  &-right {
    &-enter,
    &-leave-to {
      transform: translateX(100%);
    }
  }

  &-left,
  &-right {
    &-enter {
      will-change: visibility, transform;
    }
    &-enter,
    &-leave {
      &-active {
        transition: {
          property: visibility, transform;
          duration: 1s;
          timing-function: ease;
        }
      }
    }
  }
}
</style>

