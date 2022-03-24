![my-photo](/images/photo.jpg)

# Salabay Viktoria

## junior front-end developer

### Contact

##### Email

salabay.v@gmail.com

##### Discord

Viktoriia (@cappucinka)

### Education

2005-2011

Herzen State Pedagogical University of Russia

### Language

English A2

### Profile

Hello, my name is Viktoria!

I`m a junior front-end developer from Saint Petersburg, Russia.

I have 3+ years of web development experience.

### Experience

2020 - 2022

Alfaleads

HTML-developer

2018-2019

Center for Psychological Education

HTML-developer

2017-2018

LLC Optima Consulting

HTML-developer

### This is JavaScript Example from my [Portfolio](http://vika.bagrov.me/)

```javascript
let isSliderUnabled = false;
const upBtn = document.querySelector(".controls__button_dir_up");
const downBtn = document.querySelector(".controls__button_dir_down");
const sidebar = document.querySelector(".sidebar");
const slidesCount = document.querySelectorAll(".main-slide__item").length;
const container = document.querySelector(".container");
const mainSlide = document.querySelector(".main-slide");

const slider = () => {
  let activeSlide = 0;

  sidebar.style.top = `-${slidesCount - 1}00vh`;

  upBtn.addEventListener("click", () => {
    if (isSliderUnabled) {
      changeSlide("up");
    }
  });

  downBtn.addEventListener("click", () => {
    if (isSliderUnabled) {
      changeSlide("down");
    }
  });

  document.addEventListener("keydown", (event) => {
    if (event.key === "ArrowUp" && isSliderUnabled) {
      changeSlide("up");
    } else if (event.key === "ArrowDown" && isSliderUnabled) {
      changeSlide("down");
    }
  });

  function changeSlide(direction) {
    if (direction === "down") {
      activeSlide++;
      if (activeSlide >= slidesCount) {
        activeSlide = 0;
      }
    }
    if (direction === "up") {
      activeSlide--;
      if (activeSlide < 0) {
        activeSlide = slidesCount - 1;
      }
    }

    const height = container.clientHeight;

    sidebar.style.transform = `translateY(${height * activeSlide}px)`;
    mainSlide.style.transform = `translateY(-${height * activeSlide}px)`;
  }
};

if (window.innerWidth > 768) {
  slider();
  isSliderUnabled = true;
}

window.addEventListener("resize", function () {
  if (document.body.clientWidth < 768) {
    sidebar.removeAttribute("style");
    isSliderUnabled = false;
  } else {
    sidebar.style.top = `-${slidesCount - 1}00vh`;
    const height = container.clientHeight;
    mainSlide.style.transform = `translateY(0)`;
    isSliderUnabled = true;
  }
});
```
