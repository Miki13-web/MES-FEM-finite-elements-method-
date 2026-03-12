# Symulator Przepływu Ciepła (MES) / Heat Transfer FEM Simulator

# About the Project

A custom-built, object-oriented C++ program implementing the Finite Element Method (FEM) to solve transient heat conduction problems. The mathematical model is based on Fourier's differential equation. The software supports both structural and unstructured (isoparametric) meshes, seamlessly handling multi-material properties and complex boundary conditions (convection, heat flux).

To demonstrate the engine's practical capabilities, it was used to run an engineering simulation of frying a zander (pikeperch) fillet on a three-layer induction pan.

# Core FEM Engine Features

<ul>
  <li><strong>Numerical Calculations:</strong> Implementation of 4-node quadrilateral finite elements and 2D Gauss-Legendre quadrature (supporting 2, 3, and 4-point integration schemes).</li>
  <li><strong>Solver Architecture:</strong> Utilizes an implicit backward Euler scheme for unconditional time stability, solving the resulting system of equations via Gaussian elimination.</li>
  <li><strong>Isoparametric Mapping:</strong> Accurate calculation of the Jacobian determinant to handle distorted element geometries (Mix Grids).</li>
  <li><strong>Multi-Material Support:</strong> Each finite element independently stores thermal parameters (density, specific heat, thermal conductivity), enabling simulation of heterogeneous systems.</li>
</ul>

## Engineering Case Study: Frying Simulation
The second phase of the project involves an advanced thermal process simulation:
<ul>
  <li><strong>Geometric Model:</strong> A "sandwich" pan bottom (1mm Steel - 4mm Aluminum - 1mm Steel) and a fish fillet. The domain was discretized into 3600 elements using a custom Python script.</li>
  
  <img width="757" height="440" alt="Zrzut ekranu 2026-03-12 110140" src="https://github.com/user-attachments/assets/a38db1bb-5546-4b1a-affd-f3107d890767" />
  <img width="714" height="492" alt="Zrzut ekranu 2026-03-12 110300" src="https://github.com/user-attachments/assets/9a4be728-28c5-4e5f-91f0-767431bbf7e0" />

  <li><strong>Dynamic Control Algorithms:</strong> Implementation of a virtual thermostat cutting off the induction heat flux at 205°C and a logical function for flipping the object.</li>
  <li><strong>Results:</strong> The simulation accurately predicted the time required to reach the target internal temperature (57°C) in approximately 418 seconds, consistent with experimental culinary data.</li>
  <img width="747" height="121" alt="Zrzut ekranu 2026-03-12 110343" src="https://github.com/user-attachments/assets/5fcaf711-c669-40bf-a6b1-13b07c55aa16" />

  <li><strong>Visualization:</strong> Results exported to .msh format for post-processing and temperature mapping in Gmsh.</li>
  <img width="512" height="523" alt="Zrzut ekranu 2026-03-12 110457" src="https://github.com/user-attachments/assets/b8aba44b-47eb-4c8a-9e40-ff4d8a332759" />
  <img width="518" height="533" alt="Zrzut ekranu 2026-03-12 110523" src="https://github.com/user-attachments/assets/66e10fbd-c26e-4279-9fe6-1a9df3b7c2ee" />
  <img width="520" height="538" alt="Zrzut ekranu 2026-03-12 110537" src="https://github.com/user-attachments/assets/e34e226a-f42b-4348-837b-254ef721d83b" />
  <img width="564" height="584" alt="Zrzut ekranu 2026-03-12 110558" src="https://github.com/user-attachments/assets/b34e528b-ddb9-46ea-881f-23c172825200" />

</ul>

## Tech Stack
<ul>
  <li><strong>Language:</strong> C++ (OOP)</li>
  <li><strong>Auxiliary Tools:</strong> Python (Mesh generation), Gmsh (Visualization)</li>
</ul>
