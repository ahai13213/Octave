%mass of block
m=1;%kg
%compression in spring
dx=5*10^-2;%m (5 cm converted to meters)
%spring constant
k=4000;%N/m
%vector to store inclination angle
thita=10:10:50;%in degrees
%accelration due to gravity
g=9.81;%m/s2

%creating string array to store conclusion if block reaches the top
conclusion=repmat(string("0"),[numel(thita),1]);%intializing with string "0"
for i=1:1:numel(thita)
    if (k*dx)-(m*g*sin(thita(i)*pi/180))>=0
        conclusion(i)='Block will reach to top';
    else
        conclusion(i)='Block will not reach to top';
    end
end

%printing result in table form
disp('Answer to Q2 is:');
thita=thita';%coverting to column vector
disp(table(thita,conclusion));
