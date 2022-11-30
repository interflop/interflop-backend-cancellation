# interflop-backend-cancellation

## Arguments

The Cancellation backend implements an automatic cancellation detector at
runtime. It is founded on difference in exponents to detect cancellation faster
than in other backend. If a cancellation is detected then the backend applies
noise on the cancelled part with the model of noise from the MCA backend. The
backend additional cost of runtime time is constant and predetermined for each
operation performed.

```
Info [verificarlo]: loaded backend libinterflop_cancellation.so
Usage: libinterflop_cancellation.so [OPTION...]

  -s, --seed=SEED            Fix the random generator seed
  -t, --tolerance=TOLERANCE  Select tolerance (TOLERANCE >= 0)
  -w, --warning=WARNING      Enable warning for cancellations
  -?, --help                 Give this help list
      --usage                Give a short usage message

```

Three options control the behavior of the Cancellation backend.

The option `--tolerance` sets the tolerance within the backend will trigger a
cancellation. By default tolerance is set to 1.

The option `--warning` warns on the standard output stream when a cancellation is
triggered by the backend.

The option `--seed` fixes the random generator seed. It should not generally be
used except if one to reproduce a particular MCA trace.

Finally the user should know that this backend is still experimental and in
developpement.
