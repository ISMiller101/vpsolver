**Google Code is shutting down. This project has been moved to [GitHub](https://github.com/fdabrandao/vpsolver).**

# Vector Packing Solver (VPSolver) #

VPSolver is a vector packing solver based on an arc-flow formulation with graph compression [[Poster](http://www.dcc.fc.up.pt/~fdabrandao/papers/arcflow_poster.pdf)] [[Paper](http://www.dcc.fc.up.pt/~fdabrandao/Vector_Packing_Solver)]. VPSolver generates very strong models (equivalent to Gilmore and Gomory's) that can be solved using general-purpose mixed-integer programming solvers such as Gurobi and GLPK.

**Latest release:** VPSolver v1.1, released on May 20, 2015. [[Donwload](http://vpsolver.dcc.fc.up.pt/download/)] [[GitHub](https://github.com/fdabrandao/vpsolver)] [[Online Demo](http://vpsolver.dcc.fc.up.pt/)]<br>
- This version includes a Python API and supports Gurobi, CPLEX, COIN-OR, GLPK, SCIP and lp_solve.<br>
<br>
<b>Online Demos:</b> <a href='http://vpsolver.dcc.fc.up.pt/demo/vbp'>Vector Packing</a> |  <a href='http://vpsolver.dcc.fc.up.pt/demo/mvbp'>Multiple-choice Vector Packing</a> |<br>
<a href='http://vpsolver.dcc.fc.up.pt/demo/twostage'>Two-stage Cutting Stock</a>

<br>
<br>
<h2>Overview</h2>

The p-dimensional vector packing problem, also called general assignment problem, is a generalization of bin packing with multiple constraints. In this problem, we are required to pack n items of m different types, represented by p-dimensional vectors, into as few bins as possible. In practice, this problem models, for example, static resource allocation problems where the minimum number of servers with known capacities is used to satisfy a set of services with known demands.<br>
<br>
VPSolver is a vector packing solver based on an arc-flow formulation with graph compression [<a href='http://www.dcc.fc.up.pt/~fdabrandao/papers/arcflow_report.pdf'>Arc-flow Paper</a>].<br>
By means of reductions to vector packing, VPSolver can be used to solve several problems such as:<br>
<ul><li>Bin packing<br>
</li><li>Cutting stock<br>
</li><li>Cardinality constrained bin packing<br>
</li><li>Cutting stock with cutting knife limitation<br>
</li><li>Bin packing with conflicts<br>
</li><li>Cutting stock with binary patterns [<a href='http://www.dcc.fc.up.pt/%7Efdabrandao/papers/binarycsp.pdf'>01CSP Paper</a>]<br>
</li><li>Cutting stock with binary patterns and forbidden pairs</li></ul>


[<a href='http://vpsolver.dcc.fc.up.pt/demo/vbp'>Online Demos</a>]<br>
<br>
[<a href='http://www.dcc.fc.up.pt/~fdabrandao/research/vpsolver/results/'>Computational results on several benchmark test data sets</a>]<br>
<br>
<b>VPSolver includes a python interface that allows modeling other problems easily.</b> Using the python interface, VPSolver can be used to solve problems such as:<br>
<ul><li>Multiple-choice vector bin packing (using the method proposed in [<a href='http://www.dcc.fc.up.pt/%7Efdabrandao/papers/mvbp.pdf'>MVBP Paper</a>]) [<a href='http://vpsolver.dcc.fc.up.pt/demo/mvbp'>MVBP Online Demo</a>]<br>
</li><li>Variable-sized bin packing (as an one-dimensional multiple-choice vector bin packing problem)<br>
</li><li>Two- and three-stage two-dimensional cutting stock [<a href='http://vpsolver.dcc.fc.up.pt/demo/twostage'>Two-stage CSP Online Demo</a>]<br>
</li><li>Note: <b>Suggestions of other cutting & packing problems (including industrial applications) are welcome!</b> [<a href='http://www.dcc.fc.up.pt/~fdabrandao/'>Contact</a>]</li></ul>

<h2>Requirements</h2>
<ul><li>Compiler: g++ >= 4.6<br>
</li><li>Python 2.7 for the python interface (optional)<br>
</li><li>MIP solver: Gurobi, CPLEX, GLPK, COIN-OR, SCIP, lp_solve, ... <br>
<ul><li>VPSolver does not explicitly require any MIP solver in particular, though a good MIP solver may be necessary for solving large models.<br>
</li></ul></li><li>It has been successfully compiled and run on the following platforms:<br>
<ul><li>Linux<br>
</li><li>Mac OS X<br>
</li><li>(It may also work on Windows using Cygwin)</li></ul></li></ul>

<h2>Solution method</h2>

Brandão, F. and Pedroso, J. P. (2013). <b>Bin Packing and Related Problems: General Arc-flow Formulation with Graph Compression.</b> Technical Report DCC-2013-08, Faculdade de Ciências da Universidade do Porto, Portugal. Available at <a href='http://arxiv.org/abs/1310.6887'>http://arxiv.org/abs/1310.6887</a>.<br>
<br>
Abstract:<br>
<br>
<blockquote>We present an exact method, based on an arc-flow formulation with side constraints, for solving bin packing and cutting stock problems --- including multi-constraint variants --- by simply representing all the patterns in a very compact graph. Our method includes a graph compression algorithm that usually reduces the size of the underlying graph substantially without weakening the model. As opposed to our method, which provides strong models, conventional models are usually highly symmetric and provide very weak lower bounds.</blockquote>

<blockquote>Our formulation is equivalent to Gilmore and Gomory's, thus providing a very strong linear relaxation. However, instead of using column-generation in an iterative process, the method constructs a graph, where paths from the source to the target node represent every valid packing pattern.</blockquote>

<blockquote>The same method, without any problem-specific parameterization, was used to solve a large variety of instances from several different cutting and packing problems. In this paper, we deal with vector packing, graph coloring, bin packing, cutting stock, cardinality constrained bin packing, cutting stock with cutting knife limitation, cutting stock with binary patterns, bin packing with conflicts, and cutting stock with binary patterns and forbidden pairs. We report computational results obtained with many benchmark test data sets, all of them showing a large advantage of this formulation with respect to the traditional ones.</blockquote>

<blockquote><img src='http://www.dcc.fc.up.pt/~fdabrandao/research/vpsolver/graph.png' /></blockquote>

<blockquote>[<a href='http://www.dcc.fc.up.pt/~fdabrandao/papers/arcflow_poster.pdf'>Poster</a>] [<a href='http://www.dcc.fc.up.pt/~fdabrandao/papers/arcflow_report.pdf'>Paper</a>] [<a href='http://www.dcc.fc.up.pt/~fdabrandao/research/vpsolver/results/'>Computational Results</a>]</blockquote>

References:<br>
<ul><li>Brandão, F. and Pedroso, J. P. (2013). Bin Packing and Related Problems: General Arc-flow Formulation with Graph Compression.<br> Technical Report DCC-2013-08, Faculdade de Ciências da Universidade do Porto, Portugal. [<a href='http://www.dcc.fc.up.pt/~fdabrandao/papers/arcflow_report.pdf'>PDF</a>]</li></ul>

<ul><li>Brandão, F. and Pedroso, J. P. (2013). Multiple-choice Vector Bin Packing: Arc-flow Formulation with Graph Compression.<br> Technical Report DCC-2013-13, Faculdade de Ciências da Universidade do Porto, Universidade do Porto, Portugal. [<a href='http://www.dcc.fc.up.pt/~fdabrandao/papers/mvbp.pdf'>PDF</a>]</li></ul>

<ul><li>Brandão, F. and Pedroso, J. P. (2013). Cutting Stock with Binary Patterns: Arc-flow Formulation with Graph Compression.<br> Technical Report DCC-2013-09, Faculdade de Ciências da Universidade do Porto, Universidade do Porto, Portugal. [<a href='http://www.dcc.fc.up.pt/~fdabrandao/papers/binarycsp.pdf'>PDF</a>]</li></ul>

<ul><li>Brandão, F. (2012). Bin Packing and Related Problems: Pattern-Based Approaches.<br> Master’s thesis, Faculdade de Ciências da Universidade do Porto, Portugal. [<a href='http://www.dcc.fc.up.pt/~fdabrandao/papers/MThesisBrandao.pdf'>PDF</a>]</li></ul>

<h2>Usage</h2>

Solve a vector packing instance using Gurobi:<br>
<pre><code>  bin/vpsolver example.vbp<br>
</code></pre>

Solve a vector packing instance using Gurobi (step-by-step):<br>
<pre><code>  bin/vbp2afg example.vbp graph.afg   # 1. builds the arc-flow graph (graph.afg)<br>
  bin/afg2mps graph.afg model.mps     # 2. converts the arc-flow graph into a .mps file (model.mps)<br>
  bin/solve_gurobi model.mps vars.sol # 3. solves the MIP model and stores the solution in vars.sol<br>
  bin/vbpsol graph.afg vars.sol       # 4. outputs the vector packing solution<br>
</code></pre>

Solve a vector packing instance using GLPK (step-by-step):<br>
<pre><code>  bin/vbp2afg example.vbp graph.afg   # 1. builds the arc-flow graph (graph.afg)<br>
  bin/afg2lp graph.afg model.lp       # 2. converts the arc-flow graph into a .lp file (model.lp)    <br>
  bin/solve_glpk model.lp vars.sol    # 3. solves the MIP model and stores the solution in vars.sol<br>
  bin/vbpsol graph.afg vars.sol       # 4. outputs the vector packing solution<br>
</code></pre>

VPSolver includes several scripts for solving vector packing<br>
instances using different solvers (vpsolver_coinor.sh, vpsolver_cplex.sh, vpsolver_glpk.sh, vpsolver_gurobi.sh, vpsolver_lpsolve.sh, vpsolver_scip.sh).<br>
Solve a vector packing instance using COIN-OR:<br>
<pre><code>  scripts/vpsolver_coinor.sh --vbp instance.vbp<br>
</code></pre>

For more details, please refer to the manual.<br>
<br>
<br>
Copyright © Filipe Brandão. All rights reserved. [<a href='http://www.dcc.fc.up.pt/~fdabrandao/'>Contact</a>]