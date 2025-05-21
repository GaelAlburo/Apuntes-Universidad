## Sum of edges is less than k

- **`q_weights`**: Stores the edge weights of the graph (e.g., cAB,cAC,cBCcAB​,cAC​,cBC​).
    - Encoded as binary values in qubits (e.g., 2 qubits per weight for 4 possible values).
      
- **`q_edge`**: Superposition of all possible edges (paths) being tested.
    - Each qubit in `q_edge` represents whether an edge is included (1) or excluded (0) in the path.
    - For a 3-city graph (A, B, C), edges could be AB,AC,BCAB,AC,BC, so `q_edge` has 3 qubits.

**Conditional Weight Inclusion**
- `q_incl`: has all the weights that should be included
	- This is done by applying a Toffoli between the weight and the edge
	- If the corresponding `q_edge` qubit is 1, then the weight is added to the accumulator

**Quantum Arithmetic**
The next block of the circuit is a full adder that sums the included weights inside the accumulator
- The result is stored in a register called `q_path_weight`

**Comparator**
The final block of the circuit is a comparator with an X gate that determines if the path weight is less than $k$

