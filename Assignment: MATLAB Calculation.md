We borrowed $1000 at a 10% annual interest rate. If we did not make a payment for two years, and assuming there is no penalty for non-payment, how much do we owe now? Assign the result to a variable called debt.

### Función

```
% Principal amount
P = 1000;
% Annual interest rate
r = 0.10;
% Number of times interest is compounded per year
n = 1;
% Time period in years
t = 2;

% Calculating the amount owed
debt = P * (1 + r/n)^(n*t);

% Displaying the result
disp(debt);
```
