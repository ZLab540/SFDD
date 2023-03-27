# SFDD
This is the sea fog detection dataset mentioned in the paper “Dual-Branch Neural Network for Sea Fog Detection in Geostationary Ocean Color Imager”

A dataset with rich categories, sufficient data, and accurate annotation is the cornerstone of a deep-learning-based sea fog detection algorithm. In the past, annotations for sea fog areas were at the station level. That is, the sea fog was only sparsely recorded by individual ocean sites or buoys. Compared to these station-level labels, the labels in SFDD are pixel-level annotated based on satellite imagery and weather forecast reports. To the best of our knowledge, the proposed SFDD is the first SFDD with an extended period, large sample number, and pixel-level labeling.

## Satellite Data
The satellite data used to construct the dataset is the Level-2C multispectral data from GOCI. GOCI is one of the three payloads onboard the Communication, Ocean and Meteorological Satellite (COMS). It is the world’s first geostationary orbit satellite image sensor used for the observation or monitoring of ocean color around the Korean peninsula. The spatial resolution of GOCI is 500 m, and the imaging area is 2500 km × 2500 km centered on 130◦E, 36◦N [as shown in Fig. 1(a)]. GOCI provides satellite images at hourly intervals up to eight times a day from 00:16 to 07:16 UTC, allowing observations of short-term changes in the northeast Asia region. Six visible bands and two near-infrared bands are provided by GOCI.

## Construction of Sea Fog Detection Dataset
The National Satellite Meteorological Centre (NSMC) of China has recorded fog events over the past ten years. During the ten years from 2011 to 2020, 133 sea fog incidents occurred in the Yellow Sea and the Bohai Sea. Based on each record, we downloaded GOCI Level-2C remote sensing images (after radiation correction, geometric correction, and atmospheric correction) on the corresponding date. From 00:00 to 08:00 UTC, GOCI takes one shot every hour and records eight bands of spectral information for each shot. We selected 490-, 550-, and 680-nm wavebands as the red, green, and blue channels to form color images. The region-of-interest area (118.1◦E–128.1◦E, 29.5◦N–43.8◦N) is cropped from the color image. 

The fog inversion product released by NSMC is used as ground truth. In this product, fog areas are manually labeled by meteorological experts according to the fog product inversion manual of the NSMC. The labeling process is given as follows:
1) L1B level reflectance data are obtained from the Fengyun Geostationary satellite. 
2) Sea fog inversion is performed on reflectance data and terrain data using a threshold-based inversion algorithm.
3) Meteorologists correct the inversion results of Step 2 by using the visibility information recorded by the observation stations. 
4) Meteorologists make a second correction based on their experience.

Three meteorological experts were hired to manually annotate the GOCI data using the fog inversion product of NSMC according to the latitude and longitude. Each expert independently completed the annotation without interference from the others. The winner-takes-all strategy was used to generate a more reliable label mask as the ground truth for error analysis.

## Statistical Analysis of Sea Fog Detection Dataset
The main findings are given as follows. 
1) The fog season onset is abrupt, with the number of fog days increasing rapidly from March to April. 
2) The frequency of sea fog incidence suddenly drops from its peak in July to almost zero in August. 
3) In the Bohai Sea, only the coasts of the Liaodong peninsula and the Shandong peninsula have sea fog.
4) Sea fog appears most frequently in the central part of the Yellow Sea and the West Korea Bay.

## Citing
If you use this dataset in scientific context, please cite the following publications:
> Y. Zhou, K. Chen and X. Li, "Dual-Branch Neural Network for Sea Fog Detection in Geostationary Ocean Color Imager," in IEEE Transactions on Geoscience and Remote Sensing, vol. 60, pp. 1-17, 2022, Art no. 4208617, doi: 10.1109/TGRS.2022.3196177.

BibTeX details:

```bibtex

@article{zhou2022dual,
  title={Dual-Branch Neural Network for Sea Fog Detection in Geostationary Ocean Color Imager},
  author={Zhou, Yuan and Chen, Keran and Li, Xiaofeng},
  journal={IEEE Transactions on Geoscience and Remote Sensing},
  volume={60},
  pages={1--17},
  year={2022},
  publisher={IEEE}
}
```

## License

<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/">Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License</a>.

For commercial use, please contact us for further information.
