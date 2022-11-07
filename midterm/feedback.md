# Notes on the Midterm

* _Correctness    (out of 40):_ 39
* _Good Practices (out of 10):_ 8
* _Docs / Testing (out of 10):_ 10

_Details on the grading criteria for the midterm can be found on [Canvas](https://canvas.slu.edu/courses/28045/rubrics/23671)._

You did a great job with documentation and testing.  Thank you! Overall, a great job.


## Step 1
* Your `with open(...)` and work to read the `data` variable live outside your `average_rate()` function, meaning that the function won't work without those extra lines of code.  The function was supposed to do the work of opening the file and reading the contents, too.  I've deducted 1 point from _Correctness_ for this.

## Step 2
* Same note as above on when you open the file.
* You're missing an explicit `return None` somewhere for the case where the matching billing / service code entry isn't found.  You should handle that situation explicitly rather than just not returning anything.
* I wonder if your `else: None` was intended to be a `return None`, but in that case, you wouldn't want it inside the loops. It would return None as soon as any entry didn't match the requested billing / service code.  The appropriate way to do this is with a `return None` at the end of the function.

## Step 3
* Same note as above on opening the file. The only reason this works is because `data` has been read in by your earlier cells.
* This step should have reused your `get_rate()` function already written above, rather than copying all of the same code. After getting the base rate, it could have applied the adjustments.  I've deducted 1 point from _Good Practices_ for this.

## Step 4
* You built this up in three separate stages: read in the data, process the data into summary buckets, round the answers.  That works, but it would have been more efficient to go ahead and do all the work in your `for each_row in rows:` loop at the same time you were already reading the data.  I've deducted 1 point from _Good Practices_ for this.
* There is also a function for the csv package called `DictReader()` that does much the same thing as what you did manually while reading the file in.