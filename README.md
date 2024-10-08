
## Introduction

WQChartPy is an an open-source Python package for producing most of the graphical diagrams for visualization of water geochemistry data. Utilizing the commonly used file formats such as Microsoft Excel, comma-separated values (CSV), and general delimited Text as the input data format, WQChartPy can produce twelve geochemical diagrams including not only the traditional Piper trilinear, Durov, Chadha, Stiff, Chernoff face, Schoeller, Gibbs, and Gaillardet diagram, but also the recently proposed diagrams such as the rectangle Piper, color-coded Piper, contour-filled Piper, and HFE-D diagrams that have not been implemented in previous software. 

This is the first release of WQChartPy. As a Python-based cross platform program, WQChartPy works on Windows, MacOS X and GNU/Linux. We provided a self-contained Jupyter notebook file to illustrate how to use WQChartPy. Users with a little Python experience can do the whole process from data to the graphical diagrams. Buidling on the oldest and most popular Python plotting library Matplotlib, the figures generated by WQChartPy can be saved as portable network graphics (PNG), scalable vector graphics (SVG) or portable document format (PDF). WQChartPy is an open-source project and any assistance is welcomed. Please email the development team if you want to contribute.

The repository contains:

```bash
+-- data                                         
¦ +-- data_template.csv                      # Example water geochemsitry dataset taken from Ray et al. 2014 in CSV foramt 
¦ +-- data_template.xlsx                     # Example water geochemsitry dataset taken from Ray et al. 2014 in MS Excel foramt 
¦ +-- data_template.txt                      # Example water geochemsitry dataset taken from Ray et al. 2014 in Tab delimited Text format
¦ +-- data_Liu_et_al_2021.csv                # Example water geochemsitry dataset taken from Liu et al. 2021 in CSV format
¦ +-- data_Yang_et_al_2021.csv               # Example water geochemsitry dataset taken from Yang et al. 2020 in CSV format
¦ +-- data_Moreno_Merino_et_al_2021.csv      # Example water geochemsitry dataset taken from Moreno Merino et al. 2021 in CSV format
+-- examples         
¦ +-- example_data_template.ipynb            # Jupyter notebook to illustrate how to use WQChartPy by using dataset taken from Ray et al. 2014
¦ +-- example_Liu_et_al_2021.ipynb           # Jupyter notebook  illustrate how to use WQChartPy by using dataset taken from Liu et al. 2021
¦ +-- example_Moreno_Merino_et_al_2021.ipynb # Jupyter notebook  to illustrate how to use WQChartPy by using dataset taken from Moreno Merino et al. 2021
¦ +-- example_Yang_et_al_2020.ipynb          # Jupyter notebook  to illustrate how to use WQChartPy by using dataset taken from Yang et al. 2020
+-- papers
¦ +-- Chadha-1999-A proposed ...             # Reference for Chadha diagram    
¦ +-- ...                                    # ... 
¦ +-- Ray-2008-Reproducing the ...           # Reference for rectangle Piper diagram    
+-- wqchartpy
¦ +-- BivariateColourScheme.npy              # NumPy ndarray object used to for the background color scheme
¦ +-- __init__.py                            # Common script used in the regular package  
¦ +-- chadha.py                              # Code for generating the Chadha diagram
¦ +-- chernoff.py                            # Code for generating Chernoff faces
¦ +-- color_piper.py                         # Code for generating color-coded Piper diagram
¦ +-- contour_piper.py                       # Code for generating contour-filled Piper diagram
¦ +-- durov.py                               # Code for generating Durov diagram
¦ +-- durov_mod.py                           # Code for generating Durov diagram with modifications
¦ +-- gaillardet.py                          # Code for generating Gaillardet diagram
¦ +-- gaillardet_mod.py                      # Code for generating Gaillardet diagram with modifications
¦ +-- gibbs.py                               # Code for generating Gibbs diagram
¦ +-- gibbs_mod.py                           # Code for generating Gibbs diagram with modifications
¦ +-- hfed.py                                # Code for generating HFE-D diagram
¦ +-- hfed_mod.py                            # Code for generating HFE-D diagram with modifications
¦ +-- ions.py                                # Code for defining the ion weights and charges
¦ +-- rectangle_piper.py                     # Code for generating rectangle diagram
¦ +-- schoeller.py                           # Code for generating Schoeller diagram
¦ +-- schoeller_mod.py                       # Code for generating Schoeller diagram with modifications
¦ +-- stiff.py                               # Code for generating Stiff diagram
¦ +-- stiff_mod.py                           # Code for generating Stiff diagram with modifications
¦ +-- triangle_piper.py                      # Code for generating triangle Piper diagram
¦ +-- triangle_piper_mod.py                  # Code for generating triangle Piper diagram with modifications
+-- LICENCE                                  # Licence file
+-- MANIFEST.in                              # Adding BivariateColourScheme.npy to the source distribution 
+-- README.md                                # Readme file
+-- setup.py                                 # Centre script for installing this package
```

## Installation

WQChartPy requires **Python** 3.7 (or higher). We recommend using [Anaconda](https://www.anaconda.com/) on Windows or Linux platforms. 

The easiest way to install is via `pip`:

To install WQChartPy type:

    pip install wqchartpy

To update WQChartPy type:

    pip install wqchartpy --upgrade

To uninstall WQChartPy type:

    pip uninstall wqchartpy
    
Another way is to manually install WQChartPy with `setup.py`. Preliminary steps to take:

    1. Download the package and extract it into a local directory

    2. cd into the root directory where setup.py is located using an Anaconda Prompt

    3. Enter: python setup.py install
    
## Requirements:

- [NumPy](https://www.numpy.org)
- [Pandas](https://pandas.pydata.org/)
- [Matplotlib](https://www.scipy.org/scipylib)
- [SciPy](https://salib.readthedocs.io/en/latest/)
- [Scikit-learn](https://scikit-learn.org/stable/index.html)
    
## How to use

We recommend to start by executing the [workflow](https://github.com/jyangfsu/WQChartPy/blob/main/examples/example1.ipynb) provided in the examples folder. 

| Diagram | Basic usage
---------|------------
Triangle Piper| from wqchartpy import triangle_piper; triangle_piper.plot(df, unit, figname, figformat)
Triangle Piper Mod| from wqchartpy import triangle_piper_mod; triangle_piper_mod.plot(df, unit, figname, figformat)
Rectangle Piper| from wqchartpy import rectangle_piper; rectangle_piper.plot(df, unit, figname, figformat)
Color-coded Piper| from wqchartpy import color_piper; color_piper.plot(df, unit, figname, figformat)
Contour-filled Piper| from wqchartpy import contour_piper; contour_piper.plot(df, unit, figname, figformat)
Durov| from wqchartpy import durov; durov.plot(df, unit, figname, figformat)
Durov Mod| from wqchartpy import durov mod; durov_mod.plot(df, unit, figname, figformat)
Stiff| from wqchartpy import stiff; stiff.plot(df, unit, figname, figformat)
Stiff Mod| from wqchartpy import stiff_mod; stiff_mod.plot(df, unit, figname, figformat)
Chernoff face| from wqchartpy import chernoff; chernoff.plot(df, unit, figname, figformat)
Schoeller| from wqchartpy import schoeller; schoeller.plot(df, unit, figname, figformat)
Schoeller Mod| from wqchartpy import schoeller_mod; schoeller_mod.plot(df, unit, figname, figformat)
Gibbs| from wqchartpy import gibbs; gibbs.plot(df, unit, figname, figformat)
Gibbs Mod| from wqchartpy import gibbs_mod; gibbs_mod.plot(df, unit, figname, figformat)
Chadha| from wqchartpy import chadha; chadha.plot(df, unit, figname, figformat)
Gaillardet| from wqchartpy import gaillardet; gaillardet.plot(df, unit, figname, figformat)
Gaillardet Mod| from wqchartpy import gaillardet_mod; gaillardet_mod.plot(df, unit, figname, figformat)
HFE-D| from wqchartpy import hfed; hfed.plot(df, unit, figname, figformat)
HFE-D Mod| from wqchartpy import hfed_mod; hfed_mod.plot(df, unit, figname, figformat)

### Triangle Piper Modification with Hydrogeochemical Facies Interpretation

<img src="mod_images/triangle Piper diagram mod.jpg" width="600"/>

### Triangle Piper 

<img src="http://m.qpic.cn/psc?/V5428EvQ2PMkSA3NWIHm4Ak3hg45PLib/TmEUgtj9EK6.7V8ajmQrECmTiF9WFCBK*FqbaC1Gc9x8p0qnA.IgiMoIYsqJbpqLbhokrRynpBx.b4LtRhNGuzcMrO4vXEwgLmeRZte6ItI!/b&bo=yQQ4BAAAAAABF8E!&rf=viewer_4" width="600"/>

### Triangle Piper with color varying across TDS values

<img src="http://m.qpic.cn/psc?/V5428EvQ2PMkSA3NWIHm4Ak3hg45PLib/TmEUgtj9EK6.7V8ajmQrEBru*QgAOH7Q*HFhoW*r.ZSdVPFpNMgWY06mi6kr023QxWX1LysoKTNSjvZsYZQFGB4BAkAqV*ER4H97ojaeg24!/b&bo=ZAU4BAAAAAABF20!&rf=viewer_4" width="600"/>

### Rectangle Piper

<img src="http://m.qpic.cn/psc?/V5428EvQ2PMkSA3NWIHm4Ak3hg45PLib/TmEUgtj9EK6.7V8ajmQrED65VNtqduHH9ZXaYXUt2kXuTCyMjLOJtYlPYWgJsJCcDaRJawc70iUGAuHxzIbF92HzirvHzdOOgGhXYIgYRGM!/b&bo=TA04BAAAAAABF00!&rf=viewer_4" width="600"/>

### Color-coded Piper

<img src="http://m.qpic.cn/psc?/V5428EvQ2PMkSA3NWIHm4Ak3hg45PLib/TmEUgtj9EK6.7V8ajmQrEH5ZUa7NHBJfUicR19oK1LdR.4BlQkIGQK5ZStLnkw0hw2dZ3HZ0RMTh6MUXtCT8lS9iKyNVp*yqKMdenah5Gyw!/b&bo=kQQ4BAAAAAABF5k!&rf=viewer_4" width="600"/>

### Contour-filled Piper

<img src="http://m.qpic.cn/psc?/V5428EvQ2PMkSA3NWIHm4Ak3hg45PLib/TmEUgtj9EK6.7V8ajmQrELaJZx2xDjJTZR7e5mjwQ7hVXxTfCTamHwVQU09sclARJPwdmwMWxWwhlVnwZqUne89Ni3WCFfFZPYh*CXc15tE!/b&bo=kgIVAgAAAAABF7c!&rf=viewer_4" width="600"/>

### Durov

<img src="http://m.qpic.cn/psc?/V5428EvQ2PMkSA3NWIHm4Ak3hg45PLib/TmEUgtj9EK6.7V8ajmQrEEELoir7Oh4SDzBYQWBXJICvbD3nwobK7w.AAFx2guuOu1H7LyyMwkYlEcEm8DlajY4MLCz1N2LBOjkMUqmtYNo!/b&bo=3AU4BAAAAAABF9U!&rf=viewer_4" width="600"/>

### Durov Modification

<img src="mod_images/Durov Diagram mod.jpg" width="600"/>

### Stiff

<img src="http://m.qpic.cn/psc?/V5428EvQ2PMkSA3NWIHm4Ak3hg45PLib/TmEUgtj9EK6.7V8ajmQrEJ0QBoQ3kzaRJmIjLTV2iGzJ1f88h7s7cZxWBVMD45bHVTWxXGhucZBhj7Ug7nTwNJTm53CIaNHFVO4HUOmHL6w!/b&bo=ZgTAAwAAAAABF5E!&rf=viewer_4" width="600"/>

### Stiff Modification Inidividual

<img src="mod_images/Stiff Diagram mod_sample6.jpg" width="600"/>

### Stiff Modification Combined

<img src="mod_images/Stiff Diagram mod_combined.jpg" width="600"/>

### Chernoff face

<img src="http://m.qpic.cn/psc?/V5428EvQ2PMkSA3NWIHm4Ak3hg45PLib/TmEUgtj9EK6.7V8ajmQrEFDP5srN0pcH1HRqLbjEYEZth.Y7CLr4mjgaSENZ6s.*nG8K3r233ZpOdBXiY9Cye0aAHvCRUEaFELfRKU2ixdk!/b&bo=2QVFAwAAAAABF6o!&rf=viewer_4" width="400"/>

### Schoeller

<img src="http://m.qpic.cn/psc?/V5428EvQ2PMkSA3NWIHm4Ak3hg45PLib/TmEUgtj9EK6.7V8ajmQrEJxgqA6zKacIyWVqI1dsvgm0t8el8yLIIyKkatCvtLXFm03BnWImNlfZ9EyRr*wtXQ4Iasm4SWyJupSE5YcHhaw!/b&bo=qQZRAwAAAAABF80!&rf=viewer_4" width="600"/>

### Schoeller Modification

<img src="mod_images/Schoeller Diagram mod.jpg" width="600"/>

### Gibbs

<img src="http://m.qpic.cn/psc?/V5428EvQ2PMkSA3NWIHm4Ak3hg45PLib/TmEUgtj9EK6.7V8ajmQrEEYIDsjXF2BR6qd0W.btr15at96MQhDvyw9uAAjsrtmZuZqOR3YtXE8KWjo55kp3zQ509JwGt1MUDib4fCnbvr4!/b&bo=JgY4BAAAAAABFyw!&rf=viewer_4" width="600"/>

### Gibbs Modification

<img src="mod_images/Gibbs Diagram mod.jpg" width="600"/>

### Chadha

<img src="http://m.qpic.cn/psc?/V5428EvQ2PMkSA3NWIHm4Ak3hg45PLib/TmEUgtj9EK6.7V8ajmQrEENdiG8P6729iw*UOcN1GpRnV0Yw2rOpgVpIwSeLkRxoIz18rWQigF.fqvwaERJlm55j.8vNKDPNptg3elsBLAE!/b&bo=PgQ4BAAAAAABFzY!&rf=viewer_4" width="400"/>

### Gaillardet

<img src="original_images/Gaillardet Diagram.jpg" width="600"/>

### Gaillardet Modification

<img src="mod_images/Gaillardet Diagram mod.jpg" width="600"/>

### HFE-D

<img src="http://m.qpic.cn/psc?/V5428EvQ2PMkSA3NWIHm4Ak3hg45PLib/TmEUgtj9EK6.7V8ajmQrENfr7msUfIWvp3kVfM8MrjAN69HYZrIFaJ7sEWMk1ikSlnro6GZmXw1k2u..tuy8WVBrAvfoMM9cjmh4.rjMSUI!/b&bo=qAU4BAAAAAABF6E!&rf=viewer_4" width="600"/>

### HFE-D Modification

<img src="mod_images/HFE-D Diagram mod.jpg" width="600"/>

## How to cite

Yang, J., Liu, H., Tang, Z., Peeters, L. and Ye, M. (2022), Visualization of Aqueous Geochemical Data Using Python and WQChartPy. Groundwater. https://doi.org/10.1111/gwat.13185

## License

WQChartPy is distributed under the GNU General Public License v3.0. See the [LICENSE](https://github.com/jyangfsu/WQChartPy/LICENSE) file for details.

## Contributing to WQChartPy

Users are welcome to submit bug reports, feature requests, and code contributions to this project through GitHub or mail to us at jingyang@cug.edu.cn.
