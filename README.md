# whatsym.m
Given a symbolic expression, outputs the symbolic variables as a cell array.

## Usage
For temporary use, put it in your working directory. For a more permanent use, put it in a folder and include it in `HOME > ENVIRONMENT > Set Path`. This script can thus be used without having it in the working directory. (Obviously, calling this function on another computer without this `m` file will not work.)

## Syntax
```
A = whatsym(symexp)
```

## Description
* Prints the symbolic variables used in the symbolic expression `symexp`. If `symexp` is a symbolic matrix, each element is treated separately and displayed on a new line.
* Returns a cell matrix of all the symbolic variables found in the cell array. If `symexp` is a n1-by-n2 symbolic matrix, a n1-by-n2 cell matrix is returned.

## Examples

### Example 1
Simple symbolic expression.
```
>> syms x y z
>> eqn = x^2 + 2*y - z;
>> A = whatsym(eqn)
```

```
[1]    [1]    'x'    'y'    'z'


A =

1×1 cell array

{1×3 cell}
```

### Example 2
3-by-2 symbolic matrix.
```
>> syms x y z
>> eqns = [x^2+y,   y^3-z;
           x,       y^2-x;
           z^2+x+y, z];
>> A = whatsym(eqns)
```

```
[1]    [1]    'x'    'y'

[1]    [2]    'y'    'z'

----------
[2]    [1]    'x'

[2]    [2]    'x'    'y'

----------
[3]    [1]    'x'    'y'    'z'

[3]    [2]    'z'


A =

3×2 cell array

{1×2 cell}    {1×2 cell}
{1×1 cell}    {1×2 cell}
{1×3 cell}    {1×1 cell}
```
