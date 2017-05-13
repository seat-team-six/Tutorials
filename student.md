# SEAT

In order to use SEAT as a student you need to follow 6 simple steps: 

1. Install Haskell [installation](https://www.haskell.org/platform/) or [Stack](https://docs.haskellstack.org/en/stable/README/) (recommended), a Haskell package manager which includes `GHC`. Make sure to run `stack setup` once it is installed and change the SEAT configurations as described below.

3. Install the Haskell library QuickCheck by running `cabal install QuickCheck` or `stack install QuickCheck` if you used the Stack installation.

4. [Download VS Code](https://code.visualstudio.com)

5. [Download SEAT extension](https://marketplace.visualstudio.com/items?itemName=UCL.labassignments). You can also run this command `ext install labassignments` in VS Code Quick Open.

6. Open any `.pla` file ([here](https://drive.google.com/open?id=0B-bbBbmOr9FZMlJUQXYyQ05DSGs) you have one covering Haskell basics). SEAT will automatically generate a `.hs` where you can start coding your solutions. You'll need to open the `.pla` file first everytime you want to use SEAT.

7. Whenever you want to check if your code is correct, click the button: `Check answers`. SEAT will assess your solutions and provide feedback. If the code doesn't compile, SEAT will show the compiling errors through GHCi.

Note: In order for SEAT to work correctly with Stack, two configurations must be changed (open the config file through Code > Preferences > Settings): 
  - `"seat.haskell.runHaskell"` -> `"stack runhaskell"`
  - `"seat.haskell.ghci"` -> `"stack ghci"`


# Feedback
SEAT is still under development. If you have any useful feedback or bug reports, please [contact us at marti.serra.15@ucl.ac.uk](mailto:marti.serra.15@ucl.ac.uk?subject=SEAT feedback) or preferably open an issue on [Github](https://github.com/seat-team-six/tutorials/issues). Thanks for your help!
