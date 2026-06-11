.. image:: https://img.shields.io/badge/sotn--005-lsst.io-brightgreen.svg
   :target: https://sotn-005.lsst.io
.. image:: https://github.com/lsst-so/sotn-005/workflows/CI/badge.svg
   :target: https://github.com/lsst-so/sotn-005/actions/

############################################################################
Thermal Predictors of Open-Loop Focus Drift at the Vera C. Rubin Observatory
############################################################################

SOTN-005
========

The Vera C. Rubin Observatory’s Active Optics System corrects slowly varying, thermally induced defocus through closed-loop active control and, ultimately, an open-loop look-up table calibrated against bulk temperature. However, rapid residual focus drifts, quantified by the Zernike coefficient $Z_4$, are observed after LUT correction on timescales of $\sim 30$ minutes. These drifts are suspected to arise from rapidly evolving thermo-optical coupling, motivating a systematic characterization of residual thermal effects on focus stability. We analyze 23 open-loop stability image sequences from November and December 2025, each consisting of 40 exposures acquired over $\sim$28 minutes with the hexapod held fixed. Temperature data from 13 sensors spanning the enclosure air, telescope structure, mirror glass, and hexapod assemblies are queried and mean-centered to isolate thermal dynamics from bulk nightly cooling. We compute Pearson correlations between $Z_4$ and individual sensors, physically motivated pairwise temperature gradient proxies, and PCA-derived thermal modes, repeating all analyses at the slope timescale. Individual sensor and temperature gradient proxy correlations are weak (max $r \simeq 0.3$) and no sensor maintains a stable multivariate coefficient across runs. Top sensor thermal correlations are stronger in runs classified as smooth, consistent with a thermal signal that is present but frequently obscured by measurement noise and other dynamical effects. Correlations among the $Z_4$ measurements themselves further complicate the interpretation, indicating that apparent sensor relationships may partly reflect shared temporal structure rather than direct causal coupling. These results suggest that thermal-optical coupling at the Rubin Observatory is distributed across multiple mechanisms and timescales and cannot be captured by simple linear relationships with individual temperature sensors. Future work will require additional temperature sensing, a larger sample of open-loop runs, and nonlinear or multivariate dynamical models to separate true thermal drivers from correlated focus variability.

Links
=====

- Live drafts: https://sotn-005.lsst.io
- GitHub: https://github.com/lsst-so/sotn-005

Build
=====

This repository includes lsst-texmf_ as a Git submodule.
Clone this repository::

    git clone --recurse-submodules https://github.com/lsst-so/sotn-005

Compile the PDF::

    make

Clean built files::

    make clean

Updating acronyms
-----------------

A table of the technote's acronyms and their definitions are maintained in the ``acronyms.tex`` file, which is committed as part of this repository.
To update the acronyms table in ``acronyms.tex``::

    make acronyms.tex

*Note: this command requires that this repository was cloned as a submodule.*

The acronyms discovery code scans the LaTeX source for probable acronyms.
You can ensure that certain strings aren't treated as acronyms by adding them to the `skipacronyms.txt <./skipacronyms.txt>`_ file.

The lsst-texmf_ repository centrally maintains definitions for LSST acronyms.
You can also add new acronym definitions, or override the definitions of acronyms, by editing the `myacronyms.txt <./myacronyms.txt>`_ file.

Updating lsst-texmf
-------------------

`lsst-texmf`_ includes BibTeX files, the ``lsstdoc`` class file, and acronym definitions, among other essential tooling for LSST's LaTeX documentation projects.
To update to a newer version of `lsst-texmf`_, you can update the submodule in this repository::

   git submodule update --init --recursive

Commit, then push, the updated submodule.

.. _lsst-texmf: https://github.com/lsst/lsst-texmf
