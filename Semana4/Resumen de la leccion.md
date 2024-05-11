Write a function called trio that takes two positive integer inputs n and m. The function returns a 3n-by-m matrix called T. The top third of T (an n by m submatrix) is all 1s, the middle third is all 2-s while the bottom third is all 3-s. For an example,see the code below:
```
M = trio(2,4)
M =
     1     1     1     1
     1     1     1     1
     2     2     2     2
     2     2     2     2
     3     3     3     3
     3     3     3     3
```

### Función

```
function T = trio(n, m)
    % Create the top third of T with all 1s
    top_third = ones(n, m);
    
    % Create the middle third of T with all 2s
    middle_third = 2 * ones(n, m);
    
    % Create the bottom third of T with all 3s
    bottom_third = 3 * ones(n, m);
    
    % Concatenate the three thirds vertically to form T
    T = [top_third; middle_third; bottom_third];
end
```
