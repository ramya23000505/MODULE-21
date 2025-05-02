# EX 3B Hamiltonian Circuit Problem
## DATE: 29-03-2025
## AIM:
To write a python program to check whether Hamiltonian path exits in the given graph.

## Algorithm
1. Start the program.
2. Initialize the Path Array: Create an array path[] of size N to store the current path being explored. Set all elements in path[] to -1 initially (indicating unvisited vertices). Set path[0] = 0 to start the path at vertex 0.
3. Define the Recursive Function is_hamiltonian_path(path, pos)
4. If pos == N (i.e., we have visited all vertices), return True (Hamiltonian path found).
5. Iterate over all vertices v from 0 to N-1.
6. Call is_hamiltonian_path(path, 1) to begin the recursive search, with the second vertex (pos = 1) to be filled.
7. If is_hamiltonian_path(path, 1) returns True, print "YES" (Hamiltonian path exists).
8. If is_hamiltonian_path(path, 1) returns False, print "NO" (No Hamiltonian path exists).
9. End the program.   

## Program:
```
/*
Program to implement to check whether Hamiltonian path exits in the given graph.
Developed by: RAMYA R
Register Number:  212223230169
*/
```
```
def Hamiltonian_path(adj, N):    
    def is_hamiltonian_path(path, pos):
        if pos == N:
            return True
        for v in range(N):
            if adj[path[pos - 1]][v] == 1 and v not in path:
                path[pos] = v
                if is_hamiltonian_path(path, pos + 1):
                    return True
                path[pos] = -1
        return False
    path = [-1] * N
    path[0] = 0
    if not is_hamiltonian_path(path, 1):
        return False
    return True
    
adj = [ [ 0, 1, 1, 1, 0 ] ,
        [ 1, 0, 1, 0, 1 ],
        [ 1, 1, 0, 1, 1 ],
        [ 1, 0, 1, 0, 0 ] ]
N = len(adj)
if (Hamiltonian_path(adj, N)):
    print("YES")
else:
    print("NO")
```

## Output:

![image](https://github.com/user-attachments/assets/0751e6df-c059-4821-8816-2eaa31bb4bed)


## Result:
The Hamiltonian path program executed successfully, and it determined whether a Hamiltonian path exists in the given graph.
