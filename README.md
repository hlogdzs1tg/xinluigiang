"use strict";

const titleElement = document.querySelector(".title");
const buttonsContainer = document.querySelector(".buttons");
const yesButton = document.querySelector(".btn--yes");
const noButton = document.querySelector(".btn--no");
const catImg = document.querySelector(".cat-img");

const MAX_IMAGES = 5;

let play = true;
let noCount = 0;

yesButton.addEventListener("click", handleYesClick);

noButton.addEventListener("click", function () {
  if (play) {
    noCount++;
    const imageIndex = Math.min(noCount, MAX_IMAGES);
    changeImage(imageIndex);
    resizeYesButton();
    updateNoButtonText();
    if (noCount === MAX_IMAGES) {
      play = false;
    }
  }
});

function handleYesClick() {
  titleElement.innerHTML = "Da hlog cam on ,hlog hứa hongg làm cau buồn nữa au :3";
  buttonsContainer.classList.add("hidden");
  changeImage("yes");
}

function resizeYesButton() {
  const computedStyle = window.getComputedStyle(yesButton);
  const fontSize = parseFloat(computedStyle.getPropertyValue("font-size"));
  const newFontSize = fontSize * 1.6;

  yesButton.style.fontSize = `${newFontSize}px`;
}

function generateMessage(noCount) {
  const messages = [
    "Không Bao Giờ",
    "hlog bicc lỗi rồi ạa",
    "Mong cau tha lỗi choo to :((",
    "hlogg saii rồi , to đáng trách ạ",
    "Cau đừng giận anhh nữa nhoo",
    "Hlog quy hgiang nhắm nhunnn đóoooo",
  ];

  const messageIndex = Math.min(noCount, messages.length - 1);
  return messages[messageIndex];
}

function changeImage(image) {
  catImg.src = `img/cat-${image}.jpg`;
}

function updateNoButtonText() {
  noButton.innerHTML = generateMessage(noCount);
}[Uploading in<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link
      href="https://fonts.googleapis.com/css2?family=Protest+Riot&display=swap"
      rel="stylesheet"
    />
    <link rel="stylesheet" href="style.css" />
    <style>
      .title span {
        font-size: 1.5em; /* Kích thước chữ 1.5em */
      }
    </style>
    <title>Valentine</title>
  </head>
  <body>
    <main class="container">
      <img
        class="cat-img"
        src="https://media.giphy.com/media/SVkhYVCi8fKPKvypi6/giphy.gif"
        alt="Picture of a cat"
      />
      <p class="title">
        Cun ơi choo hlogg xinn lỗi nhooo😭<br /><span
          >Cau hong chọn hoặc thoát là tha lỗi cho to đó ><</span
        >
      </p>
      <div class="buttons">
        <button type="button" class="btn btn--yes">To chấp nhận</button>
        <button type="button" class="btn btn--no">Không bao giờ</button>
      </div>
    </main>

    <script type="module" src="script.js"></script>
  </body>
</html>
dex.html…]()

[Uploading styles.css…]()* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font-size: 62.5%;
}

body {
  background-color: #fff0f6;
  font-family: "Protest Riot", sans-serif;
}

.container {
  height: 100vh;
  margin: 0 auto;

  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.cat-img {
  width: 30rem;
  height: 30rem;
  margin-bottom: 2rem;
}

.title {
  font-size: 3.6rem;
  color: #f53699;
  text-align: center;
  margin-bottom: 2rem;
}

.buttons {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;

  gap: 1rem;
}

.btn {
  padding: 1.5rem 2.5rem;
  border: none;
  border-radius: 4px;

  color: white;
  font-size: 1.6rem;
  font-weight: 600;
  cursor: pointer;
  display: inline-block;
}

.btn--yes {
  background-color: #40c057;
}

.btn--no {
  background-color: #f03e3e;
}

.hidden {
  display: none;
}

