# octave-learning

### Displaying
```octave
disp(sprintf('display 6 decimals: %0.6f', var));

disp(sprintf('display 3 decimals: %0.3f', var));
```
*formats*

```octave
format long;

format short;
```
### Matrices

```octave
a = [1 2; 5 6; 9 5]; % 3 by 2 matrix

v = 1:6; % -> [1 2 3 4 5 6]

v = 1:0.5:2; % -> [1 1.5 2]
```

*Generating ones*

```octave
v = ones(2,3); % Generates the below
```

| 1 | 1 | 1 |
|-|-|-|
| 1 | 1 | 1 |

*Generating Randoms*

```octave
rand(3,5); % Uniform distribution

randn(3,5); % Normal distribution
```

*Generating Identity*

```octave
eye(3) % 3 by 3 identity matrix
```

*Size and Length*

```
A = [1 2; 5 6; 3 4];

size(A); % returns a 3 2 matrix

length(A); % returns the length of a vector
```

*Loading Files*

```octave
load filename.ext;

who; % shows all the variables
whos; % Detailed view of above

clear variable; % clears a variable

v = mat(1:10); % takes the first 10 of the mat matrix

save file.mat v; % saves v into file.ext

save file.txt v -ascii; % saves into human readable
```

*Picking items from Matrix*

```octave
A = [1 2; 3 4; 5 6];

A(3,2); % Gets you 6

A(2,:); % gets you the second row 3 4
A(:,2); % Gets you the second column 2 4 6
A([1 3],:) % Gets you the 1,3 rows and all the columns -> 1 2; 5 6
A(2,:) = [5 9] % changes the second row to 5 9
A(:) % Puts everything into a column vector [1; 2; 3; 4; 5; 6;]

```

### Computation

```octave
A.*B # Multiply by elements
A.^2 # Square all elements

A' # Transpose
```

### Plotting
```octave
t = [0:0.1:0.98];
y1 = sin(2*pi*4*t);
y2 = cos(2*pi*4*t);

plot(t,y1);
hold on; % Holds the graph, so other plot commands doesnt kill the previous ones
plot(t,y2,red);
xlabel('time');
ylabel('value');
legend('sin','cos');
title('my plot');
print -dpng 'myplot.png';

imagesc(A), colorbar, colormap gray; # Shows the values in color strength
```

### Control statements
```octave
% For loops
for i=1:10,
  v(i)=2^i;
end;

% While loops
i = 5;
while i <= 5,
  v(i) = 2^i;
  i = i + 1;
end;  

% Conditional
if i == 6,
  disp('six')
elseif i == 5,
  disp('five');
else
  disp('not five or six');
end
```

*Creating functions*

* Save file.m 
* Make sure you're in the right directory
* Or use the addpath('path') function to add a search path

```octave
function y = squareThisNumber(x)
y = x^2

function [y1,y2] = squareAndCube(x)
y1 = x^2
y2 = x^3

% Usage
```
