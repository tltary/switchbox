# Customasible checkbox like ios style

[demo](https://tltary.github.io/switchbox/index.html)

``` html
<label class="switch__box">
  	<input type="checkbox" checked>
  	<span class="item"></span>
  	<span class="text">checked example</span>
</label>
```

### css
``` css
.switch__box {
  display: inline-block;
  position: relative;
  vertical-align: top;
}

.switch__box .text {
    display: inline-block;
    vertical-align: sub;
    margin-left: 60px;
}

.switch__box .item {
  position: absolute;
  top: 0;
  left: 0;
}

.switch__box .item:before {
  content: '';
  width: 50px;
  height: 25px;
  background: #dddddd;
  border-radius: 50px;
  -webkit-box-shadow: inset 2px 3px 5px -2px rgba(0,0,0,0.2);
  -moz-box-shadow: inset 2px 3px 5px -2px rgba(0,0,0,0.2);
  box-shadow: inset 2px 3px 5px -2px rgba(0,0,0,0.2);
  position: absolute;
  transition: background .2s linear;
}

.switch__box .item:after {
  content: '';
  width: 21px;
  height: 21px;
  background: #fff;
  border-radius: 50px;
  -webkit-box-shadow: inset 2px 3px 5px -2px rgba(0,0,0,0.2);
  -moz-box-shadow: inset 2px 3px 5px -2px rgba(0,0,0,0.2);
  box-shadow: inset 2px 3px 5px -2px rgba(0,0,0,0.2);
  position: absolute;
  top: 2px;
  left: 3px;
  transform: translateX(0%);
  transition: transform .2s ease-in-out;
}

.switch__box input {
  width: 100%;
  height: 25px;
  margin: 0px;
  z-index: 2;
  position: absolute;
  opacity: 0;
  cursor: pointer;
}

.switch__box input:checked + .item:before {
  background: #6edc5f;
  transition: background .2s linear;
}

.switch__box input:checked + .item:after {
  transform: translateX(110%);
  transition: transform .2s ease-in-out;
}
```

### scss
``` scss
.switch {
  &__box {
    display: inline-block;
    position: relative;
    vertical-align: top;
    input {
      width: 100%;
      height: 25px;
      margin: 0px;
      z-index: 2;
      position: absolute;
      opacity: 0;
      cursor: pointer;
      &:checked + .item:before {
        background: #6edc5f;
        transition: background .2s linear;
      }
      &:checked + .item:after {
        transform: translateX(110%);
        transition: transform .2s ease-in-out;
      }
    }
    .text {
      display: inline-block;
      vertical-align: sub;
      margin-left: 60px;
    }
    .item {
      position: absolute;
      top: 0;
      left: 0;
      &:before {
        content: '';
        width: 50px;
        height: 25px;
        background: #dddddd;
        border-radius: 50px;
        -webkit-box-shadow: inset 2px 3px 5px -2px rgba(0,0,0,0.2);
        -moz-box-shadow: inset 2px 3px 5px -2px rgba(0,0,0,0.2);
        box-shadow: inset 2px 3px 5px -2px rgba(0,0,0,0.2);
        position: absolute;
        transition: background .2s linear;
      }
      &:after {
        content: '';
        width: 21px;
        height: 21px;
        background: #fff;
        border-radius: 50px;
        -webkit-box-shadow: inset 2px 3px 5px -2px rgba(0,0,0,0.2);
        -moz-box-shadow: inset 2px 3px 5px -2px rgba(0,0,0,0.2);
        box-shadow: inset 2px 3px 5px -2px rgba(0,0,0,0.2);
        position: absolute;
        top: 2px;
        left: 3px;
        transform: translateX(0%);
        transition: transform .2s ease-in-out;
      }
    }
  }
}
```