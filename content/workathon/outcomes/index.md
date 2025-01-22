+++
title = "Event Highlights & Outcomes"
slug = "highlights"
sort_by = "weight"
weight = 2
+++

## Hack4RiOMar summary and outcomes

*The event was attended in person by six motivated participants, who collaborated to tackle the challenges at hand and advance the FAIR2Adapt RiOMar Case Study. We would like to thank the external experts who joined the hackathon, despite not being part of the FAIR2Adapt project, and attended at their own expense.*

### Participants

**Name, organisation, Github username**:
- **Even Moa Myklebust**, Simula Research Laboratory (Norway), @evenmm 
- **Jean-Marc Delouis**, IFREMER (France), @jmdelouis
- **Justus Magin**, CNRS-LOPS (France), @keewis
- **Ola Formo Kihle**, Independent Consultant / University of Washington Contractor, (Norway), @ofk123
- **Tina Odaka**, IFREMER (France), @tinaok
- **Anne Fouilloux**, Simula Research Laboratory (Norway), @annefou

### Short summary of the Hack4RiOMar workathon

- Successfully aggregated virtual datasets into a single dataset using virtualiZarr, using kerchunk while we still have issues with icechunk.
- Successfully transformed a sample RiOMar dataset into DGSS (Healpix) grid using different resolutions
- Tested the use and potential of multiscale Zarr for DGGS-transformed RiOMar datasets.
- Initiated the process of creating Conda environments on Datarmor, one with cubed and one with dask.
- Tried out transformation of datasets into DGGS (Healpix grid) to test the robustness of our approach:
     - Successfully regridded the Argo Kinetic Energy product from Cartesian grid to a discrete global grid system, using xdggs and xarray_healpy.
     - Completed regridding and exposed the zarr file for Gebco data, with a notebook for plotting the data.
- Created a RO-Crate for RiOMar data to determine if the minimum required metadata is already available.


### Jupyter Notebooks

We created [**20** Jupyter notebooks](https://github.com/FAIR2Adapt/Hack4RiOMAR/tree/main/notebooks). Some are still in progress or contain issues we have discovered (e.g., these notebooks did not run successfully). 

**12** notebooks have successfully run, showcasing and explaining the progress and results of each planned task. Let's dig into each planned task and review the progress:

1. **Create virtualiZarr of RiOMar Data**: The goal was to use [virtualzarr](http://virtualizarr.readthedocs.io) and [icechunk](http://icechunk.io) to create a single Virtual RiOMar dataset using VirtualiZarr, aiming to make the RiOMar data accessible from anywhere. 
   - This approach is very promising and a [Jupyter notebook](https://fair2adapt.github.io/Hack4RiOMAR/notebooks/virtualizarr_riomar_icechunk.html) was developed during the workathon. 
   - However, we did not figure out how to use icechunk on non-amazon s3 buckets (the documentation is out-of-sync with the newest alpha version which made our work very difficult). 
   - We managed to use Icechunk to write the Virtual Zarr to a local filesystem (we can then push it on any S3 bucket) but we realized that icechunk cannot yet store references to `https` (RiOMar data is currently stored on Datamor e.g. IFREMER HPC cluster and made accessible to everyone via `https`).
   - As an alternative solution, we used kerchunk with virtualzarr and write to a local kerchunk parquet and upload it afterwards to a location where averyone can access it (pangeo-eosc S3, or Datamor "portal")
2. **Create an example to demonstrate how to read RiOMar data and perform regridding to a DGGS (Healpix) grid**:
   - We first created [a small sample RiOMar dataset](https://fair2adapt.github.io/Hack4RiOMAR/notebooks/pangeo-riomar_resize_datarmor.html) to make it easier to test the transformation of RiOMar data to DGGS (Healpix)
   - Regridded [RiOMar data to DGGS (Healpix)](https://fair2adapt.github.io/Hack4RiOMAR/notebooks/pangeo-riomar.html)
   - [Visualize RiOMAR dggs-transformed data with xddgs and lonboard](https://fair2adapt.github.io/Hack4RiOMAR/notebooks/visualize-riomar.html)
3. **Regrid other types of data such as NorESM data and/or GEBCO gridded bathymetry data and/or Argo Kinetic Energy Product to DGGS (Healpix) to assess the robustness of the transformation procedure**: NorESM (Norwegian Earth System Modelling) data will be used for another FAIR2Adapt case study. The GEBCO dataset is very popular and would be very useful for the FAIR2Adapt project. Transforming Argo Kinetic Energy Product into DGGS (Healpix) would help to understand if the procedure we have developed is robust. Our goal would be to write a short *recipe* that could be part of the data publishing pipeline we will develop within the FAIR2Adapt project.
   - [Transform GEBCO Bathymetry data to DGGS](https://fair2adapt.github.io/Hack4RiOMAR/notebooks/GEBCO_HEALPIX.html) and [Visualize the DGGS GEBCO Gridded Bathymetry with xdggs](https://fair2adapt.github.io/Hack4RiOMAR/notebooks/gebco_plots.html)
   - [Transform ARGO-KE products into DGGS (Healpix)](https://fair2adapt.github.io/Hack4RiOMAR/notebooks/pangeo-argo-KE-regridding.html)
   - [Prepare the ground for the second FAIR2Adapt Case study with NorESM sample dataset](https://fair2adapt.github.io/Hack4RiOMAR/notebooks/NorESM-CS1.html) and tried to [transform NorESM data to DGGS (Healpix)](https://fair2adapt.github.io/Hack4RiOMAR/notebooks/NorESM-regridding.html). It did not work and we will need to investigate further. In addition, we believe that using bilinear interpolation will not be appropriate for this second case study (Spread of radioactive isotopes in the Arctic under different climate scenarios to understand the climate change impact on radionuclide distribution for public and environmental safety) and we will need to use conservative interpolation to ensure mass conservation during regridding.
4. **Create Conda Environment**: the goal is to be able to use the same conda environment on different platform, including on Datarmor (HPC cluster of IFREMER). The plan is to create two environments: one with Cubed and one with Dask.
5. **Apply regridding to DGGS with different resolution to test multilevel (/multiscale) zarr storage format**
   - [Multi-resolution RiOMar data](https://fair2adapt.github.io/Hack4RiOMAR/notebooks/riomar_plots-datatree_multiresoplot.html)
6. **Parallelize the transformation procedure and test it on the same datasets used in 3.**
7. **Create a RO-Crate for RiOMar Data**: Explore the metadata available within the RiOMar data (checking if they truly follow the CF-Convention) and review the preliminary metadata work conducted within the RiOMar project to assess the current state and identify what needs to be done to make the RiOMar data FAIR. 
   - [Creation of RO-Crate from a RiOMar sample dataset](https://fair2adapt.github.io/Hack4RiOMAR/notebooks/Riomar_RO.html)
   - We also tested the [new NIRD archive](https://www.sigma2.no/news/2024/enhancing-data-accessibility-our-next-generation-nird-research-data-archive) which we plan to use within the FAIR2Adapt project. We archived a sample RiOMAr dataset into the new test archive and created a Jupyter notebook to show how to create a [RO-Crate from RiOMar dataset archived on NIRD](https://fair2adapt.github.io/Hack4RiOMAR/notebooks/NIRD_riomar_RO.html). This notebook will not work for most users since we have used a test instance of the new archive where only the NIRD archive team and a few test users have access to. It was however very useful to identify which metadata is missing from the RiOMar data (for instance, a unique identifier of the data creator, clear information on the provenance).
8. **Create a STAC Item for RiOMar Dataset**


### Where to find our work

- Github repository with all the notebooks we created: [https://github.com/FAIR2Adapt/Hack4RiOMAR/tree/main/notebooks](https://github.com/FAIR2Adapt/Hack4RiOMAR/tree/main/notebooks)
- [The rendered version (Jupyter Book) of the highlight Jupyter notebooks](https://fair2adapt.github.io/Hack4RiOMAR/notebooks/index.html)
- Check out our [Hack4RiOMar blog](https://fair2adapt.github.io/Hack4RiOMAR/workathon/blog/) to learn more about what we did, our successes and challenges, as well as the next steps we identified!

