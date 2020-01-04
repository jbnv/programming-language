```
@factorial = function {
    parameter @n constraint [integer, @>= 1];

    @n == 1 ? return 1;
    return [self](../keywords/self.md)(n-1);
}
