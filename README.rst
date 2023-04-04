.. image:: https://img.shields.io/badge/rtn--056-lsst.io-brightgreen.svg
   :target: https://rtn-056.lsst.io
.. image:: https://github.com/lsst/rtn-056/workflows/CI/badge.svg
   :target: https://github.com/lsst/rtn-056/actions/

########################################################################################
Study of the Photon Transfer Curve in the CCD detectors of the Vera C. Rubin Observatory
########################################################################################

RTN-056
=======

The RECA internship program allows Colombian students to get better research skills in Astronomy, Astrophysics, and Cosmology. For three months, we developed our work in this internship program, and its main objective was to study the photon transfer curves (PTC) of the Vera C. Rubin Observatory, mainly gain, and to make comparisons with the gain obtained through pairs of flats. 
    
    We used run 13144 to construct the PTCs and 13186 to analyze the crosstalk. We use \textit{DM stack}, which is the software in development for this observatory, and it makes all the reductions for the construction of the PTCs. Also, we implement simulations to reproduce the observed effects.   
    
    We initially found a 5 \% difference between the gain by PTC and pairs of flats in a range of flows between 5000 and 10000 ADU. Simulations showed that this difference was a product of the handling of the statistics and the erroneous assumption that the distribution following the Lupton equation is Gaussian. By vendor, we found an error interval for this flow region, for E2V of ($1.8 \pm 0.7$, $4.1 \pm 0.9$) \% and for ITL of ($0.85 \pm 0.7$, $2.2 \pm 0.9$) \%. Also, from the PTC we found the average Full Well Capacity of LSSTCam is $130000 \pm 10000$ e$^-$.
    
    We obtained a list of segments where we found differences with the results obtained by SLAC National Acceleration Laboratory in PTC parameters, low saturation level, or other defects. We detected and corrected the effect of statistics in the gain calculation using pairs of flats. Then, we proposed a code change for it, which was implemented in \textit{DM stack}. In addition, we do not recommend correcting for crosstalk since it does not significantly affect the parameters and does not change the shape of the PTC; the opposite is true for the nonlinearity correction.

Links
=====

- Live drafts: https://rtn-056.lsst.io
- GitHub: https://github.com/lsst/rtn-056

Build
=====

This repository includes lsst-texmf_ as a Git submodule.
Clone this repository::

    git clone --recurse-submodules https://github.com/lsst/rtn-056

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
