# What time is it?
For this activity, you will be measuring the performance characteristics of
various sorting algorithms, defined in [sort.py](sort.py).


## Timeit
Experiment with the timeit module by seeing how long the various sort
implementations take. While you could modify [sort.py](sort.py) directly, you
can take advantage of the command line interface to test different algorithms:

```console
% python -m timeit "from sort import quick_sort as sort, random_seq; print(sort(random_seq))"
```

The reason for the `as` keyword is so that you can change search algorithms in
one place instead of two.

After running the above command once, you can take advantage of your shell's command substitution
by running the following in your terminal:

```console
% ^quick^merge
```
The word after the first `^` signifies the word in the previous command to
replace, and the word after the second `^` signifies the word to use as a
replacement.

Doing so will result in the following command:

```console
% python -m timeit "from sort import merge_sort as sort, random_seq; print(sort(random_seq))"
```
**Special Note**: When running your timing profile on the **bubble_sort** algorithm, don't give up! Your computer is not stalled in an infinite loop. Waaaaaiiiiiitttttt for it ....

## cProfile
You can measure the performance of all algorithms by using the cProfile module
and running the script:

```console
% python -m cProfile -o sort.profile sort.py
```

You can then pass the resulting `sort.profile` file to the `pstats` module:

```console
% python -m pstats sort.profile
```

Take a look at
[this](https://www.stefaanlippens.net/python_profiling_with_pstats_interactive_mode/)
article for help on how to analyze statistics.


# Credits
For a closer look at some of the algorithms used in this activity, see 
[A tour of the top 5 sorting algorithms with Python code
](https://medium.com/@george.seif94/a-tour-of-the-top-5-sorting-algorithms-with-python-code-43ea9aa02889).
