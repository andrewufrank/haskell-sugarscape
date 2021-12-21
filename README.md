# haskell-sugarscape
An implementation of the FULL Sugarscape model as published in _Epstein and Axtel, Growing Artificial Societies, MIT Press, 1996 _, including property-based tests.

A description of the validation process can be found in `validation_sugarscape.pdf`.

## Installation using cabal
Install GHC with `ghcup`. The current state can be compiled wtih ctive (test with `ghcup tui`):

    GHC   8.10.4          base-4.14.1.0 

Prerequisit: 

    apt install libglut1-mesa-dev 

Clone from github and install : 
    git clone https://github.com/thalerjonathan/haskell-sugarscape.git
    cd haskell-sugarscape
    cabal build 
    cabal install 

## Running example scenarios from command line

After `cabal install` one can run preset scenarios (correspondign to Epstein & Axtel), for example: 

    sugarscape -s "Animation II-3" -f 1000 -o export/dynamics.m -r 42

The parameters are:

    - s name of the scenario (check `Main.hs` for what is available)
    - f the number of steps 
    - o the name of the output file 
    - r the RNG Seed

    <!-- What is `--ac Default` or `--sc Resource` -->
    <!-- what does clear -->

In `Main.hs` are more examples for scenarios and hints for testing and profiling. 

Running an example writes the settings used to the terminal and, after a while,  produces a file which describe the result, e.g. `export/dynamics.m` 
 
### using stack
- clear & stack exec -- sugarscape -s "Animation II-3" -f 1000 -o export/dynamics.m -r 42

- clear & stack exec -- sugarscape -s "Animation II-3" -v 0 --ac Default --sc Resource -r 42

- clear & stack exec -- sugarscape -s "Animation II-8" -f 1000 -o export/dynamics.m -r 42

## Plots 
The results can be plotted with octave; 
<!-- (perhaps also with mathlab?);  -->
install with `sudo apt install octave`. Then start octave in the `export` directory with `octave` 

On octave's prompt load the result with:

    dynamics 

On the next prompt enter any of the scripts with extension `.m` in `exports`. They produce the desired visualization of the run of the scenario. E.g. 
    
      `plotAgeHist` produces a histogram 
