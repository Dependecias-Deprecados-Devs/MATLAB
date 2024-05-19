Write a function called char_counter that counts the number of a certain character in a text file. The function takes two input arguments, fname, a char vector of the filename and character, the char it counts in the file. The function returns charnum, the number of characters found. If the file is not found or character is not a valid char, the function return -1. As an example, consider the following run. The file "simple.txt" contains a single line: "This file should have exactly three a-s..."
```
charnum = char_counter('simple.txt','a')
charnum = 
   3
```
You may find it helpful to download the files for testing and dubugging in MATLAB.
simple.txt
Frankenstein-by-Shelley.txt

### Función
```
function charnum = char_counter(fname, character)
    % Verificar si el carácter es un solo carácter
    if ~ischar(character) || length(character) ~= 1
        charnum = -1;
        return;
    end
    
    % Intentar abrir el archivo
    fid = fopen(fname, 'r');
    if fid == -1
        charnum = -1;
        return;
    end
    
    % Leer el archivo y contar el número de ocurrencias del carácter
    file_content = fread(fid, '*char').';
    charnum = sum(file_content == character);
    
    % Cerrar el archivo
    fclose(fid);
end
```
