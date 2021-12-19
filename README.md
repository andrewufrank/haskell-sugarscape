# haskell-sugarscape
An implementation of the FULL Sugarscape model, including property-based tests.

A description of the validation process can be found in validation_sugarscape.pdf

To run a prepared scenario:

RUNNING FROM COMMAND LINE EXAMPLES (copied from Main.hs - there more detail for Profiling etc.)

## using stack
- clear & stack exec -- sugarscape -s "Animation II-3" -f 1000 -o export/dynamics.m -r 42
-- clear & stack exec -- sugarscape -s "Animation II-3" -v 0 --ac Default --sc Resource -r 42

-- clear & stack exec -- sugarscape -s "Animation II-8" -f 1000 -o export/dynamics.m -r 42

## using cabal

- cabal build
- cabal install 
- sugarscape -s "Animation II-3" -f 1000 -o export/dynamics.m -r 42

produces a file `export/dynamics.m` (takes time, reports the settings used)

the results can be ploted with octave (perhaps also with mathlab?); install with `sudo apt install octave`

start octave in the `export` directory with `octave` 

on prompt:
- dynamics  (which loads the result of the )
- plotAgeHist (produces a histogram)

any of the scripts with extension `.m` in exports. 
