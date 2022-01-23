<template>
  <div>
    <treeselect v-model="value"
                :options="testData"
                :multiple="true"
                :normalizer="regionsNormalizer"
                :limit="2"
                :value-consists-of="valueConsistsOf"
                :sort-value-by="sortValueBy"
    />
    <treeselect-value :value="value" />
  </div>
</template>

<script>
import { generateOptions } from '../utils'

export default {
  data: () => ({
    options: generateOptions(2, 5),
    sortValueBy: 'INDEX',
    valueConsistsOf: 'ALL_WITH_INDETERMINATE', //'ALL_WITH_INDETERMINATE'
    value: null,
    regionsNormalizer(node) {
      return {
        id: node.region_id ? `2-${node.region_id}-${node.id}` : `1-${node.id}`,
        label: node.title,
        children: node.cities,
      }
    },
    testData: [
      {
        "id": 659,
        "title": "Хакасия",
        "cities": [
          {
            "id": 10492,
            "title": "Абаза",
            "region_id": 659,
            "__typename": "City"
          },
          {
            "id": 10493,
            "title": "Абакан",
            "region_id": 659,
            "__typename": "City"
          },
          {
            "id": 10582,
            "title": "Аскиз",
            "region_id": 659,
            "__typename": "City"
          },
          {
            "id": 10662,
            "title": "Белый Яр",
            "region_id": 659,
            "__typename": "City"
          },
          {
            "id": 10679,
            "title": "Бея",
            "region_id": 659,
            "__typename": "City"
          },
          {
            "id": 10702,
            "title": "Боград",
            "region_id": 659,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 660,
        "title": "Красноярский край",
        "cities": [
          {
            "id": 10494,
            "title": "Абан",
            "region_id": 660,
            "__typename": "City"
          },
          {
            "id": 10500,
            "title": "Агинское",
            "region_id": 660,
            "__typename": "City"
          },
          {
            "id": 10591,
            "title": "Ачинск",
            "region_id": 660,
            "__typename": "City"
          },
          {
            "id": 10618,
            "title": "Балахта",
            "region_id": 660,
            "__typename": "City"
          },
          {
            "id": 10673,
            "title": "Березовка",
            "region_id": 660,
            "__typename": "City"
          },
          {
            "id": 10685,
            "title": "Бирюлюсы",
            "region_id": 660,
            "__typename": "City"
          },
          {
            "id": 10701,
            "title": "Боготол",
            "region_id": 660,
            "__typename": "City"
          },
          {
            "id": 10703,
            "title": "Богучаны",
            "region_id": 660,
            "__typename": "City"
          },
          {
            "id": 10714,
            "title": "Большая Мурта",
            "region_id": 660,
            "__typename": "City"
          },
          {
            "id": 10732,
            "title": "Большой Улуй",
            "region_id": 660,
            "__typename": "City"
          },
          {
            "id": 10743,
            "title": "Бородино",
            "region_id": 660,
            "__typename": "City"
          },
          {
            "id": 10962,
            "title": "Дзержинск",
            "region_id": 660,
            "__typename": "City"
          },
          {
            "id": 10965,
            "title": "Дивногорск",
            "region_id": 660,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 661,
        "title": "Тюменская область",
        "cities": [
          {
            "id": 10495,
            "title": "Абатский",
            "region_id": 661,
            "__typename": "City"
          },
          {
            "id": 10566,
            "title": "Армизонское",
            "region_id": 661,
            "__typename": "City"
          },
          {
            "id": 10567,
            "title": "Аромашево",
            "region_id": 661,
            "__typename": "City"
          },
          {
            "id": 10667,
            "title": "Бердюжье",
            "region_id": 661,
            "__typename": "City"
          },
          {
            "id": 10730,
            "title": "Большое Сорокино",
            "region_id": 661,
            "__typename": "City"
          },
          {
            "id": 10766,
            "title": "Вагай",
            "region_id": 661,
            "__typename": "City"
          },
          {
            "id": 10816,
            "title": "Викулово",
            "region_id": 661,
            "__typename": "City"
          },
          {
            "id": 10905,
            "title": "Голышманово",
            "region_id": 661,
            "__typename": "City"
          },
          {
            "id": 10934,
            "title": "Губкинский",
            "region_id": 661,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 662,
        "title": "Оренбургская область",
        "cities": [
          {
            "id": 10496,
            "title": "Абдулино",
            "region_id": 662,
            "__typename": "City"
          },
          {
            "id": 10502,
            "title": "Адамовка",
            "region_id": 662,
            "__typename": "City"
          },
          {
            "id": 10512,
            "title": "Акбулак",
            "region_id": 662,
            "__typename": "City"
          },
          {
            "id": 10528,
            "title": "Александровка",
            "region_id": 662,
            "__typename": "City"
          },
          {
            "id": 10579,
            "title": "Асекеево",
            "region_id": 662,
            "__typename": "City"
          },
          {
            "id": 10664,
            "title": "Беляевка",
            "region_id": 662,
            "__typename": "City"
          },
          {
            "id": 10753,
            "title": "Бугуруслан",
            "region_id": 662,
            "__typename": "City"
          },
          {
            "id": 10756,
            "title": "Бузулук",
            "region_id": 662,
            "__typename": "City"
          },
          {
            "id": 10884,
            "title": "Гай",
            "region_id": 662,
            "__typename": "City"
          },
          {
            "id": 10923,
            "title": "Грачевка",
            "region_id": 662,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 663,
        "title": "Краснодарский край",
        "cities": [
          {
            "id": 10497,
            "title": "Абинск",
            "region_id": 663,
            "__typename": "City"
          },
          {
            "id": 10503,
            "title": "Адлер",
            "region_id": 663,
            "__typename": "City"
          },
          {
            "id": 10547,
            "title": "Анапа",
            "region_id": 663,
            "__typename": "City"
          },
          {
            "id": 10555,
            "title": "Апшеронск",
            "region_id": 663,
            "__typename": "City"
          },
          {
            "id": 10565,
            "title": "Армавир",
            "region_id": 663,
            "__typename": "City"
          },
          {
            "id": 10596,
            "title": "Аше",
            "region_id": 663,
            "__typename": "City"
          },
          {
            "id": 10641,
            "title": "Белая Глина",
            "region_id": 663,
            "__typename": "City"
          },
          {
            "id": 10657,
            "title": "Белореченск",
            "region_id": 663,
            "__typename": "City"
          },
          {
            "id": 10749,
            "title": "Брюховецкая",
            "region_id": 663,
            "__typename": "City"
          },
          {
            "id": 10773,
            "title": "Вардане",
            "region_id": 663,
            "__typename": "City"
          },
          {
            "id": 10870,
            "title": "Выселки",
            "region_id": 663,
            "__typename": "City"
          },
          {
            "id": 10892,
            "title": "Геленджик",
            "region_id": 663,
            "__typename": "City"
          },
          {
            "id": 10919,
            "title": "Горячий Ключ",
            "region_id": 663,
            "__typename": "City"
          },
          {
            "id": 10937,
            "title": "Гулькевичи",
            "region_id": 663,
            "__typename": "City"
          },
          {
            "id": 10970,
            "title": "Динская",
            "region_id": 663,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 664,
        "title": "Калининградская область",
        "cities": [
          {
            "id": 10498,
            "title": "Авангардное",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10516,
            "title": "Акулово",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10523,
            "title": "Алеевка",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10527,
            "title": "Александровка",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10534,
            "title": "Алексеевка",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10599,
            "title": "Бабушкино",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10604,
            "title": "Багратионово",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10605,
            "title": "Багратионовск",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10623,
            "title": "Балтийск",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10638,
            "title": "Бекенево",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10649,
            "title": "Белкино",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10661,
            "title": "Белый яр",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10668,
            "title": "Береговое",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10745,
            "title": "Борское",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10672,
            "title": "Березовка",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10691,
            "title": "Ближнее",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10693,
            "title": "Богатово",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10711,
            "title": "Большаково",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10715,
            "title": "Большая Поляна",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10721,
            "title": "Большие Горки",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10727,
            "title": "Большое село",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10751,
            "title": "Брянское",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10764,
            "title": "Бычково",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10777,
            "title": "Васильково",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10785,
            "title": "Великолукское",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10790,
            "title": "Верний бисер",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10810,
            "title": "Весново",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10814,
            "title": "Взморье",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10821,
            "title": "Вишневка",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10822,
            "title": "Вишневое",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10823,
            "title": "Вишневское",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10824,
            "title": "Вишневый",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10829,
            "title": "Владимирово",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10839,
            "title": "Володаровка",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10845,
            "title": "Волочаевское",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10848,
            "title": "Вольное",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10853,
            "title": "Воробьево",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10859,
            "title": "Восод",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10872,
            "title": "Высокое",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10880,
            "title": "Гаврилово",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10887,
            "title": "Гастеллово",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10889,
            "title": "Гвардейск",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10890,
            "title": "Гвардейское",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10894,
            "title": "Георгиевское",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10900,
            "title": "Глушково",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10904,
            "title": "Головкино",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10906,
            "title": "Гончарово",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10908,
            "title": "Гордое",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10922,
            "title": "Грачевка",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10927,
            "title": "Грибки",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10929,
            "title": "Громово",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10938,
            "title": "Гурьевск",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10940,
            "title": "Гусев",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10941,
            "title": "Гусево",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10947,
            "title": "Дальнее",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10953,
            "title": "Дворкино",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10957,
            "title": "Демидово",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10966,
            "title": "Дивное",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10977,
            "title": "Доброволец",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10978,
            "title": "Добровольск",
            "region_id": 664,
            "__typename": "City"
          },
          {
            "id": 10981,
            "title": "Доваторовка",
            "region_id": 664,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 665,
        "title": "Челябинская область",
        "cities": [
          {
            "id": 10499,
            "title": "Агаповка",
            "region_id": 665,
            "__typename": "City"
          },
          {
            "id": 10557,
            "title": "Аргаяш",
            "region_id": 665,
            "__typename": "City"
          },
          {
            "id": 10595,
            "title": "Аша",
            "region_id": 665,
            "__typename": "City"
          },
          {
            "id": 10747,
            "title": "Бреды",
            "region_id": 665,
            "__typename": "City"
          },
          {
            "id": 10774,
            "title": "Варна",
            "region_id": 665,
            "__typename": "City"
          },
          {
            "id": 10792,
            "title": "Верхнеуральск",
            "region_id": 665,
            "__typename": "City"
          },
          {
            "id": 10798,
            "title": "Верхний Уфалей",
            "region_id": 665,
            "__typename": "City"
          },
          {
            "id": 10983,
            "title": "Долгодеревенское",
            "region_id": 665,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 666,
        "title": "Татарстан",
        "cities": [
          {
            "id": 10501,
            "title": "Агрыз",
            "region_id": 666,
            "__typename": "City"
          },
          {
            "id": 10507,
            "title": "Азнакаево",
            "region_id": 666,
            "__typename": "City"
          },
          {
            "id": 10514,
            "title": "Аксубаево",
            "region_id": 666,
            "__typename": "City"
          },
          {
            "id": 10515,
            "title": "Актаныш",
            "region_id": 666,
            "__typename": "City"
          },
          {
            "id": 10536,
            "title": "Алексеевское",
            "region_id": 666,
            "__typename": "City"
          },
          {
            "id": 10541,
            "title": "Алькеево",
            "region_id": 666,
            "__typename": "City"
          },
          {
            "id": 10543,
            "title": "Альметьевск",
            "region_id": 666,
            "__typename": "City"
          },
          {
            "id": 10553,
            "title": "Апастово",
            "region_id": 666,
            "__typename": "City"
          },
          {
            "id": 10570,
            "title": "Арск",
            "region_id": 666,
            "__typename": "City"
          },
          {
            "id": 10586,
            "title": "Атня",
            "region_id": 666,
            "__typename": "City"
          },
          {
            "id": 10601,
            "title": "Бавлы",
            "region_id": 666,
            "__typename": "City"
          },
          {
            "id": 10622,
            "title": "Балтаси",
            "region_id": 666,
            "__typename": "City"
          },
          {
            "id": 10694,
            "title": "Богатые Сабы",
            "region_id": 666,
            "__typename": "City"
          },
          {
            "id": 10707,
            "title": "Болгар",
            "region_id": 666,
            "__typename": "City"
          },
          {
            "id": 10752,
            "title": "Бугульма",
            "region_id": 666,
            "__typename": "City"
          },
          {
            "id": 10757,
            "title": "Буинск",
            "region_id": 666,
            "__typename": "City"
          },
          {
            "id": 10776,
            "title": "Васильево",
            "region_id": 666,
            "__typename": "City"
          },
          {
            "id": 10797,
            "title": "Верхний Услон",
            "region_id": 666,
            "__typename": "City"
          },
          {
            "id": 10871,
            "title": "Высокая Гора",
            "region_id": 666,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 667,
        "title": "Тверская область",
        "cities": [
          {
            "id": 10504,
            "title": "Адреаполь",
            "region_id": 667,
            "__typename": "City"
          },
          {
            "id": 10636,
            "title": "Бежецк",
            "region_id": 667,
            "__typename": "City"
          },
          {
            "id": 10660,
            "title": "Белый",
            "region_id": 667,
            "__typename": "City"
          },
          {
            "id": 10708,
            "title": "Бологое",
            "region_id": 667,
            "__typename": "City"
          },
          {
            "id": 10874,
            "title": "Вышний Волочек",
            "region_id": 667,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 668,
        "title": "Адыгея",
        "cities": [
          {
            "id": 10505,
            "title": "Адыгейск",
            "region_id": 668,
            "__typename": "City"
          },
          {
            "id": 10896,
            "title": "Гиагинская",
            "region_id": 668,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 669,
        "title": "Карачаево-Черкесия",
        "cities": [
          {
            "id": 10506,
            "title": "Адыге-Хабль",
            "region_id": 669,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 670,
        "title": "Ростовская область",
        "cities": [
          {
            "id": 10508,
            "title": "Азов",
            "region_id": 670,
            "__typename": "City"
          },
          {
            "id": 10513,
            "title": "Аксай",
            "region_id": 670,
            "__typename": "City"
          },
          {
            "id": 10602,
            "title": "Багаевский",
            "region_id": 670,
            "__typename": "City"
          },
          {
            "id": 10630,
            "title": "Батайск",
            "region_id": 670,
            "__typename": "City"
          },
          {
            "id": 10642,
            "title": "Белая Калитва",
            "region_id": 670,
            "__typename": "City"
          },
          {
            "id": 10705,
            "title": "Боковская",
            "region_id": 670,
            "__typename": "City"
          },
          {
            "id": 10713,
            "title": "Большая Мартыновка",
            "region_id": 670,
            "__typename": "City"
          },
          {
            "id": 10809,
            "title": "Веселый",
            "region_id": 670,
            "__typename": "City"
          },
          {
            "id": 10812,
            "title": "Вешенская",
            "region_id": 670,
            "__typename": "City"
          },
          {
            "id": 10833,
            "title": "Волгодонск",
            "region_id": 670,
            "__typename": "City"
          },
          {
            "id": 10936,
            "title": "Гуково",
            "region_id": 670,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 671,
        "title": "Омская область",
        "cities": [
          {
            "id": 10509,
            "title": "Азово",
            "region_id": 671,
            "__typename": "City"
          },
          {
            "id": 10718,
            "title": "Большеречье",
            "region_id": 671,
            "__typename": "City"
          },
          {
            "id": 10722,
            "title": "Большие Уки",
            "region_id": 671,
            "__typename": "City"
          },
          {
            "id": 10918,
            "title": "Горьковское",
            "region_id": 671,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 672,
        "title": "Коми",
        "cities": [
          {
            "id": 10510,
            "title": "Айкино",
            "region_id": 672,
            "__typename": "City"
          },
          {
            "id": 10511,
            "title": "Акбулак",
            "region_id": 672,
            "__typename": "City"
          },
          {
            "id": 10815,
            "title": "Визинга",
            "region_id": 672,
            "__typename": "City"
          },
          {
            "id": 10851,
            "title": "Воркута",
            "region_id": 672,
            "__typename": "City"
          },
          {
            "id": 10863,
            "title": "Вуктыл",
            "region_id": 672,
            "__typename": "City"
          },
          {
            "id": 10868,
            "title": "Выльгорт",
            "region_id": 672,
            "__typename": "City"
          },
          {
            "id": 10869,
            "title": "Выльногорск",
            "region_id": 672,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 673,
        "title": "Читинская область",
        "cities": [
          {
            "id": 10517,
            "title": "Акша",
            "region_id": 673,
            "__typename": "City"
          },
          {
            "id": 10592,
            "title": "Ачинское",
            "region_id": 673,
            "__typename": "City"
          },
          {
            "id": 10646,
            "title": "Белебей",
            "region_id": 673,
            "__typename": "City"
          },
          {
            "id": 10736,
            "title": "Борзя",
            "region_id": 673,
            "__typename": "City"
          },
          {
            "id": 10807,
            "title": "Верх-Усугли",
            "region_id": 673,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 674,
        "title": "Башкортостан",
        "cities": [
          {
            "id": 10518,
            "title": "Акъяр",
            "region_id": 674,
            "__typename": "City"
          },
          {
            "id": 10575,
            "title": "Архангельское",
            "region_id": 674,
            "__typename": "City"
          },
          {
            "id": 10581,
            "title": "Аскарово",
            "region_id": 674,
            "__typename": "City"
          },
          {
            "id": 10583,
            "title": "Аскино",
            "region_id": 674,
            "__typename": "City"
          },
          {
            "id": 10611,
            "title": "Баймак",
            "region_id": 674,
            "__typename": "City"
          },
          {
            "id": 10612,
            "title": "Бакалы",
            "region_id": 674,
            "__typename": "City"
          },
          {
            "id": 10645,
            "title": "Белебей",
            "region_id": 674,
            "__typename": "City"
          },
          {
            "id": 10656,
            "title": "Белорецк",
            "region_id": 674,
            "__typename": "City"
          },
          {
            "id": 10680,
            "title": "Бижбуляк",
            "region_id": 674,
            "__typename": "City"
          },
          {
            "id": 10684,
            "title": "Бирск",
            "region_id": 674,
            "__typename": "City"
          },
          {
            "id": 10688,
            "title": "Благовещенск",
            "region_id": 674,
            "__typename": "City"
          },
          {
            "id": 10719,
            "title": "Большеустьикинское",
            "region_id": 674,
            "__typename": "City"
          },
          {
            "id": 10755,
            "title": "Буздяк",
            "region_id": 674,
            "__typename": "City"
          },
          {
            "id": 10759,
            "title": "Бураево",
            "region_id": 674,
            "__typename": "City"
          },
          {
            "id": 10793,
            "title": "Верхнеяркеево",
            "region_id": 674,
            "__typename": "City"
          },
          {
            "id": 10794,
            "title": "Верхние Киги",
            "region_id": 674,
            "__typename": "City"
          },
          {
            "id": 10944,
            "title": "Давлеканово",
            "region_id": 674,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 675,
        "title": "Северная Осетия",
        "cities": [
          {
            "id": 10519,
            "title": "Алагир",
            "region_id": 675,
            "__typename": "City"
          },
          {
            "id": 10561,
            "title": "Ардон",
            "region_id": 675,
            "__typename": "City"
          },
          {
            "id": 10577,
            "title": "Архонская",
            "region_id": 675,
            "__typename": "City"
          },
          {
            "id": 10677,
            "title": "Беслан",
            "region_id": 675,
            "__typename": "City"
          },
          {
            "id": 10826,
            "title": "Владикавказ",
            "region_id": 675,
            "__typename": "City"
          },
          {
            "id": 10968,
            "title": "Дигора",
            "region_id": 675,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 676,
        "title": "Свердловская область",
        "cities": [
          {
            "id": 10520,
            "title": "Алапаевск",
            "region_id": 676,
            "__typename": "City"
          },
          {
            "id": 10572,
            "title": "Артемовский",
            "region_id": 676,
            "__typename": "City"
          },
          {
            "id": 10573,
            "title": "Арти",
            "region_id": 676,
            "__typename": "City"
          },
          {
            "id": 10578,
            "title": "Асбест",
            "region_id": 676,
            "__typename": "City"
          },
          {
            "id": 10593,
            "title": "Ачит",
            "region_id": 676,
            "__typename": "City"
          },
          {
            "id": 10609,
            "title": "Байкалово",
            "region_id": 676,
            "__typename": "City"
          },
          {
            "id": 10658,
            "title": "Белоярский",
            "region_id": 676,
            "__typename": "City"
          },
          {
            "id": 10675,
            "title": "Березовский",
            "region_id": 676,
            "__typename": "City"
          },
          {
            "id": 10695,
            "title": "Богданович",
            "region_id": 676,
            "__typename": "City"
          },
          {
            "id": 10799,
            "title": "Верхняя Пышма",
            "region_id": 676,
            "__typename": "City"
          },
          {
            "id": 10800,
            "title": "Верхняя Салда",
            "region_id": 676,
            "__typename": "City"
          },
          {
            "id": 10805,
            "title": "Верхотурье",
            "region_id": 676,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 677,
        "title": "Чувашия",
        "cities": [
          {
            "id": 10521,
            "title": "Алатырь",
            "region_id": 677,
            "__typename": "City"
          },
          {
            "id": 10538,
            "title": "Аликово",
            "region_id": 677,
            "__typename": "City"
          },
          {
            "id": 10632,
            "title": "Батырево",
            "region_id": 677,
            "__typename": "City"
          },
          {
            "id": 10864,
            "title": "Вурнары",
            "region_id": 677,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 678,
        "title": "Саха-Якутия",
        "cities": [
          {
            "id": 10522,
            "title": "Алдан",
            "region_id": 678,
            "__typename": "City"
          },
          {
            "id": 10544,
            "title": "Амга",
            "region_id": 678,
            "__typename": "City"
          },
          {
            "id": 10629,
            "title": "Батагай-Алыта",
            "region_id": 678,
            "__typename": "City"
          },
          {
            "id": 10665,
            "title": "Бердигестях",
            "region_id": 678,
            "__typename": "City"
          },
          {
            "id": 10742,
            "title": "Борогонцы",
            "region_id": 678,
            "__typename": "City"
          },
          {
            "id": 10791,
            "title": "Верхневилюйск",
            "region_id": 678,
            "__typename": "City"
          },
          {
            "id": 10817,
            "title": "Вилюйск",
            "region_id": 678,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 679,
        "title": "Алтайский край",
        "cities": [
          {
            "id": 10524,
            "title": "Алейск",
            "region_id": 679,
            "__typename": "City"
          },
          {
            "id": 10540,
            "title": "Алтайское",
            "region_id": 679,
            "__typename": "City"
          },
          {
            "id": 10606,
            "title": "Баево",
            "region_id": 679,
            "__typename": "City"
          },
          {
            "id": 10627,
            "title": "Барнаул",
            "region_id": 679,
            "__typename": "City"
          },
          {
            "id": 10654,
            "title": "Белокуриха",
            "region_id": 679,
            "__typename": "City"
          },
          {
            "id": 10681,
            "title": "Бийск",
            "region_id": 679,
            "__typename": "City"
          },
          {
            "id": 10687,
            "title": "Благовещенка",
            "region_id": 679,
            "__typename": "City"
          },
          {
            "id": 10760,
            "title": "Бурла",
            "region_id": 679,
            "__typename": "City"
          },
          {
            "id": 10763,
            "title": "Быстрый Исток",
            "region_id": 679,
            "__typename": "City"
          },
          {
            "id": 10847,
            "title": "Волчиха",
            "region_id": 679,
            "__typename": "City"
          },
          {
            "id": 10886,
            "title": "Гальбштадт",
            "region_id": 679,
            "__typename": "City"
          },
          {
            "id": 10912,
            "title": "Горняк",
            "region_id": 679,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 680,
        "title": "Владимирская область",
        "cities": [
          {
            "id": 10525,
            "title": "Александров",
            "region_id": 680,
            "__typename": "City"
          },
          {
            "id": 10827,
            "title": "Владимир",
            "region_id": 680,
            "__typename": "City"
          },
          {
            "id": 10916,
            "title": "Гороховец",
            "region_id": 680,
            "__typename": "City"
          },
          {
            "id": 10943,
            "title": "Гусь Хрустальный",
            "region_id": 680,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 681,
        "title": "Саратовская область",
        "cities": [
          {
            "id": 10526,
            "title": "Александров Гай",
            "region_id": 681,
            "__typename": "City"
          },
          {
            "id": 10564,
            "title": "Аркадак",
            "region_id": 681,
            "__typename": "City"
          },
          {
            "id": 10585,
            "title": "Аткарск",
            "region_id": 681,
            "__typename": "City"
          },
          {
            "id": 10607,
            "title": "Базарный Карабулак",
            "region_id": 681,
            "__typename": "City"
          },
          {
            "id": 10616,
            "title": "Балаково",
            "region_id": 681,
            "__typename": "City"
          },
          {
            "id": 10619,
            "title": "Балашов",
            "region_id": 681,
            "__typename": "City"
          },
          {
            "id": 10621,
            "title": "Балтай",
            "region_id": 681,
            "__typename": "City"
          },
          {
            "id": 10850,
            "title": "Вольск",
            "region_id": 681,
            "__typename": "City"
          },
          {
            "id": 10857,
            "title": "Воскресенское",
            "region_id": 681,
            "__typename": "City"
          },
          {
            "id": 10911,
            "title": "Горный",
            "region_id": 681,
            "__typename": "City"
          },
          {
            "id": 10960,
            "title": "Дергачи",
            "region_id": 681,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 682,
        "title": "Пермская область",
        "cities": [
          {
            "id": 10529,
            "title": "Александровск",
            "region_id": 682,
            "__typename": "City"
          },
          {
            "id": 10626,
            "title": "Барда",
            "region_id": 682,
            "__typename": "City"
          },
          {
            "id": 10670,
            "title": "Березники",
            "region_id": 682,
            "__typename": "City"
          },
          {
            "id": 10671,
            "title": "Березовка",
            "region_id": 682,
            "__typename": "City"
          },
          {
            "id": 10716,
            "title": "Большая Соснова",
            "region_id": 682,
            "__typename": "City"
          },
          {
            "id": 10789,
            "title": "Верещагино",
            "region_id": 682,
            "__typename": "City"
          },
          {
            "id": 10910,
            "title": "Горнозаводск",
            "region_id": 682,
            "__typename": "City"
          },
          {
            "id": 10925,
            "title": "Гремячинск",
            "region_id": 682,
            "__typename": "City"
          },
          {
            "id": 10932,
            "title": "Губаха",
            "region_id": 682,
            "__typename": "City"
          },
          {
            "id": 10980,
            "title": "Добрянка",
            "region_id": 682,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 683,
        "title": "Ставропольский край",
        "cities": [
          {
            "id": 10530,
            "title": "Александровское",
            "region_id": 683,
            "__typename": "City"
          },
          {
            "id": 10563,
            "title": "Арзгир",
            "region_id": 683,
            "__typename": "City"
          },
          {
            "id": 10690,
            "title": "Благодарный",
            "region_id": 683,
            "__typename": "City"
          },
          {
            "id": 10754,
            "title": "Буденновск",
            "region_id": 683,
            "__typename": "City"
          },
          {
            "id": 10893,
            "title": "Георгиевск",
            "region_id": 683,
            "__typename": "City"
          },
          {
            "id": 10924,
            "title": "Грачевка",
            "region_id": 683,
            "__typename": "City"
          },
          {
            "id": 10967,
            "title": "Дивное",
            "region_id": 683,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 684,
        "title": "Томская область",
        "cities": [
          {
            "id": 10531,
            "title": "Александровское",
            "region_id": 684,
            "__typename": "City"
          },
          {
            "id": 10580,
            "title": "Асино",
            "region_id": 684,
            "__typename": "City"
          },
          {
            "id": 10614,
            "title": "Бакчар",
            "region_id": 684,
            "__typename": "City"
          },
          {
            "id": 10663,
            "title": "Белый Яр",
            "region_id": 684,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 685,
        "title": "Рязанская область",
        "cities": [
          {
            "id": 10532,
            "title": "Александро-Невский",
            "region_id": 685,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 686,
        "title": "Самарская область",
        "cities": [
          {
            "id": 10533,
            "title": "Алексеевка",
            "region_id": 686,
            "__typename": "City"
          },
          {
            "id": 10637,
            "title": "Безенчук",
            "region_id": 686,
            "__typename": "City"
          },
          {
            "id": 10712,
            "title": "Большая Глушица",
            "region_id": 686,
            "__typename": "City"
          },
          {
            "id": 10717,
            "title": "Большая Черниговка",
            "region_id": 686,
            "__typename": "City"
          },
          {
            "id": 10744,
            "title": "Борское",
            "region_id": 686,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 687,
        "title": "Белгородская область",
        "cities": [
          {
            "id": 10535,
            "title": "Алексеевка",
            "region_id": 687,
            "__typename": "City"
          },
          {
            "id": 10644,
            "title": "Белгород",
            "region_id": 687,
            "__typename": "City"
          },
          {
            "id": 10737,
            "title": "Борисовка",
            "region_id": 687,
            "__typename": "City"
          },
          {
            "id": 10770,
            "title": "Валуйки",
            "region_id": 687,
            "__typename": "City"
          },
          {
            "id": 10780,
            "title": "Вейделевка",
            "region_id": 687,
            "__typename": "City"
          },
          {
            "id": 10842,
            "title": "Волоконовка",
            "region_id": 687,
            "__typename": "City"
          },
          {
            "id": 10920,
            "title": "Грайворон",
            "region_id": 687,
            "__typename": "City"
          },
          {
            "id": 10933,
            "title": "Губкин",
            "region_id": 687,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 688,
        "title": "Тульская область",
        "cities": [
          {
            "id": 10537,
            "title": "Алексин",
            "region_id": 688,
            "__typename": "City"
          },
          {
            "id": 10569,
            "title": "Арсеньево",
            "region_id": 688,
            "__typename": "City"
          },
          {
            "id": 10576,
            "title": "Архангельское",
            "region_id": 688,
            "__typename": "City"
          },
          {
            "id": 10647,
            "title": "Белев",
            "region_id": 688,
            "__typename": "City"
          },
          {
            "id": 10697,
            "title": "Богородицк",
            "region_id": 688,
            "__typename": "City"
          },
          {
            "id": 10788,
            "title": "Венев",
            "region_id": 688,
            "__typename": "City"
          },
          {
            "id": 10837,
            "title": "Волово",
            "region_id": 688,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 689,
        "title": "Удмуртия",
        "cities": [
          {
            "id": 10539,
            "title": "Алнаши",
            "region_id": 689,
            "__typename": "City"
          },
          {
            "id": 10620,
            "title": "Балезино",
            "region_id": 689,
            "__typename": "City"
          },
          {
            "id": 10765,
            "title": "Вавож",
            "region_id": 689,
            "__typename": "City"
          },
          {
            "id": 10860,
            "title": "Воткинск",
            "region_id": 689,
            "__typename": "City"
          },
          {
            "id": 10897,
            "title": "Глазов",
            "region_id": 689,
            "__typename": "City"
          },
          {
            "id": 10921,
            "title": "Грахово",
            "region_id": 689,
            "__typename": "City"
          },
          {
            "id": 10954,
            "title": "Дебесы",
            "region_id": 689,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 690,
        "title": "Курганская область",
        "cities": [
          {
            "id": 10542,
            "title": "Альменево",
            "region_id": 690,
            "__typename": "City"
          },
          {
            "id": 10653,
            "title": "Белозерское",
            "region_id": 690,
            "__typename": "City"
          },
          {
            "id": 10772,
            "title": "Варгаши",
            "region_id": 690,
            "__typename": "City"
          },
          {
            "id": 10902,
            "title": "Глядянское",
            "region_id": 690,
            "__typename": "City"
          },
          {
            "id": 10945,
            "title": "Далматово",
            "region_id": 690,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 691,
        "title": "Хабаровский край",
        "cities": [
          {
            "id": 10545,
            "title": "Амурск",
            "region_id": 691,
            "__typename": "City"
          },
          {
            "id": 10597,
            "title": "Аян",
            "region_id": 691,
            "__typename": "City"
          },
          {
            "id": 10682,
            "title": "Бикин",
            "region_id": 691,
            "__typename": "City"
          },
          {
            "id": 10700,
            "title": "Богородское",
            "region_id": 691,
            "__typename": "City"
          },
          {
            "id": 10771,
            "title": "Ванино",
            "region_id": 691,
            "__typename": "City"
          },
          {
            "id": 10875,
            "title": "Вяземский",
            "region_id": 691,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 692,
        "title": "Чукотский автономный округ",
        "cities": [
          {
            "id": 10546,
            "title": "Анадырь",
            "region_id": 692,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 693,
        "title": "Иркутская область",
        "cities": [
          {
            "id": 10548,
            "title": "Ангарск",
            "region_id": 693,
            "__typename": "City"
          },
          {
            "id": 10746,
            "title": "Братск",
            "region_id": 693,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 694,
        "title": "Кемеровская область",
        "cities": [
          {
            "id": 10549,
            "title": "Анжеро-Судженск",
            "region_id": 694,
            "__typename": "City"
          },
          {
            "id": 10650,
            "title": "Белово",
            "region_id": 694,
            "__typename": "City"
          },
          {
            "id": 10676,
            "title": "Березовский",
            "region_id": 694,
            "__typename": "City"
          },
          {
            "id": 10808,
            "title": "Верх-Чебула",
            "region_id": 694,
            "__typename": "City"
          },
          {
            "id": 10939,
            "title": "Гурьевск",
            "region_id": 694,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 695,
        "title": "Воронежская область",
        "cities": [
          {
            "id": 10550,
            "title": "Анна",
            "region_id": 695,
            "__typename": "City"
          },
          {
            "id": 10692,
            "title": "Бобров",
            "region_id": 695,
            "__typename": "City"
          },
          {
            "id": 10704,
            "title": "Богучар",
            "region_id": 695,
            "__typename": "City"
          },
          {
            "id": 10738,
            "title": "Борисоглебск",
            "region_id": 695,
            "__typename": "City"
          },
          {
            "id": 10762,
            "title": "Бутурлиновка",
            "region_id": 695,
            "__typename": "City"
          },
          {
            "id": 10796,
            "title": "Верхний Мамон",
            "region_id": 695,
            "__typename": "City"
          },
          {
            "id": 10802,
            "title": "Верхняя Хава",
            "region_id": 695,
            "__typename": "City"
          },
          {
            "id": 10852,
            "title": "Воробьевка",
            "region_id": 695,
            "__typename": "City"
          },
          {
            "id": 10854,
            "title": "Воронеж",
            "region_id": 695,
            "__typename": "City"
          },
          {
            "id": 10926,
            "title": "Грибановский",
            "region_id": 695,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 696,
        "title": "Костромская область",
        "cities": [
          {
            "id": 10551,
            "title": "Антропово",
            "region_id": 696,
            "__typename": "City"
          },
          {
            "id": 10696,
            "title": "Боговарово",
            "region_id": 696,
            "__typename": "City"
          },
          {
            "id": 10758,
            "title": "Буй",
            "region_id": 696,
            "__typename": "City"
          },
          {
            "id": 10834,
            "title": "Волгореченск",
            "region_id": 696,
            "__typename": "City"
          },
          {
            "id": 10861,
            "title": "Вохма",
            "region_id": 696,
            "__typename": "City"
          },
          {
            "id": 10885,
            "title": "Галич",
            "region_id": 696,
            "__typename": "City"
          },
          {
            "id": 10895,
            "title": "Георгиевское",
            "region_id": 696,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 697,
        "title": "Приморский край",
        "cities": [
          {
            "id": 10552,
            "title": "Анучино",
            "region_id": 697,
            "__typename": "City"
          },
          {
            "id": 10568,
            "title": "Арсеньев",
            "region_id": 697,
            "__typename": "City"
          },
          {
            "id": 10571,
            "title": "Артем",
            "region_id": 697,
            "__typename": "City"
          },
          {
            "id": 10731,
            "title": "Большой Камень",
            "region_id": 697,
            "__typename": "City"
          },
          {
            "id": 10825,
            "title": "Владивосток",
            "region_id": 697,
            "__typename": "City"
          },
          {
            "id": 10828,
            "title": "Владимиро-Александровское",
            "region_id": 697,
            "__typename": "City"
          },
          {
            "id": 10849,
            "title": "Вольно-Надеждинское",
            "region_id": 697,
            "__typename": "City"
          },
          {
            "id": 10946,
            "title": "Дальнегорск",
            "region_id": 697,
            "__typename": "City"
          },
          {
            "id": 10949,
            "title": "Дальнереченск",
            "region_id": 697,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 698,
        "title": "Мурманская область",
        "cities": [
          {
            "id": 10554,
            "title": "Апатиты",
            "region_id": 698,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 699,
        "title": "Кировская область",
        "cities": [
          {
            "id": 10556,
            "title": "Арбаж",
            "region_id": 699,
            "__typename": "City"
          },
          {
            "id": 10643,
            "title": "Белая Холуница",
            "region_id": 699,
            "__typename": "City"
          },
          {
            "id": 10699,
            "title": "Богородское",
            "region_id": 699,
            "__typename": "City"
          },
          {
            "id": 10806,
            "title": "Верхошижемье",
            "region_id": 699,
            "__typename": "City"
          },
          {
            "id": 10877,
            "title": "Вятские Поляны",
            "region_id": 699,
            "__typename": "City"
          },
          {
            "id": 10952,
            "title": "Даровский",
            "region_id": 699,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 700,
        "title": "Чечня",
        "cities": [
          {
            "id": 10558,
            "title": "Аргун",
            "region_id": 700,
            "__typename": "City"
          },
          {
            "id": 10594,
            "title": "Ачхой-Мартан",
            "region_id": 700,
            "__typename": "City"
          },
          {
            "id": 10779,
            "title": "Ведено",
            "region_id": 700,
            "__typename": "City"
          },
          {
            "id": 10928,
            "title": "Грозный",
            "region_id": 700,
            "__typename": "City"
          },
          {
            "id": 10935,
            "title": "Гудермес",
            "region_id": 700,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 701,
        "title": "Мордовия",
        "cities": [
          {
            "id": 10559,
            "title": "Ардатов",
            "region_id": 701,
            "__typename": "City"
          },
          {
            "id": 10587,
            "title": "Атюрьево",
            "region_id": 701,
            "__typename": "City"
          },
          {
            "id": 10588,
            "title": "Атяшево",
            "region_id": 701,
            "__typename": "City"
          },
          {
            "id": 10720,
            "title": "Большие Березняки",
            "region_id": 701,
            "__typename": "City"
          },
          {
            "id": 10724,
            "title": "Большое Игнатово",
            "region_id": 701,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 702,
        "title": "Нижегородская область",
        "cities": [
          {
            "id": 10560,
            "title": "Ардатов",
            "region_id": 702,
            "__typename": "City"
          },
          {
            "id": 10562,
            "title": "Арзамас",
            "region_id": 702,
            "__typename": "City"
          },
          {
            "id": 10617,
            "title": "Балахна",
            "region_id": 702,
            "__typename": "City"
          },
          {
            "id": 10698,
            "title": "Богородск",
            "region_id": 702,
            "__typename": "City"
          },
          {
            "id": 10723,
            "title": "Большое Болдино",
            "region_id": 702,
            "__typename": "City"
          },
          {
            "id": 10725,
            "title": "Большое Мурашкино",
            "region_id": 702,
            "__typename": "City"
          },
          {
            "id": 10735,
            "title": "Бор",
            "region_id": 702,
            "__typename": "City"
          },
          {
            "id": 10761,
            "title": "Бутурлино",
            "region_id": 702,
            "__typename": "City"
          },
          {
            "id": 10767,
            "title": "Вад",
            "region_id": 702,
            "__typename": "City"
          },
          {
            "id": 10775,
            "title": "Варнавино",
            "region_id": 702,
            "__typename": "City"
          },
          {
            "id": 10778,
            "title": "Вача",
            "region_id": 702,
            "__typename": "City"
          },
          {
            "id": 10811,
            "title": "Ветлуга",
            "region_id": 702,
            "__typename": "City"
          },
          {
            "id": 10831,
            "title": "Вознесенское",
            "region_id": 702,
            "__typename": "City"
          },
          {
            "id": 10855,
            "title": "Воротынец",
            "region_id": 702,
            "__typename": "City"
          },
          {
            "id": 10858,
            "title": "Воскресенское",
            "region_id": 702,
            "__typename": "City"
          },
          {
            "id": 10867,
            "title": "Выкса",
            "region_id": 702,
            "__typename": "City"
          },
          {
            "id": 10883,
            "title": "Гагино",
            "region_id": 702,
            "__typename": "City"
          },
          {
            "id": 10913,
            "title": "Городец",
            "region_id": 702,
            "__typename": "City"
          },
          {
            "id": 10948,
            "title": "Дальнее Константиново",
            "region_id": 702,
            "__typename": "City"
          },
          {
            "id": 10963,
            "title": "Дзержинск",
            "region_id": 702,
            "__typename": "City"
          },
          {
            "id": 10964,
            "title": "Дивеево",
            "region_id": 702,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 703,
        "title": "Архангельская область",
        "cities": [
          {
            "id": 10574,
            "title": "Архангельск",
            "region_id": 703,
            "__typename": "City"
          },
          {
            "id": 10669,
            "title": "Березник",
            "region_id": 703,
            "__typename": "City"
          },
          {
            "id": 10786,
            "title": "Вельск",
            "region_id": 703,
            "__typename": "City"
          },
          {
            "id": 10801,
            "title": "Верхняя Тойма",
            "region_id": 703,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 704,
        "title": "Астраханская область",
        "cities": [
          {
            "id": 10584,
            "title": "Астрахань",
            "region_id": 704,
            "__typename": "City"
          },
          {
            "id": 10589,
            "title": "Ахтубинск-1",
            "region_id": 704,
            "__typename": "City"
          },
          {
            "id": 10840,
            "title": "Володарский",
            "region_id": 704,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 705,
        "title": "Камчатка",
        "cities": [
          {
            "id": 10590,
            "title": "Ачайваям",
            "region_id": 705,
            "__typename": "City"
          },
          {
            "id": 10818,
            "title": "Вилючинск",
            "region_id": 705,
            "__typename": "City"
          },
          {
            "id": 10819,
            "title": "Вилючинск-3",
            "region_id": 705,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 706,
        "title": "Вологодская область",
        "cities": [
          {
            "id": 10598,
            "title": "Бабаево",
            "region_id": 706,
            "__typename": "City"
          },
          {
            "id": 10652,
            "title": "Белозерск",
            "region_id": 706,
            "__typename": "City"
          },
          {
            "id": 10784,
            "title": "Великий Устюг",
            "region_id": 706,
            "__typename": "City"
          },
          {
            "id": 10803,
            "title": "Верховажье",
            "region_id": 706,
            "__typename": "City"
          },
          {
            "id": 10830,
            "title": "Вожега",
            "region_id": 706,
            "__typename": "City"
          },
          {
            "id": 10838,
            "title": "Вологда",
            "region_id": 706,
            "__typename": "City"
          },
          {
            "id": 10873,
            "title": "Вытегра",
            "region_id": 706,
            "__typename": "City"
          },
          {
            "id": 10931,
            "title": "Грязовец",
            "region_id": 706,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 707,
        "title": "Калужская область",
        "cities": [
          {
            "id": 10600,
            "title": "Бабынино",
            "region_id": 707,
            "__typename": "City"
          },
          {
            "id": 10615,
            "title": "Балабаново",
            "region_id": 707,
            "__typename": "City"
          },
          {
            "id": 10741,
            "title": "Боровск",
            "region_id": 707,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 708,
        "title": "Новосибирская область",
        "cities": [
          {
            "id": 10603,
            "title": "Баган",
            "region_id": 708,
            "__typename": "City"
          },
          {
            "id": 10624,
            "title": "Барабинск",
            "region_id": 708,
            "__typename": "City"
          },
          {
            "id": 10666,
            "title": "Бердск",
            "region_id": 708,
            "__typename": "City"
          },
          {
            "id": 10709,
            "title": "Болотное",
            "region_id": 708,
            "__typename": "City"
          },
          {
            "id": 10787,
            "title": "Венгерово",
            "region_id": 708,
            "__typename": "City"
          },
          {
            "id": 10982,
            "title": "Довольное",
            "region_id": 708,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 709,
        "title": "Ульяновская область",
        "cities": [
          {
            "id": 10608,
            "title": "Базарный Сызган",
            "region_id": 709,
            "__typename": "City"
          },
          {
            "id": 10628,
            "title": "Барыш",
            "region_id": 709,
            "__typename": "City"
          },
          {
            "id": 10726,
            "title": "Большое Нагаткино",
            "region_id": 709,
            "__typename": "City"
          },
          {
            "id": 10813,
            "title": "Вешкайма",
            "region_id": 709,
            "__typename": "City"
          },
          {
            "id": 10969,
            "title": "Димитровград",
            "region_id": 709,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 710,
        "title": "Алтай",
        "cities": [
          {
            "id": 10610,
            "title": "Байконур",
            "region_id": 710,
            "__typename": "City"
          },
          {
            "id": 10909,
            "title": "Горно-Алтайск",
            "region_id": 710,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 711,
        "title": "Кабардино-Балкария",
        "cities": [
          {
            "id": 10613,
            "title": "Баксан",
            "region_id": 711,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 712,
        "title": "Бурятия",
        "cities": [
          {
            "id": 10625,
            "title": "Баргузин",
            "region_id": 712,
            "__typename": "City"
          },
          {
            "id": 10686,
            "title": "Бичура",
            "region_id": 712,
            "__typename": "City"
          },
          {
            "id": 10942,
            "title": "Гусиноозерск",
            "region_id": 712,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 713,
        "title": "Новгородская область",
        "cities": [
          {
            "id": 10631,
            "title": "Батецкий",
            "region_id": 713,
            "__typename": "City"
          },
          {
            "id": 10740,
            "title": "Боровичи",
            "region_id": 713,
            "__typename": "City"
          },
          {
            "id": 10769,
            "title": "Валдай",
            "region_id": 713,
            "__typename": "City"
          },
          {
            "id": 10783,
            "title": "Великий Новгород",
            "region_id": 713,
            "__typename": "City"
          },
          {
            "id": 10844,
            "title": "Волот",
            "region_id": 713,
            "__typename": "City"
          },
          {
            "id": 10958,
            "title": "Демянск",
            "region_id": 713,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 714,
        "title": "Пензенская область",
        "cities": [
          {
            "id": 10633,
            "title": "Башмаково",
            "region_id": 714,
            "__typename": "City"
          },
          {
            "id": 10634,
            "title": "Беднодемьяновск",
            "region_id": 714,
            "__typename": "City"
          },
          {
            "id": 10639,
            "title": "Беково",
            "region_id": 714,
            "__typename": "City"
          },
          {
            "id": 10648,
            "title": "Белинский",
            "region_id": 714,
            "__typename": "City"
          },
          {
            "id": 10678,
            "title": "Бессоновка",
            "region_id": 714,
            "__typename": "City"
          },
          {
            "id": 10768,
            "title": "Вадинск",
            "region_id": 714,
            "__typename": "City"
          },
          {
            "id": 10914,
            "title": "Городище",
            "region_id": 714,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 715,
        "title": "Псковская область",
        "cities": [
          {
            "id": 10635,
            "title": "Бежаницы",
            "region_id": 715,
            "__typename": "City"
          },
          {
            "id": 10782,
            "title": "Великие Луки",
            "region_id": 715,
            "__typename": "City"
          },
          {
            "id": 10891,
            "title": "Гдов",
            "region_id": 715,
            "__typename": "City"
          },
          {
            "id": 10955,
            "title": "Дедовичи",
            "region_id": 715,
            "__typename": "City"
          },
          {
            "id": 10975,
            "title": "Дно",
            "region_id": 715,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 716,
        "title": "Курская область",
        "cities": [
          {
            "id": 10640,
            "title": "Белая",
            "region_id": 716,
            "__typename": "City"
          },
          {
            "id": 10729,
            "title": "Большое Солдатское",
            "region_id": 716,
            "__typename": "City"
          },
          {
            "id": 10901,
            "title": "Глушково",
            "region_id": 716,
            "__typename": "City"
          },
          {
            "id": 10917,
            "title": "Горшечное",
            "region_id": 716,
            "__typename": "City"
          },
          {
            "id": 10972,
            "title": "Дмитриев-Льговский",
            "region_id": 716,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 717,
        "title": "Амурская область",
        "cities": [
          {
            "id": 10651,
            "title": "Белогорск",
            "region_id": 717,
            "__typename": "City"
          },
          {
            "id": 10689,
            "title": "Благовещенск",
            "region_id": 717,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 718,
        "title": "Карелия",
        "cities": [
          {
            "id": 10655,
            "title": "Беломорск",
            "region_id": 718,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 719,
        "title": "Ханты-Мансийский автономный округ",
        "cities": [
          {
            "id": 10659,
            "title": "Белоярский",
            "region_id": 719,
            "__typename": "City"
          },
          {
            "id": 10674,
            "title": "Березово",
            "region_id": 719,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 720,
        "title": "Еврейская автономная область",
        "cities": [
          {
            "id": 10683,
            "title": "Биробиджан",
            "region_id": 720,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 721,
        "title": "Ленинградская область",
        "cities": [
          {
            "id": 10706,
            "title": "Бокситогорск",
            "region_id": 721,
            "__typename": "City"
          },
          {
            "id": 10843,
            "title": "Волосово",
            "region_id": 721,
            "__typename": "City"
          },
          {
            "id": 10846,
            "title": "Волхов",
            "region_id": 721,
            "__typename": "City"
          },
          {
            "id": 10862,
            "title": "Всеволожск",
            "region_id": 721,
            "__typename": "City"
          },
          {
            "id": 10865,
            "title": "Выборг",
            "region_id": 721,
            "__typename": "City"
          },
          {
            "id": 10888,
            "title": "Гатчина",
            "region_id": 721,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 722,
        "title": "Орловская область",
        "cities": [
          {
            "id": 10710,
            "title": "Болхов",
            "region_id": 722,
            "__typename": "City"
          },
          {
            "id": 10804,
            "title": "Верховье",
            "region_id": 722,
            "__typename": "City"
          },
          {
            "id": 10898,
            "title": "Глазуновка",
            "region_id": 722,
            "__typename": "City"
          },
          {
            "id": 10974,
            "title": "Дмитровск-Орловский",
            "region_id": 722,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 723,
        "title": "Ярославская область",
        "cities": [
          {
            "id": 10728,
            "title": "Большое Село",
            "region_id": 723,
            "__typename": "City"
          },
          {
            "id": 10739,
            "title": "Борисоглебский",
            "region_id": 723,
            "__typename": "City"
          },
          {
            "id": 10748,
            "title": "Брейтово",
            "region_id": 723,
            "__typename": "City"
          },
          {
            "id": 10881,
            "title": "Гаврилов-ям",
            "region_id": 723,
            "__typename": "City"
          },
          {
            "id": 10950,
            "title": "Данилов",
            "region_id": 723,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 724,
        "title": "Калмыкия",
        "cities": [
          {
            "id": 10733,
            "title": "Большой Царын",
            "region_id": 724,
            "__typename": "City"
          },
          {
            "id": 10915,
            "title": "Городовиковск",
            "region_id": 724,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 725,
        "title": "Тамбовская область",
        "cities": [
          {
            "id": 10734,
            "title": "Бондари",
            "region_id": 725,
            "__typename": "City"
          },
          {
            "id": 10879,
            "title": "Гавриловка-2",
            "region_id": 725,
            "__typename": "City"
          },
          {
            "id": 10971,
            "title": "Дмитриевка",
            "region_id": 725,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 726,
        "title": "Брянская область",
        "cities": [
          {
            "id": 10750,
            "title": "Брянск",
            "region_id": 726,
            "__typename": "City"
          },
          {
            "id": 10866,
            "title": "Выгоничи",
            "region_id": 726,
            "__typename": "City"
          },
          {
            "id": 10907,
            "title": "Гордеевка",
            "region_id": 726,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 727,
        "title": "Смоленская область",
        "cities": [
          {
            "id": 10781,
            "title": "Велиж",
            "region_id": 727,
            "__typename": "City"
          },
          {
            "id": 10876,
            "title": "Вязяма",
            "region_id": 727,
            "__typename": "City"
          },
          {
            "id": 10882,
            "title": "Гагарин",
            "region_id": 727,
            "__typename": "City"
          },
          {
            "id": 10899,
            "title": "Глинка",
            "region_id": 727,
            "__typename": "City"
          },
          {
            "id": 10956,
            "title": "Демидов",
            "region_id": 727,
            "__typename": "City"
          },
          {
            "id": 10961,
            "title": "Десногорск",
            "region_id": 727,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 728,
        "title": "Ивановская область",
        "cities": [
          {
            "id": 10795,
            "title": "Верхний Ландех",
            "region_id": 728,
            "__typename": "City"
          },
          {
            "id": 10820,
            "title": "Вичуга",
            "region_id": 728,
            "__typename": "City"
          },
          {
            "id": 10878,
            "title": "Гаврилов Посад",
            "region_id": 728,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 729,
        "title": "Волгоградская область",
        "cities": [
          {
            "id": 10832,
            "title": "Волгоград",
            "region_id": 729,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 730,
        "title": "Марий Эл",
        "cities": [
          {
            "id": 10835,
            "title": "Волжск",
            "region_id": 730,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 731,
        "title": "Липецкая область",
        "cities": [
          {
            "id": 10836,
            "title": "Волово",
            "region_id": 731,
            "__typename": "City"
          },
          {
            "id": 10930,
            "title": "Грязи",
            "region_id": 731,
            "__typename": "City"
          },
          {
            "id": 10951,
            "title": "Данков",
            "region_id": 731,
            "__typename": "City"
          },
          {
            "id": 10976,
            "title": "Добринка",
            "region_id": 731,
            "__typename": "City"
          },
          {
            "id": 10979,
            "title": "Доброе",
            "region_id": 731,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 732,
        "title": "Московская область",
        "cities": [
          {
            "id": 10841,
            "title": "Волоколамск",
            "region_id": 732,
            "__typename": "City"
          },
          {
            "id": 10856,
            "title": "Воскресенск",
            "region_id": 732,
            "__typename": "City"
          },
          {
            "id": 10903,
            "title": "Голицыно",
            "region_id": 732,
            "__typename": "City"
          },
          {
            "id": 10973,
            "title": "Дмитров",
            "region_id": 732,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      },
      {
        "id": 733,
        "title": "Дагестан",
        "cities": [
          {
            "id": 10959,
            "title": "Дербент",
            "region_id": 733,
            "__typename": "City"
          }
        ],
        "__typename": "Region"
      }
    ]
  }),
}
</script>
