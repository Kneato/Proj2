# Proj2
Quadratic Formula
// function declarations
void solve_linear(double b, double c, double x);
void solve_quadratic(double a, double b, double c, double x1, double x2, double discriminant);

int main()
{
   // input the coefficients of the polynomial
    double a = 0, b = 0, c = 0, x = 0, x1 = 0, x2 = 0,discriminant = 0;
    cout << "Enter the coefficients of a quadratic polynomial a*x**2 + b*x + c: \n";
    cout << "  a? ";
    cin >> a;
    cout << "  b? ";
    cin >> b;
    cout << "  c? ";
    cin >> c;
    discriminant = b*b - 4*a*c;

   // handle degenerate case (linear equation) and quit
   if (a == 0)  // linear equation, not quadratic
       solve_linear(b, c, x);       
   else  // genuine quadratic equation ... forge ahead
       solve_quadratic(a, b, c, x1, x2, discriminant);

}

// solve the linear equation b*x + c == 0
void solve_linear(double b, double c, double x)
{
   cout << "Trying to solve linear equation "
        << b << "*x + " << c << " == 0\n";

   x = -c/b;

   if (b == 0 && c == 0)
       cout << "This is the trivial identity 0 ==" << b << "." << endl;
   else if (c < 0)
       cout << "This is the contradictory statement " << c << " == 0." << endl;
   else
       cout << "One root, x = " << x <<endl; 
   
   
}

// use classical quadratic formula to solve a genuine quadratic equation
// a*x^2 + b*x + c ==0, with a != 0
void solve_quadratic(double a, double b, double c, double x1, double x2, double discriminant)
{
   cout << "Trying to solve the quadratic equation "
        << a << "*x*x + " << b << "*x + " << c << " == 0\n";
 
   x1 = (-b + sqrt(discriminant)) / (2*a);
   x2 = (-b - sqrt(discriminant)) / (2*a);

   if (x1 == x2)
       cout << "Double root, x = "<< x1 << endl;
   else if (discriminant <= 0)
       cout << "No real roots." << endl;
   else
       cout << "Two roots, x = " << x1 << " and x = " << x2 << endl;
      
}
