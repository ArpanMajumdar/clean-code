# Chapter - 2: Meaningful names

1. Use intention revealing names

Wrong

``` java
int d; // elapsed time in days
```

Correct
``` java
int elapsedTimeInDays;
int daysSinceCreation;
int daysSinceModification;
int fileAgeInDays;
```

2. Choose good names so that code is easy to understand. Magic numbers should not be used.

Wrong
``` java
public List<int[]> getThem() {
    List<int[]> list1 = new ArrayList<int[]>();
    for (int[] x : theList)
    if (x[0] == 4)
        list1.add(x);
    return list1;
}
```

Correct
``` java
public List<int[]> getFlaggedCells() {
    List<int[]> flaggedCells = new ArrayList<int[]>();
    for (int[] cell : gameBoard)
    if (cell[STATUS_VALUE] == FLAGGED)
    flaggedCells.add(cell);
    return flaggedCells;
}
```

3. Avoid disinformation
   - Do not append type of data structure to the name. e.g.- `accountList`. Try using plural like `accounts`.
   - Do not use `l` and `o` as variable names as they can be misunderstood as `0` or `1`.

4. Make meaningful distinctions
    - Do not create variable name just for avoiding error. e.g. - `klass` instead of `class`.
    - Do not use number series as variable names. e.g. - `a1`, `a2`, ... `an`.
    - Do not use noise words like `info` or `data`. e.g.- There is no meaningful difference between `Customer` and `CustomerInfo`.

5. Use pronounciable names

Wrong
``` java
class DtaRcrd102 {
    private Date genymdhms;
    private Date modymdhms;
    private final String pszqint = ”102”;
    /* … */
};
```

Correct
``` java
class Customer {
    private Date generationTimestamp;
    private Date modificationTimestamp;;
    private final String recordId = ”102”;
    /* … */
};
```

6. Use searchable names. Don't use just numbers in code as it is very difficult to find and change their value everywhere if we want to. Use `UPPER_CAMEL_CASE` for naming constants.

Wrong
``` java
for (int j=0; j<34; j++) {
    s += (t[j]*4)/5;
}
```

Correct
``` java
int realDaysPerIdealDay = 4;
const int WORK_DAYS_PER_WEEK = 5;
int sum = 0;
for (int j=0; j < NUMBER_OF_TASKS; j++) {
    int realTaskDays = taskEstimate[j] * realDaysPerIdealDay;
    int realTaskWeeks = (realdays / WORK_DAYS_PER_WEEK);
    sum += realTaskWeeks;
}
```

7. Don't use prefixes for encoding type of object. e.g. - `IShapeFactory` instead of `ShapeFactory`.

8. Avoid single letter variable names(except possibly inside a for loop).
9. Class names should be nouns and method names should be verbs.
10. When constructors are overloaded, use static factory methods with names that describe the arguments.

Wrong
``` java
Complex fulcrumPoint = Complex.FromRealNumber(23.0);
```

Correct
``` java
Complex fulcrumPoint = new Complex(23.0);
```
11. Pick one word for one abstract concept and stick with it. For instance, it’s confusing to have `fetch`, `retrieve`, and `get` as equivalent methods of different classes.
12. Do not prefix every class with same letters. e.g. - `GSD` in `GSDAccountAddress` as you are making harder for IDE to autocomplete. 



