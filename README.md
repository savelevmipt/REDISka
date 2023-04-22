Сначала развернем Redis в docker

<img width="1280" alt="image" src="https://user-images.githubusercontent.com/100207961/233781259-12e28fe8-0bde-4938-8470-d69e7f37ebae.png">

Мы будем сравнивать Redis и Redis-cluster, поэтому сразу запустим еще и Redis-cluster на другом порте.

<img width="1049" alt="image" src="https://user-images.githubusercontent.com/100207961/233781392-2fd62986-d984-4d25-8277-07bc15b49662.png">
<img width="1205" alt="image" src="https://user-images.githubusercontent.com/100207961/233781418-7c9539b3-10b8-4495-866b-32ee31854e2e.png">

Произведем разные запросы без кластера и с кластером. Для визуализации расположим данные в параллельных окнах.

<img width="1216" alt="image" src="https://user-images.githubusercontent.com/100207961/233781461-cc6af2f1-76da-4dfe-8a03-62b4443d8287.png">
<img width="1223" alt="image" src="https://user-images.githubusercontent.com/100207961/233781477-1d989ca2-36b2-4a36-82e4-9b115626bb15.png">
<img width="1226" alt="image" src="https://user-images.githubusercontent.com/100207961/233781492-8be450a2-aeeb-41ac-8618-e9f25c7c7aa6.png">

Видно, что для hset время выполнения увеличилось почти в два раза, что свидетельствует о том, что требовалось время для распределения данных по узлам системы.
Для zadd время также увеличилось, но уже в полтора раза.

А вот когда мы загружали большую строку, время почти не поменялось, так как вся строка попала на одну фиксированную ноду.
