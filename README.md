# STATEMENT
This code is aimed at approximately solving an important problem of network
science, namely to divide a network into small components by deleting vertices
in a most economic way.

The author (Hai-Jun Zhou) of this code is against any form of terrorism. This
code should only be used for pure academic purposes and for practical purposes
that improve the welfare of humanity. The author strongly condemn any intention
of adapting this code for destructive purposes.

# DESCRIPTION
Belief propagation guided decimation (BPD) as a solver for the network targeted
attack problem. The goal is to construct a minum set S such that, if all the
vertices in this set and all the attached edges are deleted from the graph,
the remaining subgraph will be formed by disconnected components of size not
exceeding a given value Sthreshold.

This program is applicable on a single graph instance. The imput graph file has
the following form:

N   M                % first row specifies N (vertex number) and M (edge number)

i_1  j_1                                            % undirected edge (i_1, j_1)
i_2  j_2                                            % undirected edge (i_2, j_2)
.    .
.    .
.    .
i_M  j_M                                            % undirected edge (i_M, j_M)

The program reads only the first EdgeNumber edges from the imput graph, with
EdgeNumber being explicitly specified (EdgeNumber <= M, of course).

Each vertex has two states (unoccupied, 0; occupied, 1). An unoccupied vertex
belongs to the constructed target set S, while an occupied vertex remains in the
network.

The target set S is contructed by three steps:
1) a feedback vertex set S0 is constructed by BPD, all the vertices in S0 are
deleted from the input graph G.
2) if a tree component of the remaining subgraph contains more than Sthreshold
vertices, one of its vertices is deleted.
3) some deleted vertices are added back to the remaining network as long as
the netowrk component sizes do not exceed Sthreshold.

# REFERENCES
For more details about the algorithm and the replica-symmetric mean field
theory and the spin glass model on which this algorithm was based, please
consult the following references:
[1] Salomon Mugisha, Hai-Jun Zhou, "Identifying optimal targets of network
attack by belief propagation", arXiv:1603.05781 (2016).
[2] Hai-Jun Zhou, "Spin glass approach to the feedback vertex set problem",
European Physical Journal B 86: 455 (2013).
[3] Hai-Jun Zhou, "Spin Glasses and Message Passing" (Science Press, Beijing,
2015), chapter 7, pages 218--238.

# COMPILE
To generate the executive file, you can simply compile as

`c++ -O3 -o tabpd.exe TAbyFVSbpdV03.cpp`

!!! please make sure some of the key parameters, such as input graph name,
number of edges, number of vertices, output file names, are appropriately
specified in the TAbyFVSbpdV03.cpp file.

# USE
After you successfully compiled the code, you can then run the algorithm as

`tabpd.exe`

or one can use the shell script **run.sh** to combine the compiling and running the executable program.

Good luck!

# LOG
28.03.2016: TAbyFVSbpdV03.cpp (publicly accessible version).
28.03.2016: copied TAbyFVSbpdV02.cpp to TAbyFVSbpdV03.cpp.

# PROGRAMMER
- Hai-Jun Zhou
- Institute of Theoretical Physics, Chinese Academy of Sciences
- Zhong-Guan-Cun East Road 55, Beijing 100190
- email: zhouhj@itp.ac.cn
- web:http://home.itp.ac.cn/~zhouhj/
