# The edgiest of cases

## Situation one
```
a addbeat 101 0 100-100 2 linear
n short rc 101
n short rc 102
n short rc 104
n short rc 105
```

Beat | Current Note Index | ActiveNotes in Conductor
------------ | ------------- | -------------
101 | (after making 101) 1 | n short rc 101
102 | 2 | n short rc 103, n short rc 102

...which is wrong, 102 should be in front of 103

### Conclusion
we should sort the activatednotes in Conductor as well
## Situation two
```
a addbeat 100 0 300-300 -199 linear
n short rc 102
n short rc 103
n short rc 104
n short rc 105

// this will become 101 at beat 100
n short rc 300
```
However, because of the way that we add notes to activenotes, the n short rc 300 -> 101 will not be read into ActiveNotes
### Conclusion
we should sort the og notes in chart as well

## Problems
Sorting is CPU demanding
- possible performance peak?

# Possible solutions
Sorting: n log(n) on the activated frames
always look for the smallest hitbeat: n every frame
always sort: n log(n) always

Sorting Activated notes are not a huge problem, because they are generally small in sizes
The problem is within the notes in chart, sorting them is going to be a lot longer

Smart solution: only sort 
