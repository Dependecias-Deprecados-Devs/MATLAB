Write a function called valid_date that takes three positive integer scalar inputs year, month, day. If these three represent a valid date, return a logical true, otherwise false. The name of the output argument is valid. If any of the inputs is not a positive integer scalar, return false as well. Note that every year that is exactly divisible by 4 is a leap year, except for years that are exactly divisible by 100. However, years that are exactly divisible by 400 are also leap years. For example, the year 1900 was not leap year, but the year 2000 was. Note that your solution must not contain any of the date related built-in MATLAB functions.	

### Función
```
function valid = valid_date(year, month, day)
    % Check if inputs are positive integer scalars
    if ~isscalar(year) || ~isscalar(month) || ~isscalar(day) || ...
       year <= 0 || month <= 0 || day <= 0 || ...
       year ~= floor(year) || month ~= floor(month) || day ~= floor(day)
        valid = false;
        return;
    end
    
    % Determine the number of days in each month
    if month == 1 || month == 3 || month == 5 || month == 7 || ...
       month == 8 || month == 10 || month == 12
        days_in_month = 31;
    elseif month == 4 || month == 6 || month == 9 || month == 11
        days_in_month = 30;
    elseif month == 2
        % Check if the year is a leap year
        if (mod(year, 4) == 0 && mod(year, 100) ~= 0) || (mod(year, 400) == 0)
            days_in_month = 29;
        else
            days_in_month = 28;
        end
    else
        valid = false;
        return;
    end
    
    % Check if the day is within the valid range for the given month
    if day > 0 && day <= days_in_month
        valid = true;
    else
        valid = false;
    end
end
```
