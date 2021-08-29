# Soil Moisture Content Dataset

This repository contains the hyperspectral and multispectral datasets used to obtain the results published in 
*Machine Learning for Soil Moisture Prediction Using Hyperspectral and Multispectral Data*. The three main datasets used are presented here.

## Hyperspectral

The [hyperspectral](https://github.com/amlobat2/smc-data/blob/main/hyperspectral_dataset.csv) dataset is a modified version of the original dataset published 
[here](https://github.com/felixriese/hyperspectral-soilmoisture-dataset/blob/master/README.md). The dataset contains 1951 ground truth soil moisture points and
the correspoding reflectance values of 115 spectral bands (470-930). A sample of the hyperspectral dataset is presented below. The soil temperature column was removed for the models where the temperature data was omitted.

| soil_moisture | soil_temperature |    x470    |    x474    |    x478    |    x482    |    x486    | ....... |    x914    |    x918    |    x922    |    x926    |    x930    |
|:-------------:|:----------------:|:----------:|:----------:|:----------:|:----------:|:----------:|:-------:|:----------:|:----------:|:----------:|:----------:|:----------:|
|     10.27     |       29.4       | 0.10123852 | 0.10188183 | 0.10201255 | 0.09744575 | 0.09515578 | ....... | 0.71040456 | 0.71463732 | 0.71226611 | 0.71242056 | 0.72392433 |
|     21.71     |       27.2       | 0.10253147 |  0.0948334 | 0.10382726 | 0.09437256 | 0.10021864 | ....... | 0.72635033 | 0.72040551 | 0.71101871 | 0.71305608 | 0.72743108 |
|     21.06     |       28.4       |  0.0928343 | 0.08586267 | 0.08321736 | 0.08515299 | 0.08386171 | ....... | 0.69956962 | 0.70145289 |  0.695842  | 0.68869439 | 0.69806206 |
|     20.48     |        25        | 0.09386866 | 0.09124511 | 0.09151317 | 0.09257986 | 0.09567505 | ....... | 0.69588982 | 0.68847447 | 0.68586279 | 0.68551678 | 0.69236359 |
|     21.55     |       28.8       | 0.10266077 | 0.10828949 | 0.11004912 | 0.10384823 | 0.10307461 | ....... | 0.64682591 | 0.64006289 | 0.63264033 | 0.63827629 | 0.65137848 |  

### Variables
- **soil_moisture** - soil moisture values in % 
- **soil_temperature** - soil temperature in &deg;C
- **x470, x474, x478, ..., x926, x930** - hyperspectral bands in nm 


## Reduced Dimensionality

The [reduced dimensionality](https://github.com/amlobat2/smc-data/blob/main/reduced_dimensionality.csv) (RD) dataset was created by choosing a feature subset and stacking the hyperspectral bands within the feature subset. The RD dataset contains 1951 ground truth soil moisture points and the corresponding reflectance values in 5 bands. The soil temperature column was removed for the models where the temperature data was omitted.
| soil_moisture | soil_temperature |     blue    |    green    |     red     |  red_edge  |     NIR    |
|:-------------:|:----------------:|:-----------:|:-----------:|:-----------:|:----------:|:----------:|
|     10.27     |       29.4       | 0.128551712 | 0.228878874 | 0.184808207 | 0.40328229 | 0.66312774 |
|     21.71     |       27.2       | 0.148152586 | 0.227744493 | 0.181546818 | 0.38209847 | 0.68942599 |
|     21.06     |       28.4       | 0.118751901 | 0.216170728 | 0.165292882 | 0.38051135 | 0.67027718 |
|     20.48     |        25        | 0.140188288 | 0.218833551 | 0.171301754 | 0.37484883 | 0.66981131 |
|     21.55     |       28.8       | 0.136302494 | 0.214982368 | 0.193116278 | 0.38742031 |  0.5994437 |


### Variables
- **soil_moisture** - soil moisture values in % 
- **soil_temperature** - soil temperature in &deg;C
- **blue, green, red, red_edge, NIR** - stacked hyperspectral bands in multispectral feature subset  


## Combined Multispectral
The final dataset, the [combined multispectral](https://github.com/amlobat2/smc-data/blob/main/combined_multispectral.csv) dataset, contains the data from the RD dataset, as well as data collected from a Sentera Double 4K multispectral sensor. There are 2134 datapoints in this dataset. The structure of the data is exactly the same as the RD dataset. 

### Variables
- **soil_moisture** - soil moisture values in % 
- **soil_temperature** - soil temperature in &deg;C
- **blue, green, red, red_edge, NIR** - stacked hyperspectral bands in multispectral feature subset & collected multispectral data 

# Cite this dataset


```
@misc{lobatosmc,
    author = {Lobato, Michaela, and Norris, William Robert, and Nagi, Rakesh},
    title = {Hyperspectral and multispectral soil moisture dataset},
    year = {2021},
    publisher = {GitHub},
    howpublished = {\url{https://github.com/amlobat2/soilmoisturecontent-data}}
}
```
