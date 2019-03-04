# 15-Febrero
%PROBLEMA1
syms x a

Y = 2*x+a;

X = solve(Y==5,x)

x_sust_a=subs(X,a,1)

y_comp = subs(Y,[a x],[1 x_sust_a])




%PROBLEMA2
syms x a b

Y = x.^2+a*x+b

X = solve(Y==0,x) 

x_sust1_ab = subs(X(1,1), [a b],[5 2])
x_sust2_ab = subs(X(2,1), [a b],[5 2])

y_comp1 = subs(Y,[a b x],[5 2 x_sust1_ab])
y_comp2 = subs(Y,[a b x],[5 2 x_sust2_ab])

vpa(y_comp1)
vpa(y_comp2)




%PROBLEMA3
syms x a b

Y = 2*exp(x)+3*cos(x)

X = solve(Y==0,x)

x_sust=subs(X)

comp1 = subs(Y,[x],[x_sust])




%PROBLEMA4
syms x y c

Ec1 = 2*x -3*c*y;
Ec2 = c*x +2*y;

[Sol1 Sol2] = solve([Ec1 == 5 Ec2 == 7],[x y])
[Sol1] = solve([Ec1 == 5],[x])
[Sol2] = solve([Ec2 == 7],[y])
%xy_sol1 = subs(Sol1, [c], [1])
%xy_sol2 = subs(Sol2, [c], [1])

%[comp1] = subs(Ec1, [x y c], [1 1 xy_sol1])
%[comp2] = subs(Ec2, [x y c], [1 1 xy_sol2])




%PROBLEMA5
syms x y

Ec1 = 3*x.^2 -2*x +y -7 ==0
Ec2 = x*y +x -5 == 0

[Sol1] = solve([Ec1],[x])

y_sol1 = subs(Sol1,y,5)

comp1 = subs(Ec1, x, y_sol1)
