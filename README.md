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
To find the #MSG (in OG setting) according to the magnetic configuration.</br>
If you find problems, please contact us. Email: rhzhang@iphy.ac.cn</br>


* how to make:

      $  tar -zxvf src_mom2msg.tar.gz
      $  cd src_mom2msg
      $  make

### 1) prepare the original POSCAR file (without magnetism).
Here we take a POSCAR $NiF_2$ as an example (space group: 136):</br>

   $     Ni F2
   $     1.0
   $             4.7100000381         0.0000000000         0.0000000000
   $             0.0000000000         4.7100000381         0.0000000000
   $             0.0000000000         0.0000000000         3.1180000305
   $        Ni    F
   $         2    4
   $     Direct
   $          0.000000000         0.000000000         0.000000000  
   $          0.500000000         0.500000000         0.500000000  
   $          0.303299993         0.303299993         0.000000000
   $          0.196700007         0.803300023         0.500000000
   $          0.803300023         0.196700007         0.500000000
   $          0.696699977         0.696699977         0.000000000



