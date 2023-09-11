## Github on the command line

1. On your github account, create a github repo named "Only alkanes"
2. Clone the newly created repo to your local machine
3. Copy the contents of *alkanes* folder from *shell-lesson-data/exercise-data/*, used in previous classes, into your "Only alkanes" repo
4. Run the following command while inside the repo
```for j in `ls *.pdb`; do for k in {1..100}; do cp $j $(basename -s .pdb $j)$k.pdb; done; done```
5. Find the **easiest** way to push **only** the .pdb files whose number suffix is divisible by 10

6. Document your answer/work-around for the task *number 5* in a markdown file named "Easiest solution.md"
