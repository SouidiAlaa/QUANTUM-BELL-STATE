from qiskit import QuantumCircuit, Aer, execute
from qiskit.visualization import circuit_drawer

# Define the quantum circuit with four qubits
qc = QuantumCircuit(4, 4)

# Apply Hadamard gates to the first two qubits
qc.h(0)
qc.h(1)

# Apply CNOT gates to create two Bell pairs
qc.cx(0, 2)
qc.cx(1, 3)

# Measure all qubits and store the results in classical bits
qc.measure([0, 1, 2, 3], [0, 1, 2, 3])

# Draw the circuit diagram
circuit_drawer(qc, output='mpl')

