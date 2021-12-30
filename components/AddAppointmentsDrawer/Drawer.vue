<template>
  <div
    id="sidebar-right"
    tabindex="-1"
    role="dialog"
    aria-modal="false"
    aria-labelledby="sidebar-right___title__"
    class="b-sidebar shadow b-sidebar-right bg-light text-dark"
    style=""
  >
    <header class="b-sidebar-header">
      <button type="button" aria-label="Close" class="close text-dark">
        <svg
          viewBox="0 0 16 16"
          width="1em"
          height="1em"
          focusable="false"
          role="img"
          aria-label="x"
          xmlns="http://www.w3.org/2000/svg"
          fill="currentColor"
          class="bi-x b-icon bi"
        >
          <g>
            <path
              d="M4.646 4.646a.5.5 0 0 1 .708 0L8 7.293l2.646-2.647a.5.5 0 0 1 .708.708L8.707 8l2.647 2.646a.5.5 0 0 1-.708.708L8 8.707l-2.646 2.647a.5.5 0 0 1-.708-.708L7.293 8 4.646 5.354a.5.5 0 0 1 0-.708z"
            ></path>
          </g>
        </svg></button
      ><strong id="sidebar-right___title__"></strong>
    </header>
    <div class="b-sidebar-body">
      <div class="px-3 py-2">

        {{firstName}}
      </div>
    </div>
    <!---->
  </div>
</template>

<script>
export default {
  props:{
    firstName:String
  }
};
</script>

<style></style>
