# Finding-Detective-Chessboard

METHODOLOGY:
Given a n by n board where n is of form 2^k where k >= 1 (Basically, n is a power of
2 with minimum value as 2). The board has one missing square). Fill the board using
trionimos. A trionimo is an L-shaped tile is a 2 × 2 block with one cell of size 1×1
missing.
Solving the problem efficiently isn’t the goal of this post. Visualizing the board as the
algorithm runs is much more interesting in my opinion, though. Lets discuss the
algorithm first.

Steps to find the defective chessboard:
1. We have a chessboard of size n x n , where n =2k.Exactly on square is
defective in the chessboard.The tiles are in L-shape i.e. 3 squares.
Objective Cover all the chessboard with L-shape tiles, except the defective
square.
2. It is possible to cover all non-defective squares. Let’s see how. As the size of
the chessboard is n x n and n=2k. Therefore, Total no. of squares =2k x2k
=22k. No. of non-defective squares = 22k-1.Now, for the value of K,22k-1 is
divisible by 3.
3. Defective chessboards. 1x1 2 x2 2 x2 2 x2 2 x2 As the Size of these
chessboards displayed here, 1x1 and 2x2 we don’t have to place any L-shape
tile in the first and rest can be filled by just using 1 L-shaped tile. For 4x 4
chessboard.
4. For 8X8 DEFECTIVE CHESS BOARD.
One of the cell is defective.
We divide the chess board into equal sub half's.Creation of defective
box.
Trick to cover the chess board with tiles.
Again creation of defective boxes as we divide the chess board
division of problems into sub-problems.
As we have finally divided the problem into 2x2 board we will put the
tiles.
The procedure will continue until all the sub board are covered with
the tiles.
The final chess board covered with all the titles and only left with the
defectives which we created.
Here we will cover the defectives which we have created as in the
last, there should be only one defective left.Combining of all sub
problems.
• 8x8 4x4 4x4 4x4 4x4
• 2x2 2x2 2x2 4x4 2x2
• 1x1 2x2 4x4 8x8 

ALGORITHIM:
Step-1:
Apply Divide and conquer and divide the cell as 4x4 cells Step-2:
Place a L shaped tile at the centre such that it does not cover the n/2*n/2 sub
square that has a missing square.
Now all four sub-squares of size n/2*n/2 have a missing cell.
Step-3:
Now the 4x4 sub square is divided into further 2x2 squares (ie) solve the
problem recursively until the base case is reached. To make every sub-problem a
smaller version of our original problem add defects at the center, with one
square in each of the four quadrants of our board, except for the one with our
original defect would allow use to make four proper sub-problems, at the same
time ensuring that we can solve the complete problem by adding a last trionimo
to cover up the pseudo-defective squares we added.
Step-4:
Once the base case is reached then fill the L shaped tiles.
After solving each of the four sub-problems and putting them together to form a
complete board, we have 4 defects in our board: the original one will lie in one
of the quadrants, while the other three were those we had intentionally added to
solved the problem using DAC. All we have to do is add a final trionimo to
cover up those defects.
Every recursive algorithm must have a base case, to ensure that it terminates.So
we have 2x2 block with a single defect as a base case.
Step-5:
Now the chess board except the missing tile part has been successfully been
placed with L shape tiles.


 size_of_grid = 8;
memset(arr, 0, sizeof(arr));
 a = 0, b = 0; arr[a][b] = -1;
tile(size_of_grid, 0, 0);
for (int i = 0; i < size_of_grid; i++)
{
 for (int j = 0; j < size_of_grid; j++)
cout << arr[i][j] << " \t";
cout << "\n";
 }
}
