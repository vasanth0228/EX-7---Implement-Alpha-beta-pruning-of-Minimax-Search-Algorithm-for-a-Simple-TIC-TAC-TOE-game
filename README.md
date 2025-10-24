<h1>ExpNo 7 : Implement Alpha-beta pruning of Minimax Search Algorithm for a Simple TIC-TAC-TOE game</h1> 
<h3>Name: Vasanth kumar V</h3>
<h3>Register Number: 2305002027         </h3>
<H3>Aim:</H3>
<p>
Implement Alpha-beta pruning of Minimax Search Algorithm for a Simple TIC-TAC-TOE game
</p>
<h1>GOALS of Alpha-Beta Pruning in MiniMax Search Algorithm</h1>

<h3>Improve the decision-making efficiency of the computer player by reducing the number of evaluated nodes in the game tree.</h3>
<h3>Tic-Tac-Toe game implementation incorporating the Alpha-Beta pruning and the Minimax algorithm with Python Code.</h3>
<h1>IMPLEMENTATION</h1>

The project involves developing a Tic-Tac-Toe game implementation incorporating the Alpha-Beta pruning with the Minimax algorithm. Using this algorithm, the computer player analyzes the game state, evaluates possible moves, and selects the optimal action based on the anticipated outcomes.

<h1>The Minimax algorithm</h1>

recursively evaluates all possible moves and their potential outcomes, creating a game tree.

<h1>Alpha-Beta pruning</h1>

Alpha–Beta (𝛼−𝛽) algorithm is actually an improved minimax using a heuristic. It stops evaluating a move when it makes sure that it’s worse than a previously examined move. Such moves need not to be evaluated further.

When added to a simple minimax algorithm, it gives the same output but cuts off certain branches that can’t possibly affect the final decision — dramatically improving the performance

## PROGRAM
```python
import math
def win(b):
    for x,y,z in [(0,1,2),(3,4,5),(6,7,8),(0,3,6),(1,4,7),(2,5,8),(0,4,8),(2,4,6)]:
        if b[x]==b[y]==b[z] and b[x]!=' ': return b[x]
    return None
def minimax(b,d,mx,a,bta):
    w=win(b)
    if w=='X': return 10-d
    if w=='O': return d-10
    if ' ' not in b: return 0
    f=-math.inf if mx else math.inf
    for i in range(9):
        if b[i]==' ':
            b[i]='X' if mx else 'O'
            sc=minimax(b,d+1,not mx,a,bta)
            b[i]=' '
            if mx: f=max(f,sc); a=max(a,f)
            else: f=min(f,sc); bta=min(bta,f)
            if bta<=a: break
    return f
def best_move(b):
    m=-1;v=-math.inf
    for i in range(9):
        if b[i]==' ': b[i]='X';s=minimax(b,0,0,-math.inf,math.inf);b[i]=' '
        if b[i]==' ' and s>v: v=s;m=i
    return m
b=['X','O','X','O','O',' ','X',' ',' ']
for i in range(0,9,3): print(b[i:i+3])
print("\nBest move for X:",best_move(b))

```
<hr>
<h2>Sample Input and Output:</h2>

<img width="405" height="257" alt="Screenshot 2025-10-24 134657" src="https://github.com/user-attachments/assets/b468bdcd-dba4-439f-8722-1599d302bed1" />


## RESULT
We have successfully implemented Alpha-beta pruning of Minimax Search Algorithm for a Simple TIC-TAC-TOE game.
