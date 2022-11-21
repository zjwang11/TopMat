# TQC and TopMat in 1651 MSGs
The complete theory of topological quantum chemistry (TQC) in all 1651 magnetic space groups (MSGs).</br>
The series of codes for searching for topological materials (TopMat) in 1651 MSGs.

* Ref: J. Gao, et al. "Magnetic band representations, Fu-Kane-like symmetry indicators, and magnetic topological materials", Phys. Rev. B 106, 035150 (2022). https://doi.org/10.1103/PhysRevB.106.035150  <br>

## A generate workflow for topologicl materials in 1651 magnetic space groups (MSGs) online http://tm.iphy.ac.cn/TopMat_1651msg.html
### 1) prepare the original POSCAR file (without magnetism).

### 2) phonopy --symmetry --tolerance 0.01 -c POSCAR

### 3) pos2msg (converting PPOSCAR to POSCAR_msg and initializing MAGMOM on magnetic atoms)
 
### 4) cp POSCAR_msg POSCAR; do spin-polarized VASP calculations with the given "MAGMOM" setting.

### 5) irvsp -sg sg#B [ -nb $m $n ] > outir (generating tqc.txt/tqc.data when using only maximal HSKPs)

### 6) solve compatibility relations (CR) and calculate symmetry indicators (SI) in 1651 magnetic space groups (using tqc.data).

# mom2msg (The additional tool to generate POSCAR_msg)
to converting PPOSCAR to POSCAR_msg and initializing MAGMOM on magnetic atoms.</br>

* how to make:

      $  tar -zxvf src_mom2msg.tar.gz
      $  cd src_mom2msg
      $  make

* how to use:

      $ src_mom2msg/mom2msg > msgout

* If you find problems, please contact us. Email: rhzhang@iphy.ac.cn
