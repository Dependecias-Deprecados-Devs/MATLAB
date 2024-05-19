A sparse matrix is a large matrix with almost all elements of the same value (typically zero). The normal representation of a sparse matrix takes up lots of memory when the useful information can be captured with much less. A possible way to represent a sparse matrix is with a cell vector whose first element is a 2-element vector representing the size of the sparse matrix. The second element is a scalar specifying the default value of the sparse matrix. Each successive element of the cell vector is a 3-element vector representing one element of the sparse matrix that has a value other than the default. The three elements are the row index, the column index and the actual value. Write a function called sparse2matrix that takes a single input of a cell vector as defined above and returns the output argument called matrix, the matrix in its traditional form. Consider the following run:
```
cellvec = {[2 3], 0, [1 2 3], [2 2 -3]};
matrix = sparse2matrix(cellvec)

matrix =

     0     3     0
     0    -3     0
```

### Función
```
function matrix = sparse2matrix(cellvec)
    % Extract the size of the matrix
    size_vec = cellvec{1};
    rows = size_vec(1);
    cols = size_vec(2);
    
    % Extract the default value
    default_value = cellvec{2};
    
    % Initialize the matrix with the default value
    matrix = default_value * ones(rows, cols);
    
    % Loop through the remaining elements of the cell vector
    for i = 3:length(cellvec)
        element = cellvec{i};
        row_index = element(1);
        col_index = element(2);
        value = element(3);
        
        % Assign the value to the appropriate position in the matrix
        matrix(row_index, col_index) = value;
    end
end
```
