# DT-Auto
Dofus Touch bot socket written in python.

- HTTP Authentication with cloudscraper
- Game authentication with socket
- Game management with socket
- Command-line only

Current functionnalities:
  - Fight
  - Move
  - Interaction with npcs (dialogs, buy/sell items)
  - Conditionnals programmation of paths (eg: execute dialog with given npc only if character have job id 41, move to right if character's lvl >15, etc..)
  - Group ( instable)
  - Auto character creation
  - Bypass tutorial step for new account

Paths configuration:
  - name
  - restrict fight by monsters id to fight only agaisnt given monsters  (however, fight against every monsters)
  - ia to use in fight
  - bank path  
  - conditions
  - dialogs with conditions


Data models:
  - Account: JSON file
  - Paths: JSON file
  - basic configuration: 
    - ```{"name":"inca to astrub","monsters":[],"ia":"","bank":{},"path":{
        "{ 
          -5,-1":{
             "harvest":false,
             "fight":false,
             "move":[{"S":{"conditions":[]}}]
          },
          "-4,0":{
             "harvest":false,
             "fight":false,
             "move":[{"R":{"conditions":[]}}]
          }
        }
  - dialogs with conditions:
    -  ``` {
        "9,3": {
        "fight": false,
        "harvest": false,
        "dialog": [
          {
            "888": {
              "conditions": [
                {"dontHaveJobId": 41}
              ],
              "action": 3,
              "messages": {
                "9828": [10537,10539],
	              "9829": [10535],
                "9830": [10540],
                "17400": [33028]
              }
            }
          }
        ]
      
        
  - more advanced dialog:
    -  ``` { "2,-24":{
         "harvest":false,
         "fight":false,
         "move":[
           {"L":
             {"conditions":[
                  {"haveJobId": 41}
                ]
               }
             }
         ],
         "dialog": [
           {
             "564": {
               "conditions": [
                 {"dontHaveJobId": 41}
               ],
               "action": 3,
               "messages": {
                 "2357": [1962,8835],
                 "2358": [1963],
                 "2359": [1964],
                 "2361": [1965],
                 "2362": [1966],
                 "8800": [1968],
                 "1175": [845]
               }
             }
           },
           {
             "564b":{
               "conditions": [
                 {"haveJobId": 41},
                 {"dontHaveWeaponSet": 1934}
               ],
               "action": 1,
               "buy": 1934,
               "messages":{}
             }
           }
         ]```
         
- Views:
  - ![image](https://user-images.githubusercontent.com/45556777/118512627-455efc00-b733-11eb-9f01-d480c6da11c1.png)
  - ![image](https://user-images.githubusercontent.com/45556777/118512745-5dcf1680-b733-11eb-97f4-4345be1f87a4.png)

