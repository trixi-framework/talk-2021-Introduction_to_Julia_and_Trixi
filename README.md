# Introduction to Julia and Trixi, a numerical simulation framework for hyperbolic PDEs

[![License: MIT](https://img.shields.io/badge/License-MIT-success.svg)](https://opensource.org/licenses/MIT)
<!-- [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/trixi-framework/talk-2021-julia-adaptive-multi-physics-simulations/main?filepath=getting_started_with_julia_and_trixi.ipynb) -->

This is the companion repository for the talk

**Introduction to Julia and Trixi, a numerical simulation framework for hyperbolic PDEs**</br>
*Hendrik Ranocha*</br>
TODO: Some seminar</br>
TODO: Some date and time

[(see abstract below)](#abstract).
Here you can find the presentation in form of a [Jupyter](https://jupyter.org/)
notebook [`Talk.ipynb`](Talk.ipynb). This notebook contains a couple of additional
slides not presented in the talk. There are also some additional Trixi elixirs
(simulation setups) in the [`examples`](examples) directory.

## Getting started

### Using mybinder.org
The easiest way to get started is to click on the *Launch Binder* badge above.
<!-- (or [here](https://mybinder.org/TODO)). -->
This launches the notebook for interactive use in your browser without the need
to download or install anything locally.

In this case, you can skip the rest of this *Getting started* section. A
Jupyter instance will be started automagically in the cloud via
[mybinder.org](https://mybinder.org), and the notebook will loaded directly from
this repository.

*Note:*  Depending on current usage and available resources,
it typically takes 1-2 minutes to launch a notebook with
[mybinder.org](https://mybinder.org) (sometimes a little longer), so try to
remain patient. Similarly, the first two cells of the notebook take much longer
to execute than usual (around 1.5 minutes for the first Trixi simulation and
about 1 minute for the first plot), since Julia compiles all methods
"just-ahead-of-time" at first use.  Subsequent runs will be much faster.

### Setting up a local Julia/Jupyter installation
Alternatively, you can also clone this repository and open the notebook on your
local machine. This is recommended if you already have a Julia & Jupyter setup
or if you plan to try out Julia anyways.

#### Installing Julia and IJulia
To obtain Julia, go to [julialang.org/downloads](https://julialang.org/downloads)
and download the latest stable release (v1.6.0 as of 2021-04-19;
neither use the LTS release nor Julia Pro). Then, follow the
[platform-specific instructions](https://julialang.org/downloads/platform/)
to install Julia on your machine. Note that there is no need to compile anything
if you are using Linux, MacOS, or Windows.

After the installation, open a terminal and start the Julia *REPL*
(i.e., the interactive prompt) with
```shell
julia
```
To use the notebook, you also need to get the
[IJulia](https://github.com/JuliaLang/IJulia.jl) package, which provides a Julia
backend for Jupyter. In the REPL, execute
```julia
using Pkg
Pkg.add("IJulia")
```
to install IJulia. For more details, especially on how to use an existing Jupyter installation,
please refer to the [IJulia documentation](https://julialang.github.io/IJulia.jl/stable/).
From here on, we assume that you have a working installation of Julia, Jupyter,
and the Julia kernel for Jupyter.

#### Installing the required Julia packages
To make the notebook fully reproducible, we have used Julia's package manager
to pin all packages to a fixed release. This ensures that you always have a
Julia environment in which all examples in this notebook work. Later you can
always install the latest versions of Trixi and its dependencies by following
the instructions in the Trixi
[documentation](https://trixi-framework.github.io/Trixi.jl/stable/).

If you have not done it yet, clone the repository where this notebook is stored:
```shell
git clone https://github.com/trixi-framework/talk-2021-Introduction_to_Julia_and_Trixi.git
```
Then, navigate to your repository folder and open a Jupyter notebook.
```shell
cd talk-2021-Introduction_to_Julia_and_Trixi
jupyter notebook
```
The first few cells of the [Jupyter notebook](Talk.ipynb) will enable you to
download and build all required packages, including the ODE package
[OrdinaryDiffEq](https://github.com/SciML/OrdinaryDiffEq.jl), the visualization
package [Plots](https://github.com/JuliaPlots/Plots.jl), and of course
[Trixi](https://github.com/trixi-framework/Trixi.jl).
The information Julia's package manager needs for this to work is contained
in the two files [`Project.toml`](Project.toml) and [`Manifest.toml`](Manifest.toml).

As an alternative to running the examples in the notebook directly, you may
also just view the notebook *statically* by opening it within
[Jupyter NBViewer](https://nbviewer.jupyter.org/github/trixi-framework/talk-2021-Introduction_to_Julia_and_Trixi/blob/main/Talk.ipynb?flush_cache=true).

*General note:* Make sure that you execute the examples (either in the notebook
or in the REPL) *in order*, at least for the first time. Both the notebook and
the Julia REPL maintain an internal state and and some snippets depend on
earlier statements having been executed.

#### Displaying the presentation

To display the presentation as in the talk (skipping some cells/slides that
provide further information), you need the
[Jupyter extension RISE](https://rise.readthedocs.io/en/stable),
that you can install via
```shell
pip3 install --user RISE
```
After opening the Jupyter notebook, you can enter the RISE presentation mode
with `Alt + R`.


## Abstract

TODO

<!-- Julia has been touted as a programming language especially well-suited for
numerical analysis and scientific computing. However, while its prevalence is
steadily increasing, it has not yet seen widespread adoption in the
computational science or high-performance computing communities. One of the
hurdles is a (perceived) lack of real-world examples that show how Julia can be
used to conduct numerical simulations and what its advantages and drawbacks are
for scientific applications.

To remediate this, in this talk we discuss the development of a purely
hyperbolic method for self-gravitating gas dynamics within our Julia-based open
source simulation framework
[Trixi.jl](https://github.com/trixi-framework/Trixi.jl). In this approach, we
reformulate
the elliptic gravity problem into a hyperbolic diffusion problem, which is
solved in pseudotime using the same explicit high-order discontinuous Galerkin
method we use for the flow solution. A key benefit is that in the resulting
multi-physics simulation problem, we can reuse existing hyperbolic solvers while
retaining advanced features such as non-conforming and solution-adaptive meshes.

Next to presenting numerical results, we will critically examine our experience
with building a multi-physics simulation framework with Julia. We will discuss
its strengths and weaknesses as a programming language for research software
engineering, including an assessment of how Julia's claimed benefits hold up
against scientific reality, and give a live demonstration of Julia and Trixi.jl
in action. -->

To make the shown examples reproducible by the audience, the Jupyter notebook
used for the live demonstration is available in this repository
(see [above](#getting-started)).
It can be either run from a local Julia/Jupyter installation or in the cloud via
Binder (without having to install Julia locally).

## Authors
This repository was initiated by [Hendrik Ranocha](https://ranocha.de).

## License
The contents of this repository are licensed under the MIT license
(see [LICENSE.md](LICENSE.md)).

The material in this repository is inspired by and partially derived from the talks
- [Stefan Karpinski (2019), The unreasonable effectiveness of multiple dispatch](https://www.youtube.com/watch?v=kc9HwsxE1OY)
- [Robin Deits (2020), Intro to Julia Programming Language with Detroit Tech Watch](https://www.youtube.com/watch?v=qLO-yaUkLKE)
- [Michael Schlottke-Lakemper (2021), Julia for adaptive high-order multi-physics simulations](https://github.com/trixi-framework/talk-2021-julia-adaptive-multi-physics-simulations)
