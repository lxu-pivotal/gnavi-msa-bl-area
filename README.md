Welcome to gnavi-msa-bl-area!
===================

Overview
-------------

Business Logic layer for area.

-------------
Deployment to Cloud Foundry
-------------
git clone this repository and this msa branch.

Remember to install [cf cli](https://github.com/cloudfoundry/cli/releases).
After login, push the application:
```
cf push
```

You can access your app at 
```
http://gnavi-msa-bl-area.<your_cf_domain>/api
```

-------------
For Training Steps
-------------
Please check if the MicroServices which act as business logic layers provide expected data to the presentation layer.

Test the 'area' business logic layer which has been deployed on CF:
```
curl -X GET "http://gnavi-msa-bl-area.<your_cf_domain>/api/prefectures"
curl -X GET "http://gnavi-msa-bl-area.<your_cf_domain>/api/areas"
curl -X GET "http://gnavi-msa-bl-area.<your_cf_domain>/api/count_by_area"
curl -H "Content-Type: application/json" -X POST "http://gnavi-msa-bl-area.<your_cf_domain>/api/count_by_area_cat" -d '{"areaList":[{"area_code":"AREA130","area_name":"中部"}],"catList":[{"category_l_code":"RSFST09000","category_l_name":"居酒屋"},{"category_l_code":"RSFST02000","category_l_name":"日本料理・郷土料理"},{"category_l_code":"RSFST03000","category_l_name":"すし・魚料理・シーフード"}]}'
```

Test the 'area' business logic layer which is started locally:
```
npm start
curl -X GET "http://localhost:9000/api/prefectures"
curl -X GET "http://localhost:9000/api/areas"
curl -X GET "http://localhost:9000/api/count_by_area"
curl -H "Content-Type: application/json" -X POST "http://localhost:9000/api/count_by_area_cat" -d '{"areaList":[{"area_code":"AREA130","area_name":"中部"}],"catList":[{"category_l_code":"RSFST09000","category_l_name":"居酒屋"},{"category_l_code":"RSFST02000","category_l_name":"日本料理・郷土料理"},{"category_l_code":"RSFST03000","category_l_name":"すし・魚料理・シーフード"}]}'
```

-------------
Schedule & Progress of Training Steps
-------------

###Follow the TODOs at the following files.

**/manifest.yml**
+ Step1: Cover TODO_01.

**/controllers/prefsController.js**
+ Step1: Cover TODO_01, 02, 03.

**/controllers/areasController.js**
+ Step1: Cover TODO_01, 02, 03 & 04.

**/controllers/countByAreaController.js**
+ Step2: Cover TODO_01, 02, 03, 04 & 05.

**/controllers/countByAreaController.js**
+ Step3: Cover TODO_01, 02, 03, 04 & 05.