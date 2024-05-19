Write a function called freezing that takes a vector of numbers that correspond to daily low temperatures in Fahrenheit. Return numfreeze, the number of days with sub freezing temperatures (that is, lower than 32 F) without using loops. Here is an example run:
```
numfreeze = freezing([45 21 32 31 51 12])
numfreeze =
     3
```

### Función
```
function numfreeze = freezing(temperatures)
    % Find the number of days with temperatures lower than 32 F
    numfreeze = sum(temperatures < 32);
end
```
