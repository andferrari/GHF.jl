# GHF (Gaussian homogeneous spatial field)

GHJ.jl contains a julia trascription of algorithm in section 2.2:
"Generating Stationary Processes via Circulant embedding" of

> Kroese, D.P. and Botev, Z.I. (2013).
> "Spatial Process Generation."
> Lectures on Stochastic Geometry, Spatial Statistics and Random Fields,
> Volume II: Analysis, Modeling and Simulation of Complex Structures,
> V. Schmidt (Ed.).  Springer-Verlag, Berlin.
> http://arxiv.org/abs/1308.0399


## Installation

```julia
Pkg.clone("https://github.com/andferrari/GHF.jl")
```

## Usage

To compute a Gaussian homogeneous spatial field with
exponential correlation:

```julia
using PyPlot
using GHF

n = 512
m = 512
tx= linspace(0, n-1, n)
ty= linspace(0, m-1, m)

corl = n/5.0
rho(x,y) = exp(-norm([x, y])/corl)

field = genghf(tx::Vector, ty::Vector, rho::Function)

img = imshow(field)
colorbar(img)
```
