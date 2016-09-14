# circular-prime

bool checkCircularPrime (int n)
{
    if (n < 2) return false;
    if (n == 2) return true;
    if (n % 2 == 0) return false;
    double s = sqrt(n);
    for ( int i=3; i<=s; i+=2)
    {
        if (( n%i) == 0) return false;

    }
    return true;
}
int main()
{
    int count=0, N=10;
    int j=0; // array length
    int arr[N];
    int num =0;
    int tempCount;
    for (int n=2 ; n<N ; n++)
    {
       if (checkCircularPrime(n))
        {
            while ( n!=0 )
            {
                int d;
                d = n%10;
                arr[j] = d;
                n/=10;
                j++;
            }
            for ( int i=0; i<j; i++)
            {
                int first = arr[0];
                for ( int i=0; i<j-1; i++)
                    arr[i] = arr[i+1];
                arr[j-1] = first;
                for ( int i=j-1; i=0; i--)
                {
                    num += (pow(10, i)*arr[j-1-i]);
                }
                if (checkCircularPrime(num)) tempCount++;
            }
            if (tempCount == j) count++;
        }
    }
    cout << count;
}
