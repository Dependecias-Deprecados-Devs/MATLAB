Write a function called picker that takes three input arguments called condition, in1 and in2 in this order. The argument condition is a logical. If it is true, the function assigns the value of in1 to the output argument out,  otherwise, it assigns the value of in2 to out. See the examples below to see how picker works in practice.
```
a = 2;
b = 3;
picker(a<b,a,b)
ans =
     2
picker(a<0,1,-1)
ans =
     -1
```

### FUNCIÓN

```
function out = picker(condition, in1, in2)
    % Check the condition and assign the value of in1 or in2 to out accordingly
    if condition
        out = in1;
    else
        out = in2;
    end
end
```
