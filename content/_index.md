+++
title = "DGGS for FAIR2Adapt case studies"
slug = "hack4riomar"
sort_by = "weight"
+++

![](https://raw.githubusercontent.com/FAIR2Adapt/Hack4RiOMAR/refs/heads/main/static/logoFAIR2Adapt_with_earth.png)

## Welcome to the Workhathon! 🌍📊

We’re excited to have you here for the DGGS for FAIR2Adapt RiOMar Case Study workathon! Together, we’ll explore high-resolution RiOMar data, dive into DGGS-powered workflows (with xDGGS + Pangeo 🚀), and lay the groundwork for FAIR, scalable solutions supporting climate adaptation.

Let’s collaborate, innovate, and make an impact! 💡🌱


## Data challenges for the FAIR2Adapt RiOMar Case study 

This case study is led by [IFREMER](http://ifremer.fr) and builds on the outcomes of the RiOMar Project - Coastal Water Quality Anticipation to manage coastal zone ecosystem responses for biodiversity conservation. The RiOMar project’s data is high-resolution and complex to manipulate. To effectively support climate adaptation strategies and plans, it is crucial to maintain the high-resolution quality while enabling efficient data fusion with diverse datasets.

## About the Workhathon

We are excited to invite a small group of experts to a workathon focused on exploring the integration of Discrete Global Grid Systems (DGGS) into future data workflows for the FAIR2Adapt project, using high-resolution RiOMar data. This event will assess how to develop a preprocessing pipeline for publishing datasets into DGGS grids and evaluate how this approach can streamline data co-location and fusion, providing critical support for climate adaptation strategies.

This workathon aims to lay the foundation for future efforts in FAIR2Adapt by:

- **Deep Dive into DGGS**: Explore the fundamentals and advantages of DGGS for high-resolution spatial data management, with a focus on leveraging [xdggs](https://github.com/xarray-contrib/xdggs) for scalable and efficient analysis.
- **Assess RiOMar Data**: Examine the RiOMar datasets and associated metadata to evaluate their readiness for DGGS integration and explore how tools within the Pangeo ecosystem can facilitate data access and preprocessing.
- **Pipeline Development**: Design and initiate a data processing pipeline using Healpix (DGGS), xDGGS, and Zarr, aligned with FAIR principles and leveraging the Pangeo stack for scalable workflows.
- **Support Data Fusion**: Demonstrate how DGGS, combined with Pangeo’s data processing and visualization capabilities, facilitates seamless integration of RiOMar data with other datasets, advancing the development of climate adaptation strategies.

## Event Details

- Dates: 16-19 January 2025
- Location: Geilo, Norway
- By invitation only, with a maximum capacity of 7 participants. Most participants will be from the FAIR2Adapt project, with a few additional experts in DGGS invited to complement our group. Invitees will receive a detailed agenda and preparation materials.

## Advancing FAIR Workflows for Climate Adaptation
This workathon is a unique opportunity to collaborate with peers and contribute to innovative workflows that empower climate resilience. If you’ve received this invitation, we look forward to your insights and expertise.

## Hack4RiOMar summary and outcomes

*The event was attended in person by six motivated participants, who collaborated to tackle the challenges at hand and advance the FAIR2Adapt RiOMar Case Study. We would like to thank the external experts who joined the hackathon, despite not being part of the FAIR2Adapt project, and attended at their own expense.*

**Participants** (name, organisation, Github username):
- Even Moa Myklebust, Simula Research Laboratory (Norway), @evenmm 
- Tina Odaka, IFREMER (France), @tinaok
- Jean-Marc Delouis, IFREMER (France), @jmdelouis
- Justus Magin, CNRS-LOPS (France), @keewis
- Ola Formo Kihle, Independent Consultant / University of Washington Contractor, (Norway), @ofk123
- Anne Fouilloux, Simula Research Laboratory (Norway), @annefou

### short summary of the Hack4RiOMar workathon

- Successfully aggregated virtual datasets into a single dataset using virtualiZarr, using kerchunk while we still have issues with icechunk.
- Successfully transformed a sample RiOMar dataset into DGSS (Healpix) grid using different resolutions
- Tested the use and potential of multiscale Zarr for DGGS-transformed RiOMar datasets.
- Initiated the process of creating Conda environments on Datarmor, one with cubed and one with dask.
- Tried out transformation of datasets into DGGS (Healpix grid) to test the robustness of our approach:
     - Successfully regridded the Argo Kinetic Energy product from Cartesian grid to a discrete global grid system, using xdggs and xarray_healpy.
     - Completed regridding and exposed the zarr file for Gebco data, with a notebook for plotting the data.
- Created a RO-Crate for RiOMar data to determine if the minimum required metadata is already available.


We created 20 Jupyter notebooks. Some are still in progress or contain issues we have discovered (e.g., these notebooks did not run successfully). 12 notebooks have successfully run, showcasing and explaining the progress and results of each planned task.

- Github repository with all the notebooks we created: [https://github.com/FAIR2Adapt/Hack4RiOMAR/tree/main/notebooks](https://github.com/FAIR2Adapt/Hack4RiOMAR/tree/main/notebooks)
- [Check the rendered version (Jupyter Book) of the highlight Jupyter notebooks created during the hackathon](notebooks/index.html)

Check out our [Hack4RiOMar blog]() to learn more about what we did, our successes and challenges, as well as the next steps we identified!

## Organizers and Sponsors

This workathon is organised by [Simula Research Laboratory](https://www.simula.no) as part of the [FAIR2Adapt project](http://fair2adapt-eosc.eu).

The FAIR2Adapt project has received funding from the European Union’s HORIZON-INFRA-2024-EOSC-01-01 programme under grant agreement No 101188256.

