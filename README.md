# BIOMD0000000174: Model_1

## Installation

Download this repository, and install with distutils

`python setup.py install`

Or, install using pip

`pip install git+https://github.com/biomodels/BIOMD0000000174.git`

To install a specific version (in this example, from the 2014-09-16 BioModels release)

`pip install git+https://github.com/biomodels/BIOMD0000000174.git@20140916`

## Usage

Importing the model package.

`import BIOMD0000000174 as model`

Get the SBML string from the model

`print model.sbmlString`

If [python-libsbml](https://pypi.python.org/pypi/python-libsbml) bindings are
installed, the libsbml.SBMLDocument object is also accessible

`model.sbml`


# Model Notes


**Membrane identity and GTPase cascades regulated by toggle and cut-out switches**   
Perla Del Conte-Zerial, Lutz Brusch, Jochen C Rink, Claudio Collinet, Yannis
Kalaidzidis, Marino Zerial, and Andreas Deutsch: _Molecular Systems
Biology_4:206 _15 July 2008_, [ doi:10.1038/msb.2008.45
](http://dx.doi.org/10.1038/msb.2008.45)

This is the cut-out switch model for the Rab5 - Rab7 transition, also referred
to as model 2 in the original publication.  
This model is not completely described in all details in the publication.
Thanks go to Barbara Szomolay and Lutz Brusch for finding and clarifying this.
According to Dr. Brusch this model represents the mechanism identified by the
qualitative analysis in the article in the scenario deemed most useful by the
authors. For the time-course simulations it was necessary to add a time
dependency to one of the parameters, which is only verbally described in the
article.  
As argued in the publication the switch between early and late endosomes can
be triggered by a parameter change. While with fixed parameter values each
switch just converges to one steady state from its initial conditions and
stays there, endosomes should switch between two different states. These
changes would in reality of course depend on many different factors, such as
cargo composition and amount in the specific endosome, its location and some
additional cellular control mechanisms and encompass many different
parameters. To keep the model simple the authors chose to add a time
dependency to only one reaction - **ke** in the activation of RAB5 is
multiplied with a term monotonously increasing over time from 0 to 1. They
also hard coded a time dependence in this term, 100 minutes, to make the
switch occur after several hundred minutes. As long as this modulating term
remains monotonic all resulting time courses should look similar, with the
switching behavior depending on the initial conditions and whether the term is
increasing or decreasing. Monotonic increase is a reasonable assumption for
the described mechanism of cargo accumulation.  
Not explicitly described in the article: _activation of Rab5 (time)_ :
_r*ke***time/(100+time)** /(1+e(kg-R)*kf)_ instead of _r*ke/(1+e(kg-R)*kf)_

This model originates from BioModels Database: A Database of Annotated
Published Models. It is copyright (c) 2005-2009 The BioModels Team.  
For more information see the [terms of
use](http://www.ebi.ac.uk/biomodels/legal.html).  
To cite BioModels Database, please use [Le Novère N., Bornstein B., Broicher
A., Courtot M., Donizelli M., Dharuri H., Li L., Sauro H., Schilstra M.,
Shapiro B., Snoep J.L., Hucka M. (2006) BioModels Database: A Free,
Centralized Database of Curated, Published, Quantitative Kinetic Models of
Biochemical and Cellular Systems Nucleic Acids Res., 34: D689-D691.](http://ww
w.pubmedcentral.nih.gov/articlerender.fcgi?tool=pubmed&pubmedid=16381960)


