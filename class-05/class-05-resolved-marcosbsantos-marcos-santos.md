##MongoDB -Aula05- Exercícios
##autor: MARCOS SANTOS

##1. Importar as collections restaurantes e pokemons:

b$ mongoimport --host 127.0.0.1 --db be-mean-instagram --collection restaurantes --drop --file /home/marcos/Documentos/bemean/mongodb/restaurantes.json
2015-12-04T15:03:40.254-0300	connected to: 127.0.0.1
2015-12-04T15:03:40.255-0300	dropping: be-mean-instagram.restaurantes
2015-12-04T15:03:41.315-0300	imported 25359 documents

$ mongoimport --host 127.0.0.1 --db be-mean-instagram --collection pokemons --drop --file /home/marcos/Documentos/bemean/mongodb/pokemons.json
2015-12-04T15:26:47.752-0300	connected to: 127.0.0.1
2015-12-04T15:26:47.753-0300	dropping: be-mean-instagram.pokemons
2015-12-04T15:26:47.778-0300	imported 610 documents


##2. Distinct por cuisine na restaurantes:

be-mean-instagram> db.restaurantes.distinct('cuisine')
[
  "Bakery",
  "Jewish/Kosher",
  "American ",
  "Hamburgers",
  "Delicatessen",
  "Ice Cream, Gelato, Yogurt, Ices",
  "Chinese",
  "Irish",
  "Other",
  "Chicken",
  "Turkish",
  "Caribbean",
  "Donuts",
  "Sandwiches/Salads/Mixed Buffet",
  "Bagels/Pretzels",
  "Continental",
  "Pizza",
  "Italian",
  "Steak",
  "Polish",
  "Latin (Cuban, Dominican, Puerto Rican, South & Central American)",
  "German",
  "French",
  "Pizza/Italian",
  "Mexican",
  "Spanish",
  "Café/Coffee/Tea",
  "Tex-Mex",
  "Pancakes/Waffles",
  "Soul Food",
  "Seafood",
  "Hotdogs",
  "Greek",
  "Not Listed/Not Applicable",
  "African",
  "Japanese",
  "Indian",
  "Armenian",
  "Thai",
  "Chinese/Cuban",
  "Mediterranean",
  "Korean",
  "Bottled beverages, including water, sodas, juices, etc.",
  "Russian",
  "Eastern European",
  "Middle Eastern",
  "Asian",
  "Ethiopian",
  "Vegetarian",
  "Barbecue",
  "Egyptian",
  "English",
  "Sandwiches",
  "Portuguese",
  "Indonesian",
  "Chinese/Japanese",
  "Filipino",
  "Juice, Smoothies, Fruit Salads",
  "Brazilian",
  "Afghan",
  "Vietnamese/Cambodian/Malaysia",
  "CafÃ©/Coffee/Tea",
  "Soups & Sandwiches",
  "Tapas",
  "Moroccan",
  "Pakistani",
  "Peruvian",
  "Bangladeshi",
  "Czech",
  "Salads",
  "Creole",
  "Fruits/Vegetables",
  "Iranian",
  "Cajun",
  "Scandinavian",
  "Polynesian",
  "Soups",
  "Australian",
  "Hotdogs/Pretzels",
  "Southwestern",
  "Nuts/Confectionary",
  "Hawaiian",
  "Creole/Cajun",
  "Californian",
  "Chilean"
]

##3- Distinct por types na pokemons:

 be-mean-instagram> db.pokemons.distinct('types')
[
  "fire",
  "water",
  "normal",
  "bug",
  "flying",
  "poison",
  "electric",
  "steel",
  "ice",
  "ghost",
  "fighting",
  "psychic",
  "grass",
  "ground",
  "fairy",
  "rock",
  "dark",
  "dragon"
]

##4. As primeiras 3 páginas com .limit() e .skip() de pokemons (5 em 5):

db.pokemons.find().limit(5).skip(5*0)
{
  "_id": ObjectId("564b1dad25337263280d047a"),
  "attack": 52,
  "created": "2013-11-03T15:05:41.271082",
  "defense": 43,
  "height": "6",
  "hp": 39,
  "name": "Charmander",
  "speed": 65,
  "types": [
    "fire"
  ]
}
{
  "_id": ObjectId("564b1dad25337263280d047c"),
  "attack": 63,
  "created": "2013-11-03T15:05:41.280718",
  "defense": 80,
  "height": "10",
  "hp": 59,
  "name": "Wartortle",
  "speed": 58,
  "types": [
    "water"
  ]
}
{
  "_id": ObjectId("564b1dad25337263280d047d"),
  "attack": 83,
  "created": "2013-11-03T15:05:41.282985",
  "defense": 100,
  "height": "16",
  "hp": 79,
  "name": "Blastoise",
  "speed": 78,
  "types": [
    "water"
  ]
}
{
  "_id": ObjectId("564b1dad25337263280d0479"),
  "attack": 56,
  "created": "2013-11-03T15:05:41.305777",
  "defense": 35,
  "height": "3",
  "hp": 30,
  "name": "Rattata",
  "speed": 72,
  "types": [
    "normal"
  ]
}
{
  "_id": ObjectId("564b1dad25337263280d047e"),
  "attack": 30,
  "created": "2013-11-03T15:05:41.285736",
  "defense": 35,
  "height": "3",
  "hp": 45,
  "name": "Caterpie",
  "speed": 45,
  "types": [
    "bug"
  ]
}
Fetched 5 record(s) in 3ms


 db.pokemons.find().limit(5).skip(5*1)
{
  "_id": ObjectId("564b1dad25337263280d047f"),
  "attack": 20,
  "created": "2013-11-03T15:05:41.288107",
  "defense": 55,
  "height": "7",
  "hp": 50,
  "name": "Metapod",
  "speed": 30,
  "types": [
    "bug"
  ]
}
{
  "_id": ObjectId("564b1dad25337263280d047b"),
  "attack": 64,
  "created": "2013-11-03T15:05:41.273462",
  "defense": 58,
  "height": "11",
  "hp": 58,
  "name": "Charmeleon",
  "speed": 80,
  "types": [
    "fire"
  ]
}
{
  "_id": ObjectId("564b1dad25337263280d0480"),
  "attack": 45,
  "created": "2013-11-03T15:05:41.290411",
  "defense": 50,
  "height": "11",
  "hp": 60,
  "name": "Butterfree",
  "speed": 70,
  "types": [
    "flying",
    "bug"
  ]
}
{
  "_id": ObjectId("564b1dad25337263280d0481"),
  "attack": 60,
  "created": "2013-11-03T15:05:41.310402",
  "defense": 30,
  "height": "3",
  "hp": 40,
  "name": "Spearow",
  "speed": 70,
  "types": [
    "normal",
    "flying"
  ]
}
{
  "_id": ObjectId("564b1dad25337263280d0482"),
  "attack": 25,
  "created": "2013-11-03T15:05:41.294947",
  "defense": 50,
  "height": "6",
  "hp": 45,
  "name": "Kakuna",
  "speed": 35,
  "types": [
    "poison",
    "bug"
  ]
}
Fetched 5 record(s) in 3ms


 be-mean-instagram> db.pokemons.find().limit(5).skip(5*2)
{
  "_id": ObjectId("564b1dae25337263280d0483"),
  "attack": 65,
  "created": "2013-11-03T15:05:41.439497",
  "defense": 55,
  "height": "8",
  "hp": 52,
  "name": "Farfetchd",
  "speed": 60,
  "types": [
    "normal",
    "flying"
  ]
}
{
  "_id": ObjectId("564b1dae25337263280d0484"),
  "attack": 35,
  "created": "2013-11-03T15:05:41.435237",
  "defense": 70,
  "height": "3",
  "hp": 25,
  "name": "Magnemite",
  "speed": 45,
  "types": [
    "steel",
    "electric"
  ]
}
{
  "_id": ObjectId("564b1dae25337263280d0486"),
  "attack": 85,
  "created": "2013-11-03T15:05:41.441502",
  "defense": 45,
  "height": "14",
  "hp": 35,
  "name": "Doduo",
  "speed": 75,
  "types": [
    "normal",
    "flying"
  ]
}
{
  "_id": ObjectId("564b1dae25337263280d0485"),
  "attack": 60,
  "created": "2013-11-03T15:05:41.437483",
  "defense": 95,
  "height": "10",
  "hp": 50,
  "name": "Magneton",
  "speed": 70,
  "types": [
    "steel",
    "electric"
  ]
}
{
  "_id": ObjectId("564b1dae25337263280d0488"),
  "attack": 110,
  "created": "2013-11-03T15:05:41.443720",
  "defense": 70,
  "height": "18",
  "hp": 60,
  "name": "Dodrio",
  "speed": 100,
  "types": [
    "normal",
    "flying"
  ]
}
Fetched 5 record(s) in 2ms


##5 . Group ou Aggregate contando a quantidade de pokemons de cada tipo:

be-mean-instagram> db.pokemons.aggregate([
... {$unwind:'$types'},
... {$group:{
... _id:'$types',
... QtdTypes:{$sum:1}}
... }
... ])
{
  "result": [
    {
      "_id": "fairy",
      "QtdTypes": 28
    },
    {
      "_id": "psychic",
      "QtdTypes": 62
    },
    {
      "_id": "fighting",
      "QtdTypes": 38
    },
    {
      "_id": "dark",
      "QtdTypes": 38
    },
    {
      "_id": "ground",
      "QtdTypes": 51
    },
    {
      "_id": "grass",
      "QtdTypes": 75
    },
    {
      "_id": "electric",
      "QtdTypes": 40
    },
    {
      "_id": "steel",
      "QtdTypes": 37
    },
    {
      "_id": "rock",
      "QtdTypes": 46
    },
    {
      "_id": "flying",
      "QtdTypes": 77
    },
    {
      "_id": "fire",
      "QtdTypes": 47
    },
    {
      "_id": "ice",
      "QtdTypes": 24
    },
    {
      "_id": "bug",
      "QtdTypes": 61
    },
    {
      "_id": "poison",
      "QtdTypes": 54
    },
    {
      "_id": "ghost",
      "QtdTypes": 34
    },
    {
      "_id": "dragon",
      "QtdTypes": 20
    },
    {
      "_id": "water",
      "QtdTypes": 105
    },
    {
      "_id": "normal",
      "QtdTypes": 78
    }
  ],
  "ok": 1
}


##6. Realizar 3 counts na pokemons:

 be-mean-instagram> db.pokemons.count({})
610


 be-mean-instagram> db.pokemons.count({types:'fire'})
47


 db.pokemons.count({defense:{$gt:70}})
250

