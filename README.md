# Tcl puts stderr Unexpected Behavior in Procedures

This repository demonstrates a subtle bug related to the use of `puts stderr` within a Tcl procedure that also returns a value.  The issue stems from the interaction between the `puts stderr` command and the procedure's return value. While `puts stderr` correctly sends output to standard error, the procedure's return value might be unexpectedly affected or lost.

## Bug Description

The `badproc` procedure demonstrates the problem.  It appears to work correctly, but in certain contexts the output is silently discarded and the returned value is not what's expected.

## Solution

The solution involves careful handling of standard error output and ensuring that the `return` statement doesn't overwrite or interfere with the stderr output.  The `goodproc` procedure demonstrates this corrected approach.