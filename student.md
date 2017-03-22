# SEAT for students

In order to use SEAT you need to follow 5 simple steps: 

1. Install [Stack](https://docs.haskellstack.org/en/stable/README/), a Haskell package manager which includes `GHC`. Make sure to run `stack setup` once it is installed. 

2. [Download VS Code](https://code.visualstudio.com)

3. [Download SEAT extension](https://marketplace.visualstudio.com/items?itemName=UCL.labassignments). You can also run this command `ext install labassignments` in VS Code Quick Open.

4. Open any `.pla` file. SEAT will automatically generate a `.hs` where you can start coding your solutions.

5. Whenever you want to check if your code is correct, click the button: `Check answers`. SEAT will assess your solutions and provide feedback on them.


Note: Although Stack is highly recommended, SEAT also works with the normal Haskell [installation](https://www.haskell.org/platform/). In that case two SEAT settings have to be changed: 
  - `"seat.haskell.runHaskell"` -> `"runHaskell"`
  - `"seat.haskell.ghci"` -> `"ghci"`