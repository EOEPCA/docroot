# STAC Tools and Utilities

## Introduction

STAC has emerged as the primary means for passing data in/out of processing workflows, including:

* openEO - via load_stac() and between steps within the processing graph
* OGC Application Packages - data in/out as described by the OGC Best Practice for Application packages

In support, we identify here a set of tools and utilities that have been created by the EOEPCA project and its partners, that help use of STAC for data in/out.

---

## STAC Catalogue Utilities

It was motivated to support developers of OGC Application Packages to help them present the results (output data) of their containerised algorithm as a STAC catalogue, in accordance with the OGC Best Practice for Application packages.

It is a python library that abstracts the STAC file formats. The idea being that the application package would invoke this library on the data outputs as the end of the processing.

See the GitHub repo - https://github.com/EOEPCA/stac-cat-utils

---

## MLOps STAC Abstractions

Designed to support the [MLOps BB](https://eoepca.readthedocs.io/projects/mlops), which is able to execute model inference by encapsulating the model in a container and executing as an Application Package via API Processes.

In the case of ML models that are not coded to exploit STAC for data in/out (e.g. expecting just a directory of files as input) - then the MLOps BB introduces pre/post containers into the inference workflow to abstract STAC in/out from the ML execution. These containers rely upon a python helper library, that provides a simple pathway for the packaged model to transparently satisfy the STAC in/out expectations of the OGC Best Practice for Application Packages.

Link to git repos pending...

---

## STAC Catalogue Builder

This tool generates a STAC collection from a set of GeoTiff images.

It is mainly intended to create STAC collections and catalogs for use in openEO, with the load_stac process.

It requires some configuration for the fields we need to fill in, but the goal is to make it much easier to generate STAC collections from a set of EO images.

For now it only supports GeoTIFFs. For example, netCDF is not supported yet, because it can be a lot more complex to extract info from than GeoTIFF. According to needs, support beyond GeoTIFFs will be considered as required.

Support for uploading to a STAC API is in the making.

See the GitHub repo - https://github.com/VitoTAP/stac-catalog-builder

See also the (additional) use cases - https://github.com/VitoTAP/stac-catalog-builder/blob/main/docs/goals-and-user-stories.md

---

## rio-stac

`rio-stac` is a simple rasterio plugin for creating valid STAC items from a raster dataset. The library is built on top of pystac to make sure we follow the STAC specification.

See the GitHub repo - https://developmentseed.org/rio-stac/

---

## See Also

See also [`stac-utils`](https://github.com/stac-utils) which offers a suite of tools for working with STAC.
