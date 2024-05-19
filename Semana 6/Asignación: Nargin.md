Write a function called under_age that takes two positive integer scalar arguments: 
age that represents someone's age, and 
limit that represents an age limit. 
The function returns true if the person is younger than the age limit. If the second argument, limit, is not provided, it defaults to 21. You do not need to check that the inputs are positive integer scalars. The name of the output argument is too_young.

### Función
```
function too_young = under_age(age, limit)
    % Check if the second argument limit is provided
    if nargin < 2
        limit = 21; % Set default limit to 21 if not provided
    end
    
    % Check if the person is younger than the age limit
    too_young = age < limit;
end
```
