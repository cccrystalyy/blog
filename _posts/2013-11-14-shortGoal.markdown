---
title: shortGoal
layout: post
guid: urn:uuid:6e112cce-40d8-4944-b8e8-1c27a8f331f1
tags:
  - Plans
  - MS Project
  - RCache
---
* Math part 
    * SH basis function in angular form (Done in mathematica)
        * Gradient of SH basis (Done in mathematica)
        * Hessian of SH basis (Done in mathematica)
    * SH basis function in cartesian form
        * Gradient of SH basis 
        * Hessian of SH basis 
    * Or from angular to cartesian 
        * dhdp, dhdt -->  dhdx, dhdy, dz? (Krivanek)
        * H(h)_(t,p) --> H(h)_(x, y, z?) 
    * Coef Vector 
        * Gradient  
            * Formula available 
        * Hessian 
            * Exam in mathematica
    * How to implement it?
        * libsh 
* Radiance Cache part 
    * Extrapolation& interpolation 
        * Compute Weight -> icrecord.h: better read ic book
        * Extrapolation -> project global coord to U and V 
        * Interpolation -> local coord: rotation 
    * Radius 
        * Error based?
        * Heuristic?
        * Harmonic distance computed by inverse of hit distane, then clamped by gradient (Need Verify)
    * How they compute gradient
        * Ward approach -> Stratification based(dont need to compute dhdx, dhdy) 
            * better result with occlussion 
        * Solid angle based  -> analytical result (need dhdx, dhdy)
    * Cache generation 
        * One ray per pixel 
    * Rotation 
        * libsh --> fast rotation

