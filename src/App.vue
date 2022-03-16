<template>
  <ProductShow />
</template>

<script>
import ProductShow from './Product/ProductShow.vue'

export default {
  name: 'GradiTest',
  components: {
    ProductShow
  }
}
</script>

<style lang="scss">
// Color
// ––––––––––––––––––––––––––––––––––––––––––––––––––
$color-initial: #fff !default;
$color-primary: #0e060f !default;
$color-secondary: #858c92 !default;
$color-tertiary: #f4f5f6 !default;
$color-quaternary: #d1d1d1 !default;
$color-quinary: #e1e1e1 !default;
$tablet: 768px;
$desktop: 960px;
$phone: 480px;
:root{
  --color-initial: #{$color-initial};
  --color-primary: #{$color-primary};
  --color-secondary: #{$color-secondary};
  --color-tertiary: #{$color-tertiary};
  --color-quaternary: #{$color-quaternary};
  --color-quinary: #{$color-quinary};
  --tablet: #{$tablet};
  --desktop: #{$desktop};
  --phone: #{$phone};
}
*, *:after, *:before{
  box-sizing: inherit;
}
@import url('https://fonts.googleapis.com/css2?family=Raleway:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');

  // The base font-size is set at 62.5% for having the convenience
  // of sizing rems in a way that is similar to using px: 1.6rem = 16px
html{
  box-sizing: border-box;
  font-size: 62.5%;
}
body{
  color: $color-primary;
  font-family: 'Raleway', 'Helvetica Neue', 'Helvetica', 'Arial', sans-serif;
  font-size: 1.6em; // Currently ems cause chrome bug misinterpreting rems on body element
  font-weight: 300;
  letter-spacing: .01em;
  line-height: 1.6;
}
hr{
  display: block; height: 1px;
  border: 0; border-top: 1px solid #ccc;
  margin: 1em 0; padding: 0;
}
.container {
  margin: 0 auto;
  max-width: 112.0rem;
  padding: 0 2.0rem;
  position: relative;
  width: 100%;
}
.noselect {
  -webkit-touch-callout: none; /* iOS Safari */
  -webkit-user-select: none; /* Safari */
  -khtml-user-select: none; /* Konqueror HTML */
  -moz-user-select: none; /* Old versions of Firefox */
  -ms-user-select: none; /* Internet Explorer/Edge */
  user-select: none; /* Non-prefixed version, currently
                                  supported by Chrome, Edge, Opera and Firefox */
}
.wrapper{

  width: 90vw!important;
  margin: 4rem auto 0 auto !important;

}
.row {
  display: flex;
  flex-direction: column;
  padding: 0;
  width: 100%;

  &.row-no-padding {
    padding: 0;

    > .column {
      padding: 0;
    }
  }

  &.row-wrap {
    flex-wrap: wrap;
  }

  &.row-top {
    align-items: flex-start;
  }

  &.row-bottom {
    align-items: flex-end;
  }

  &.row-center {
    align-items: center;
  }

  &.row-stretch {
    align-items: stretch;
  }

  &.row-baseline {
    align-items: baseline;
  }

  .column {
    display: block;
    flex: 1 1 auto;
    margin-left: 0;
    max-width: 100%;
    width: 100%;
    &.column-offset-5 {
      margin-left: 10%;
    }
    &--left{
      flex: 0 0 50%;
      max-width: 50%;
    }
    &--right{
      flex: 0 0 40%;
      max-width: 40%;
      margin-left: 5%;
    }

    &.column-offset-10 {
      margin-left: 10%;
    }

    &.column-offset-20 {
      margin-left: 20%;
    }

    &.column-offset-25 {
      margin-left: 25%;
    }

    &.column-offset-33, &.column-offset-34 {
      margin-left: 33.3333%;
    }

    &.column-offset-40 {
      margin-left: 40%;
    }

    &.column-offset-50 {
      margin-left: 50%;
    }

    &.column-offset-60 {
      margin-left: 60%;
    }

    &.column-offset-66, &.column-offset-67 {
      margin-left: 66.6666%;
    }

    &.column-offset-75 {
      margin-left: 75%;
    }

    &.column-offset-80 {
      margin-left: 80%;
    }

    &.column-offset-90 {
      margin-left: 90%;
    }

    &.column-10 {
      flex: 0 0 10%;
      max-width: 10%;
    }

    &.column-20 {
      flex: 0 0 20%;
      max-width: 20%;
    }

    &.column-25 {
      flex: 0 0 25%;
      max-width: 25%;
    }

    &.column-33, &.column-34 {
      flex: 0 0 33.3333%;
      max-width: 33.3333%;
    }

    &.column-40 {
      flex: 0 0 40%;
      max-width: 40%;
    }

    &.column-50 {
      flex: 0 0 50%;
      max-width: 50%;
    }

    &.column-60 {
      flex: 0 0 60%;
      max-width: 60%;
    }

    &.column-66, &.column-67 {
      flex: 0 0 66.6666%;
      max-width: 66.6666%;
    }

    &.column-75 {
      flex: 0 0 75%;
      max-width: 75%;
    }

    &.column-80 {
      flex: 0 0 80%;
      max-width: 80%;
    }

    &.column-90 {
      flex: 0 0 90%;
      max-width: 90%;
    }

    .column-top {
      align-self: flex-start;
    }

    .column-bottom {
      align-self: flex-end;
    }

    .column-center {
      align-self: center;
    }
  }
}

@media (min-width: 40rem) {
  .row {
    flex-direction: row;
    margin-left: -1.0rem;
    width: calc(100% + 2.0rem);

    .column {
      margin-bottom: inherit;
      padding: 0 1.0rem;
    }
  }
}
//buttons
.btn{
  margin-bottom: 1rem;
  letter-spacing: -0.025rem;
  background-size: 150%;
  background-position-x: 25%;
  display: inline-block;
  font-weight: 700;
  line-height: 1.4;
  color: #67748e;
  text-align: center;
  vertical-align: middle;
  cursor: pointer;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  background-color: transparent;
  border: 1px solid transparent;
  padding: 0.75rem 1.5rem;
  font-size: 1.4rem;
  transition: all 0.15s ease-in;
  &--primary{
    background-color: #0e060f !important;
    color: #fff;
  }
  &--secondary{
    background-color: #c4c4c4 !important;
    color:black;
  }
}
.w{
  &-25{
    width: 25%;
  }
  &-50{
    width: 50%;
  }
  &-100{
    width: 100%;
  }
}

//Typography
b, strong {
  font-weight: bold;
}

p {
  margin-top: 0;
}

h1, h2, h3, h4, h5, h6 {
  font-weight: 700;
  letter-spacing: -.1rem;
  margin-bottom: 2.0rem;
  margin-top: 0;
}

h1 {
  font-size: 3.8rem;
  line-height: 1.2;
}

h2 {
  font-size: 3.6rem;
  line-height: 1.25;
}

h3 {
  font-size: 2.8rem;
  line-height: 1.3;
}

h4 {
  font-size: 2.2rem;
  letter-spacing: -.08rem;
  line-height: 1.35;
}

h5 {
  font-size: 1.8rem;
  letter-spacing: -.05rem;
  line-height: 1.5;
}

h6 {
  font-size: 1.6rem;
  letter-spacing: 0;
  line-height: 1.4;
}
img{
  max-width: 100%;
}
.clearfix{
  &:after {
    clear: both;
    content: ' '; // The space content is toavod Opera bug
    display: table;
  }
}

.float-left {
  float: left;
}

.float-right {
  float: right;
}

</style>
