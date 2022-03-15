
# Objetivo: Modelo para seleccionar el mejor tipo de grano dadas las condiciones de suelo.
# Objetivo 2: Modelo de predicción de fertilizante dado un tipo de suelo y un tipo de grano.

Se usaron diferentes modelos que se los hizo competir por el mejor score.

## Authors

- [@econtarino](https://www.github.com/econtarino)


## Features

- N -> Nitrogen (Nitrogeno en el suelo).
- P -> phosphorus (Fosforo en el suelo).
- K -> Potassium (Potasio en el suelo).
- temperature -> temperatura.
- humidity -> valores de humedad.
- ph -> ph del suelo
- rainfall ->  cantidad de lluvia.
- label -> (target to calculate type of corn)


## Target

- Label -> Tipo de grano a predecir.

## Installation

Para correr el proyecto usar el csv dentro de la carpeta Datos del proyecto descargardo el siguiente archivo

```bash
  curl 'https://storage.googleapis.com/kagglesdsdata/datasets/1046158/1760012/Crop_recommendation.csv?X-Goog-Algorithm=GOOG4-RSA-SHA256&X-Goog-Credential=gcp-kaggle-com%40kaggle-161607.iam.gserviceaccount.com%2F20220314%2Fauto%2Fstorage%2Fgoog4_request&X-Goog-Date=20220314T044435Z&X-Goog-Expires=259199&X-Goog-SignedHeaders=host&X-Goog-Signature=a1e0b871d4c5a7792d1893b582a795df534aa07d8c597e17d7fb44d235fb6544b41e7413031b888b99b4695d525ae311a3f8e393ab5fed4f8afa4dde59c9d5a441e8f88fd34cac54ae3a932575cf51cba74057169b5f95017c7c75ae86117ee5af9500c887950f8203fc39be5c234960b19d44f6165f918ac1d11349a53e621f7ffdde4374a5f75029614f1d890f3171dcef3d3e35f91217131db43a2124fd660f1b424b08967f26423683d5df792faf4c6e12400e8d0a34db39bfe4dba6137fd4bed94456b3764bd441a0ddd94d790563d3ed958612c43a83ecae27e74c20e4ac18c8ba386405b4faa417fb39e27aee53af1aa2b74bc6a3c70eb9d79fe350bd' \
  -H 'authority: storage.googleapis.com' \
  -H 'upgrade-insecure-requests: 1' \
  -H 'user-agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36' \
  -H 'accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9' \
  -H 'sec-fetch-site: cross-site' \
  -H 'sec-fetch-mode: navigate' \
  -H 'sec-fetch-user: ?1' \
  -H 'sec-fetch-dest: document' \
  -H 'sec-ch-ua: " Not;A Brand";v="99", "Google Chrome";v="97", "Chromium";v="97"' \
  -H 'sec-ch-ua-mobile: ?0' \
  -H 'sec-ch-ua-platform: "macOS"' \
  -H 'referer: https://www.kaggle.com/' \
  -H 'accept-language: es-ES,es;q=0.9,en;q=0.8' \
  --compressed > crop_recomendation.csv


  curl 'https://storage.googleapis.com/kagglesdsdata/datasets/420288/802720/Fertilizer%20Prediction.csv?X-Goog-Algorithm=GOOG4-RSA-SHA256&X-Goog-Credential=gcp-kaggle-com%40kaggle-161607.iam.gserviceaccount.com%2F20220314%2Fauto%2Fstorage%2Fgoog4_request&X-Goog-Date=20220314T163710Z&X-Goog-Expires=259199&X-Goog-SignedHeaders=host&X-Goog-Signature=05513f02a7eb5b0a5fe0e0dedf06fafdc0a50c6372c698c273fadc1abfd990c0f827b40eeb4bd7659e3a871643452f5a77e6d9c0e051e1292085141cc6ea3e15bdcf5419e4041fef944ee0542bc8288ae91f73d0347af187a05144c7e53fbfe5b95ec49e4a263dbedcd587a28a42cc040ed742a886eabec2887b4f69fd450c4eda3c9d43aca7f107edd9500954a993b4acd15db9c8d1f1737d3a93990c240f905fab38caef29b478278ca317f9696f0f8d4faf984cf3579a0506fc37216cf422bc7c45c8cde8dbd5ce93753a9008fc06d77a14bea5c0bbb38c65bec8b24de08eaf4aed750ec23d9ee191112bf8c17f4f477fbcc00ee8c2999f4714452105c4e4' \
  -H 'authority: storage.googleapis.com' \
  -H 'upgrade-insecure-requests: 1' \
  -H 'user-agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.51 Safari/537.36' \
  -H 'accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9' \
  -H 'sec-fetch-site: cross-site' \
  -H 'sec-fetch-mode: navigate' \
  -H 'sec-fetch-user: ?1' \
  -H 'sec-fetch-dest: document' \
  -H 'sec-ch-ua: " Not A;Brand";v="99", "Chromium";v="99", "Google Chrome";v="99"' \
  -H 'sec-ch-ua-mobile: ?0' \
  -H 'sec-ch-ua-platform: "macOS"' \
  -H 'referer: https://www.kaggle.com/' \
  -H 'accept-language: es-ES,es;q=0.9,en;q=0.8' \
  --compressed > fertilizer_prediction.csv
```
    
## ¿Por qué se tomo este problema?

En Argentina y Brasil las ganancias mas grandes de exportación son de Agricultura.

Esto afecta directamente la economia en el PBI, indicadores KPIS de los paises de latam.

### Datos del PBI distribuido por sector en Argentina 64 Billones dolarés.
<img src="images/gdp_argentina.png">

### Datos del PBI distribuido por sector en Brasil 230 Billones dolarés (tiene una exportación X3 mas grande que Argentina).
#### Se visualizan grandes exportaciones de soja maiz y café que sumadas son el 21,54% del PBI (50B dolarés casi todo el pbi de Arg sumando todos los sectores).
#### Brasil es un pais estratégico para realizar ventas de servicios por su alto impacto en la economía de latino América. 
<img src="images/gdp_brasil.png">

### Uruguay mercado mas chico pero con una gran exportación Total 9B dolarés.
<img src="images/gdp_uruguay.png">


## Precio de las comodities después de la recesión del covid y debido a la guerra en Europa.
## Dado el conflicto aumentaron a valores a precios históricos con esto dando una oportunidad de crecimiento a los grandes exportadores.
## Por esta razón es vital conectar al agro con los datos para aumentar su productividad.
<img src="images/soja.png">
