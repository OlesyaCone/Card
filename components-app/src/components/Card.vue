<script>
export default {
  data() {
    return {
      border: "",
      image:
        "https://upload.wikimedia.org/wikipedia/commons/thumb/9/95/Vue.js_Logo_2.svg/185px-Vue.js_Logo_2.svg.png",
      bgColor: "#35495E",
      title: "Vue",
      fontColorTitle: "#52ff66",
      fontSizeTitle: 30,
      textAlginTitle: "center",
      text: "Vue.js — JavaScript-фреймворк с открытым исходным кодом для создания пользовательских интерфейсов. Легко интегрируется в проекты с использованием других JavaScript-библиотек. Может функционировать как веб-фреймворк для разработки одностраничных приложений в реактивном стиле.",
      fontColorText: "#52ff66",
      fontSizeText: 15,
      textAlginText: "center",
      button: "Кнопка",
      fontColorButton: "#35495E",
      bgColorButton: "#52ff66",
      fontSizeButton: 15,
      textAlginButton: "center",
      fontColorHr: "#52ff66",
      heightHr: 5,
      widhtHr: 100,
      borderButton: 5,
      locationButton: "left",
      locationText: "left",
      locationTitle: "left",
      paddingButton: 8,
      cardContent: "",
      fontFamily:
        "'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif",
    };
  },
  methods: {
    copy() {
      this.cardContent =
        `<div class="card">
<img src="` +
        this.image +
        `" class="img" alt="..." />
<h5 class="card-title">` +
        this.title +
        `<h5>
<hr id="hr"/>
<p class="card-text">` +
        this.text +
        `<p>
<span id="button"><button class="card-button">` +
        this.button +
        `</button></span>
</div>

<style>
.card{
width: 25vh;
padding-left: 1em;
padding-right: 1em;
padding-bottom: 0.001em;
background-color: ` +
        this.bgColor +
        `;
border-radius: ` +
        this.border +
        `px;
}
.img{
width: 100%;
}
.card-title{
color: ` +
        this.fontColorTitle +
        `;
font-size: ` +
        this.fontSizeTitle +
        `px;
text-align: ` +
        this.locationTitle +
        `;
margin: 0;
}
#hr{
width: ` +
        this.widhtHr +
        `%;
border-top: ` +
        this.heightHr +
        `px solid ` +
        this.fontColorHr +
        `;
margin: 20px auto;
opacity: 50%;
margin: 0;

}
.card-text{
color: ` +
        this.fontColorText +
        `;
font-size: ` +
        this.fontSizeText +
        `px;
text-align: ` +
        this.locationText +
        `;
font-weight:50;
}
#button{
display: flex;
justify-content: ` +
        this.locationButton +
        `;
}
.card-button{
color: ` +
        this.fontColorButton +
        `;
font-size:  ` +
        this.fontSizeButton +
        `px;
background-color: ` +
        this.bgColorButton +
        `;
border-radius: ` +
        this.borderButton +
        `px;
border: none;
padding: ` +
        this.paddingButton +
        `px;
}
</style>`;

      navigator.clipboard
        .writeText(this.cardContent)
        .then(() => {
          console.log("Текст успешно скопирован в буфер обмена");
        })
        .catch((err) => {
          console.error("Произошла ошибка при копировании текста: ", err);
        });
    },
  },
};
</script>

<template>
  <div id="container">
    <div class="card" id="editor">
      <div class="card-body">
        <h6>Карточка</h6>
        <input
          type="number"
          class="form-control mt-3"
          min="20"
          max="100"
          placeholder="Скругление краев карточки"
          v-model="border"
        />
        <input type="color" class="form-control mt-3" v-model="bgColor" />
        <div class="input-group mb-3">
          <span class="input-group-text">Изображение</span>
          <textarea class="form-control" v-model="image"></textarea>
        </div>
        <h6>Название</h6>
        <input
          type="text"
          class="form-control mt-3 text-center"
          placeholder="Название"
          v-model="title"
        />
        <select
          class="form-select form-control mt-3"
          aria-label="Default select example"
          v-model="locationTitle"
        >
          <option value="center">По центру</option>
          <option value="left">Слева</option>
          <option value="right">Справа</option>
        </select>
        <input
          type="range"
          class="form-control mt-3"
          min="20"
          max="100"
          v-model="fontSizeTitle"
        />
        <input
          type="color"
          class="form-control mt-3"
          v-model="fontColorTitle"
        />
        <h6>Линия</h6>
        <div class="d-flex">
          <input
            type="number"
            class="form-control mt-3"
            min="20"
            max="100"
            placeholder="Высота линии"
            v-model="heightHr"
          />
          <input
            type="range"
            class="form-control mt-3"
            min="20"
            max="100"
            v-model="widhtHr"
          />
        </div>
        <input type="color" class="form-control mt-3" v-model="fontColorHr" />
        <h6>Текст</h6>
        <textarea
          class="form-control mt-3 text-center"
          type="text"
          placeholder="Текст"
          v-model="text"
        />
        <select
          class="form-select form-control mt-3"
          aria-label="Default select example"
          v-model="locationText"
        >
          <option value="center">По центру</option>
          <option value="left">Слева</option>
          <option value="right">Справа</option>
        </select>
        <select
          class="form-select form-control mt-3"
          aria-label="Default select example"
          v-model="fontFamily"
        >
          <option value="'Courier New', Courier, monospace">
            'Courier New', Courier, monospace
          </option>
          <option
            value="'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif"
          >
            'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif
          </option>
          <option
            value="'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif"
          >
            'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans
            Unicode', Geneva, Verdana, sans-serif
          </option>
          <option value="'Segoe UI', Tahoma, Geneva, Verdana, sans-serif">
            'Segoe UI', Tahoma, Geneva, Verdana, sans-serif
          </option>
          <option value="'Times New Roman', Times, serif">
            'Times New Roman', Times, serif
          </option>
          <option
            value="'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif"
          >
            'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida
            Sans', Arial, sans-serif
          </option>
          <option value="Arial, Helvetica, sans-serif">
            Arial, Helvetica, sans-serif
          </option>
          <option
            value="Cambria, Cochin, Georgia, Times, 'Times New Roman', serif"
          >
            Cambria, Cochin, Georgia, Times, 'Times New Roman', serif
          </option>
          <option value="Georgia, 'Times New Roman', Times, serif">
            Georgia, 'Times New Roman', Times, serif
          </option>
          <option value="Verdana, Geneva, Tahoma, sans-serif">
            Verdana, Geneva, Tahoma, sans-serif
          </option>
        </select>
        <input
          type="number"
          class="form-control mt-3"
          min="20"
          placeholder="Размер шрифта"
          max="100"
          v-model="fontSizeText"
        />
        <input type="color" class="form-control mt-3" v-model="fontColorText" />
        <h6>Кнопка</h6>
        <input
          type="text"
          class="form-control mt-3 text-center"
          placeholder="Кнопка"
          v-model="button"
        />
        <select
          class="form-select form-control mt-3"
          aria-label="Default select example"
          v-model="locationButton"
        >
          <option value="center">По центру</option>
          <option value="left">Слева</option>
          <option value="right">Справа</option>
        </select>
        <div class="d-flex input-group mb-3 mt-3">
          <input
            type="number"
            class="form-control mt-3"
            min="20"
            max="100"
            v-model="borderButton"
            placeholder="Скругление краев кнопки"
          />
          <input
            type="number"
            class="form-control mt-3"
            min="20"
            max="100"
            placeholder="Отсупы"
            v-model="paddingButton"
          />
        </div>

        <input
          type="number"
          class="form-control mt-3"
          min="20"
          max="100"
          placeholder="Размер шрифта"
          v-model="fontSizeButton"
        />

        <div class="d-flex">
          <input
            type="color"
            class="form-control mt-3"
            v-model="bgColorButton"
          />
          <input
            type="color"
            class="form-control mt-3"
            v-model="fontColorButton"
          />
        </div>
      </div>
    </div>
    <div id="right">
      <div
        class="card"
        style="width: 25vh"
        :style="{
          'background-color': bgColor,
          'border-radius': border + 'px',
        }"
      >
        <img :src="image" class="card-img-top" alt="..." />
        <div class="card-body">
          <h5
            class="card-title"
            :style="{
              color: fontColorTitle,
              'font-size': fontSizeTitle + 'px',
              'text-align': locationTitle,
            }"
          >
            {{ title }}
          </h5>
          <hr
            :style="{
              width: widhtHr + '%',
              'border-top': heightHr + 'px solid' + fontColorHr,
              margin: '20px auto',
            }"
          />
          <p
            class="card-text"
            :style="{
              color: fontColorText,
              'font-size': fontSizeText + 'px',
              'text-align': locationText,
              'font-family': fontFamily,
            }"
          >
            {{ text }}
          </p>
          <span
            :style="{
              display: 'flex',
              'justify-content': locationButton,
            }"
            ><button
              :style="{
                color: fontColorButton,
                'background-color': bgColorButton,
                'border-radius': borderButton + 'px',
                'font-size': fontSizeButton + 'px',
                border: 'none',
                padding: paddingButton + 'px',
              }"
            >
              {{ button }}
            </button></span
          >
        </div>
      </div>
    </div>
    <div id="card">
      <div class="tools">
        <div class="circle">
          <span class="red box"></span>
        </div>
        <div class="circle">
          <span class="yellow box"></span>
        </div>
        <div class="circle">
          <span class="green box"></span>
        </div>
        <div class="centralize">
          <div>
            <button id="copy" @click="copy">
              <span
                ><svg
                  viewBox="0 0 467 512.22"
                  clip-rule="evenodd"
                  fill-rule="evenodd"
                  image-rendering="optimizeQuality"
                  text-rendering="geometricPrecision"
                  shape-rendering="geometricPrecision"
                  xmlns="http://www.w3.org/2000/svg"
                  fill="#0E418F"
                  height="12"
                  width="12"
                >
                  <path
                    d="M131.07 372.11c.37 1 .57 2.08.57 3.2 0 1.13-.2 2.21-.57 3.21v75.91c0 10.74 4.41 20.53 11.5 27.62s16.87 11.49 27.62 11.49h239.02c10.75 0 20.53-4.4 27.62-11.49s11.49-16.88 11.49-27.62V152.42c0-10.55-4.21-20.15-11.02-27.18l-.47-.43c-7.09-7.09-16.87-11.5-27.62-11.5H170.19c-10.75 0-20.53 4.41-27.62 11.5s-11.5 16.87-11.5 27.61v219.69zm-18.67 12.54H57.23c-15.82 0-30.1-6.58-40.45-17.11C6.41 356.97 0 342.4 0 326.52V57.79c0-15.86 6.5-30.3 16.97-40.78l.04-.04C27.51 6.49 41.94 0 57.79 0h243.63c15.87 0 30.3 6.51 40.77 16.98l.03.03c10.48 10.48 16.99 24.93 16.99 40.78v36.85h50c15.9 0 30.36 6.5 40.82 16.96l.54.58c10.15 10.44 16.43 24.66 16.43 40.24v302.01c0 15.9-6.5 30.36-16.96 40.82-10.47 10.47-24.93 16.97-40.83 16.97H170.19c-15.9 0-30.35-6.5-40.82-16.97-10.47-10.46-16.97-24.92-16.97-40.82v-69.78zM340.54 94.64V57.79c0-10.74-4.41-20.53-11.5-27.63-7.09-7.08-16.86-11.48-27.62-11.48H57.79c-10.78 0-20.56 4.38-27.62 11.45l-.04.04c-7.06 7.06-11.45 16.84-11.45 27.62v268.73c0 10.86 4.34 20.79 11.38 27.97 6.95 7.07 16.54 11.49 27.17 11.49h55.17V152.42c0-15.9 6.5-30.35 16.97-40.82 10.47-10.47 24.92-16.96 40.82-16.96h170.35z"
                    fill-rule="nonzero"
                  ></path>
                </svg>
                Скопировать</span
              >
              <span>Скопировано!</span>
            </button>
          </div>
        </div>
      </div>
      <div class="card__content" v-bind="cardContent">
        <p>
          <br />
          &lt;div class="card"&gt; <br />
          &lt;img src="{{ image }}" class="img" alt="..." /&gt;<br />
          &lt;h5 class="card-title"&gt;{{ title }}&lt;h5&gt;<br />
          &lt;hr id="hr"/&gt;<br />
          &lt;p class="card-text"&gt;{{ text }}&lt;p&gt;<br />
          &lt;span id="button"&gt;&lt;button class="card-button"&gt;{{
            button
          }}&lt;/button&gt;&lt;/span&gt;<br />
          &lt;/div&gt;
        </p>
        <p>
          &lt;style&gt; <br />
          .card{<br />
          width: 25vh;<br />
          background-color: {{ bgColor }};<br />
          border-radius: {{ border }}px;<br />
          padding-left: 1em;<br />
          padding-right: 1em;<br />
          padding-bottom: 0.001em;<br />
          }<br />
          .img{<br />
          width: 100%;<br />
          }<br />
          .card-title{<br />
          color: {{ fontColorTitle }};<br />
          font-size: {{ fontSizeTitle }}px;<br />
          text-align: {{ locationTitle }};<br />
          margin: 0;<br />
          }<br />
          #hr{<br />
          width: {{ widhtHr }}%;<br />
          border-top: {{ heightHr }}px solid {{ fontColorHr }};<br />
          margin: 20px auto;<br />
          opacity: 50%;<br />
          border-bottom: 0;<br />
          }<br />
          .card-text{<br />
          color: {{ fontColorText }};<br />
          font-size: {{ fontSizeText }}px;<br />
          text-align: {{ locationText }};<br />
          font-weight:50;<br />
          }<br />
          #button{<br />
          display: flex;<br />
          justify-content: {{ locationButton }};<br />
          }<br />
          .card-button{<br />
          color: {{ fontColorButton }};<br />
          font-size: {{ fontSizeButton }}px;<br />
          background-color: {{ bgColorButton }};<br />
          border-radius: {{ borderButton }}px;<br />
          border: none;<br />
          padding: {{ paddingButton }}px;<br />
          }<br />
          &lt;/style&gt;
        </p>
      </div>
    </div>
  </div>
</template>

<style>
#container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
}

#editor {
  grid-column: span 2;
}

#right {
  display: flex;
  justify-content: center;
  align-items: center;
}

button {
  border: none;
}

h6 {
  text-align: center;
}

#copy {
  border: none;
  background: #52ff66dc;
}

#card {
  width: 100%;
  height: auto;
  margin: 0 auto;
  background-color: #011522;
  border-radius: 8px;
  z-index: 1;
  grid-column: 1/3;
  color: white;
}

.tools {
  display: flex;
  align-items: center;
  padding: 9px;
}

.circle {
  padding: 0 4px;
}

.box {
  display: inline-block;
  align-items: center;
  width: 10px;
  height: 10px;
  padding: 1px;
  border-radius: 50%;
}

.red {
  background-color: #ff605c;
}

.yellow {
  background-color: #ffbd44;
}

.green {
  background-color: #00ca4e;
}

#copy {
  background-color: #52ff66;
  width: 100px;
  height: 30px;
  border: none;
  border-radius: 10px;
  font-weight: 600;
  overflow: hidden;
  transition-duration: 700ms;
}

#copy span:first-child {
  color: #35495e;
  position: absolute;
  transform: translate(-50%, -50%);
}

#copy span:last-child {
  position: absolute;
  color: #52ff66;
  opacity: 0;
  transform: translateY(100%) translateX(-50%);
  height: 14px;
  line-height: 13px;
}

#copy:focus {
  background-color: #35495e;
  width: 120px;
  height: 40px;
  transition-delay: 100ms;
  transition-duration: 500ms;
}

#copy:focus span:first-child {
  color: #52ff66;
  transform: translateX(-50%) translateY(-150%);
  opacity: 0;
  transition-duration: 500ms;
}

#copy:focus span:last-child {
  transform: translateX(-50%) translateY(-50%);
  opacity: 1;
  transition-delay: 300ms;
  transition-duration: 500ms;
}

#copy:focus:end {
  background-color: #52ff66;
  width: 120px;
  height: 40px;
  transition-duration: 900ms;
}

.centralize {
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: right;
  align-items: right;
  text-align: right;
  margin-right: 25px;
  margin-top: 1px;
}

.description {
  margin-top: 10px;
  color: #52ff66;
}
</style>