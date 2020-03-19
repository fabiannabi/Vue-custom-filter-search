<template>
  <div>
    <form>
      <div class="search_bar">
        <input type="text" v-model="search" placeholder="Serch a Kanji" />
      </div>
    </form>
    <div class="cardbody">
      <div v-for="kanji in FilteredSearch" :key="kanji.id">
        <div class="card_container">
          <div class="whole_card">
            <div class="front">
              <p class="kanji_kanji">{{kanji.kanji}}</p>
              <p class="kanji_meaning">{{kanji.meaning}}</p>
            </div>
            <div class="back">
              <p class="kanji_reading">Readings</p>
              <p class="kanji_readingOn">音読み: {{kanji.onyomi}}</p>
              <p class="kanji_readingKun">訓読み: {{kanji.kunyomi}}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "app",
  data() {
    return {
      search: "",
      kanjis: [
        {
          kanji: "一",
          meaning: "Uno",
          onyomi: "Ka, kan, de, te",
          kunyomi: "hi",
          appears: "uno"
        },
        {
          kanji: "火",
          meaning: "fuego",
          Onyomi: "Ka , ",
          kunyomi: "hi",
          appears: "fuego"
        },
        {
          kanji: "火山",
          meaning: "volcan",
          Onyomi: "Ka , ",
          kunyomi: "hi",
          appears: "fuego volcan montaña"
        },
        {
          kanji: "月",
          meaning: "luna",
          Onyomi: "Ka , ",
          kunyomi: "hi",
          appears: "luna"
        },
        {
          kanji: "一月",
          meaning: "Enero",
          Onyomi: "Ka , ",
          kunyomi: "hi",
          appears: "uno luna enero"
        },
        {
          kanji: "一月",
          meaning: "Enero",
          Onyomi: "Ka , ",
          kunyomi: "hi",
          appears: "uno luna enero"
        },
        {
          kanji: "一月",
          meaning: "Enero",
          Onyomi: "Ka , ",
          kunyomi: "hi",
          appears: "uno luna enero"
        },
        {
          kanji: "一月",
          meaning: "Enero",
          Onyomi: "Ka , ",
          kunyomi: "hi",
          appears: "uno luna enero"
        },
        {
          kanji: "一月",
          meaning: "Enero",
          Onyomi: "Ka , ",
          kunyomi: "hi",
          appears: "uno luna enero"
        },
        {
          kanji: "一月",
          meaning: "Enero",
          Onyomi: "Ka , ",
          kunyomi: "hi",
          appears: "uno luna enero"
        },
        {
          kanji: "十一月",
          meaning: "Noviembre",
          Onyomi: "Ka , ",
          kunyomi: "hi",
          appears: "diez uno luna"
        }
      ]
    };
  },
  computed: {
    //esto regresa un nuevo array llamado FilteredSearch
    FilteredSearch: function() {
      //hace el retun de la funcion, que aplicara a toda la lista de kanji y a cada uno le hace la funcion
      return this.kanjis.filter(kanji => {
        //hace un match en la propiedad indicada y si esta es true y queda en el array
        return kanji.appears.match(this.search.toLowerCase());
      });
    }
  }
};
</script>

<!--
 base : hsl(3, 50%, 50%)

 dark : 
 (3, 100%, 70%)

ligth : hsl(3, 50%, 90%)
-->

<style lang="scss">
@import "_variables";
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.search_bar {
  text-align: center;
  margin-top: 2rem;
  height: 10rem;
  font-size: 48px;
  font-family: $kanjiFont;
}
input {
  width: 90%;
  margin-top: 2rem;
  font-size: 48px;
  font-family: $kanjiFont;
  text-align: center;
  color: hsl(3, 72%, 20%);
  border-radius: 30px;
  background-color: hsl(3, 72%, 80%);
  border-radius: 30px;
  box-shadow: inset 1 -1px 0px hsl(3, 10%, 73%);
}

.cardbody {
  width: 50%;
  margin: auto;
}
.card_container {
  position: relative;
  width: 500px;
  height: 500px;
  margin: 0.5rem 1rem;
}

.whole_card {
  position: absolute;
  width: 100%;
  height: 100%;
  transform-style: preserve-3d;
  transition: all 0.5s ease-in-out;
}

.card_container:hover .whole_card {
  transform: rotateY(180deg);
}
.front {
  position: absolute;
  width: 100%;
  height: 100%;
  backface-visibility: hidden;
  background-color: hsl(3, 100%, 80%);
  border-radius: 10px;
  box-shadow: $shadow;
}
.kanji_kanji {
  text-align: center;
  font-size: 72px;
  font-weight: bold;
  font-family: $kanjiFont;
  margin: 2rem 0 0 0;
  color: hsl(3, 100%, 10%);
  border-bottom: solid 1px black;
}
.kanji_meaning {
  color: hsl(3, 100%, 25%);
  text-align: center;
  font-size: 70px;
  font-family: $kanjiFont;
  margin: 3rem 0 0 0;
}

.back {
  position: absolute;
  width: 100%;
  height: 100%;
  backface-visibility: hidden;
  background-color: hsl(3, 100%, 70%);
  transform: rotateY(180deg);
  border-radius: 10px;
  box-shadow: $shadow;
}
.kanji_reading {
  text-align: center;
  font-size: 60px;
  font-family: $kanjiFont;
  margin: 3.6rem 0 0 0;
  color: hsl(3, 100%, 10%);
  border-bottom: solid 1px black;
}
.kanji_readingOn {
  text-align: start;
  color: hsl(3, 100%, 15%);
  font-size: 46px;
  font-family: $kanjiFont;
  margin: 1rem 0 0 1rem;
}
.kanji_readingKun {
  text-align: start;
  color: hsl(3, 100%, 15%);
  font-size: 46px;
  font-family: $kanjiFont;
  margin: 1rem 0 0 1rem;
}

@media (min-width: 1000px) {
  .cardbody {
    display: flex;
    flex-wrap: wrap;
    width: 100%;
    margin: auto;
  }
  .card_container {
    position: relative;
    width: 250px;
    height: 250px;
    margin: 0.5rem 2rem;
  }
  input {
    width: 50%;
    margin-top: 2rem;
    border-radius: 10px;
    font-size: 24px;
    font-family: $kanjiFont;
    text-align: center;
    width: 90%;
    color: hsl(3, 72%, 20%);
    border-radius: 30px;
    background-color: hsl(3, 72%, 80%);
    border-radius: 30px;
    box-shadow: inset 1 -1px 0px hsl(3, 10%, 73%);
  }
  .kanji_kanji {
    text-align: center;
    color: hsl(3, 100%, 10%);
    font-size: 30px;
    font-weight: bold;
    font-family: $kanjiFont;
    margin: 2rem 0 0 0;
    border-bottom: solid 1px black;
  }
  .kanji_meaning {
    text-align: center;
    font-size: 40px;
    font-family: $kanjiFont;
    color: hsl(3, 100%, 25%);
    margin: 3rem 0 0 0;
  }
  .kanji_reading {
    color: hsl(3, 100%, 10%);
    text-align: center;
    font-size: 24px;
    font-family: $kanjiFont;

    margin: 1rem 0 0 0;
    border-bottom: solid 1px black;
  }
  .kanji_readingOn {
    text-align: start;
    font-size: 22px;
    color: hsl(3, 100%, 15%);
    font-family: $kanjiFont;
    margin: 1rem 0 0 1rem;
  }
  .kanji_readingKun {
    text-align: start;
    font-size: 22px;
    color: hsl(3, 100%, 15%);
    font-family: $kanjiFont;
    margin: 1rem 0 0 1rem;
  }
}
</style>
