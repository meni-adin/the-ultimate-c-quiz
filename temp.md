int main(void)
{
    int my_int = INT_MAX - 2;
    float my_float = 1.0f;
    bool b = 1;
    unsigned int magic1 = b ? my_int : my_float;
    unsigned int magic2;
    if (b)
        magic2 = my_int;
    else
        magic2 = my_float;

    printf("magic1: %u\n", magic1);
    printf("magic2: %u\n", magic2);

    return EXIT_SUCCESS;
}
