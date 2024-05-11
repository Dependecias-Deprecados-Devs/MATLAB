Write a function called minimax that takes M, a matrix input argument and returns mmr, a row vector containing the absolute values of the difference between the maximum and minimum valued elements in each row. As a second output argument called mmm, it provides the difference between the maximum and minimum element in the entire matrix. See the code below for an example: 
```
>> A = randi(100,3,4)
A =
    66    94    75    18
     4    68    40    71
    85    76    66     4
>> [x, y] = minimax(A)
x =
    76    67    81
y =
    90
```

### FUNCTION:
```
function [mmr, mmm] = minimax(M)
    % Calculate the maximum values along each row
    max_vals = max(M, [], 2);
    
    % Calculate the minimum values along each row
    min_vals = min(M, [], 2);
    
    % Calculate the absolute differences
    mmr = abs(max_vals - min_vals);
    
    % Calculate the difference between the maximum and minimum element in the entire matrix
    mmm = max(M(:)) - min(M(:));
end
```
