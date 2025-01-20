+++
title = "Event Overview"
slug = "overview"
sort_by = "weight"
weight = 1
+++

## About the Workhathon

We are excited to invite a small group of experts to a workathon focused on exploring the integration of Discrete Global Grid Systems (DGGS) into future data workflows for the FAIR2Adapt project, using high-resolution RiOMar data. This event will assess how to develop a preprocessing pipeline for publishing datasets into DGGS grids and evaluate how this approach can streamline data co-location and fusion, providing critical support for climate adaptation strategies.

This workathon aims to lay the foundation for future efforts in FAIR2Adapt by:

- **Deep Dive into DGGS**: Explore the fundamentals and advantages of DGGS for high-resolution spatial data management, with a focus on leveraging [xdggs](https://github.com/xarray-contrib/xdggs) for scalable and efficient analysis.
- **Assess RiOMar Data**: Examine the RiOMar datasets and associated metadata to evaluate their readiness for DGGS integration and explore how tools within the Pangeo ecosystem can facilitate data access and preprocessing.
- **Pipeline Development**: Design and initiate a data processing pipeline using Healpix (DGGS), xDGGS, and Zarr, aligned with FAIR principles and leveraging the Pangeo stack for scalable workflows.
- **Support Data Fusion**: Demonstrate how DGGS, combined with Pangeo’s data processing and visualization capabilities, facilitates seamless integration of RiOMar data with other datasets, advancing the development of climate adaptation strategies.

## Program 

Before the start of the Hack4RiOMAR workathon, we outlined a comprehensive list of tasks to guide participants throughout the event. These tasks were designed to address the challenges and goals of the FAIR2Adapt RiOMar Case Study and to enhance workflows, ensuring that these developments can be reused for other FAIR2Adapt Case Studies and beyond. The planned tasks included:

1. **Create virtualiZarr of RiOMar Data**: Aggregate the virtual datasets of RiOMar data into a single dataset using VirtualiZarr, aiming to make the RiOMar data accessible from anywhere.
2. **Create an example to demonstrate how to read RiOMar data and perform regridding to a DGGS (Healpix) grid** 
3. **Regrid other types of data such as Odysea and/or NorESM and/or GEBCO gridded bathymetry data and/or Argo Kinetic Energy Product to DGGS (Healpix) to assess the robustness of the transformation procedure**: transforming Odysea (Ocean DYnamics and Surface Exchange with the Atmosphere) data is particularly interesting because it originates from remote sensing with satellite tracks, making the data very sparse—a characteristic shared with many other data sources used in the FAIR2Adapt project. NorESM (Norwegian Earth System Modelling) data will be used for another FAIR2Adapt case study. The GEBCO dataset is very popular and would be very useful for the FAIR2Adapt project. Transforming Argo Kinetic Energy Product into DGGS (Healpix) would help to understand if the procedure we have developed is robust. Our goal would be to write a short *recipe* that could be part of the data publishing pipeline we will develop within the FAIR2Adapt project.
4. **Create Conda Environment**: the goal is to be able to use the same conda environment on different platform, including on Datarmor (HPC cluster of IFREMER). The plan is to create two environments: one with Cubed and one with Dask.
5. **Apply regridding to DGGS with different resolution to test multilevel (/multiscale) zarr storage format**
6. **Parallelize the transformation procedure and test it on the same datasets used in 3.**
7. **Create a RO-Crate for RiOMar Data**: Explore the metadata available within the RiOMar data (checking if they truly follow the CF-Convention) and review the preliminary metadata work conducted within the RiOMar project to assess the current state and identify what needs to be done to make the RiOMar data FAIR. 
8. **Create a STAC Item for RiOMar Dataset**


