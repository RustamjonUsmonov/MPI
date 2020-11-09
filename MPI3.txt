
#include <iostream> 
#include "mpi.h" 
double Y(double x)
{
	return x * x;
}
int main(int argc, char** argv)
{
	int rank;
	int size;
	MPI_Status status;
	MPI_Init(&argc, &argv);
	MPI_Comm_rank(MPI_COMM_WORLD, &rank);
	MPI_Comm_size(MPI_COMM_WORLD, &size);

	double x[10];
	double y[10];
	double c[10];
	double x1;
	double x2;
	int n = 1000;
	double sum = 0;

	double h = (x2 - x1)/n;
	double x = x1 + (h / 2.0) + (h * n * rank / size);

	
	x[0] = 5;y[0] = 3;
	x[1] = 2;y[1] = 2;
	

	for (int i=0;i<=sizeof(c);i++) 
	{
		c[i] = h * y[i];
	}

	for (int i = 0; i < sizeof(c); i++)
	{
		sum += n / size;
		std::cout << c[i];
	}
	MPI_Finalize();
}