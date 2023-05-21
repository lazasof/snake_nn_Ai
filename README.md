# snake_nn_Ai
from a freecodecamp tutorial messing around with nn architectures, lr, gamma values, epsilon, activation functions and rewards.<br>
in general tweaking with parameters yielded better results than tweeking with the model
<br>
<br>
concept #best highscore after 100 games aplying diferent parameters# <br>
output<br>
3 values [x,y,z] x= straight, y = right z=left<br>
#################################################<br>
inputs<br>
Danger Straight: Represents whether there is a danger in the direction the snake is currently moving.<br>
Danger Right: Represents whether there is a danger to the right of the snake's head.<br>
Danger Left: Represents whether there is a danger to the left of the snake's head.<br>
Move Direction Left: Represents whether the snake is currently moving left.<br>
Move Direction Right: Represents whether the snake is currently moving right.<br>
Move Direction Up: Represents whether the snake is currently moving up.<br>
Move Direction Down: Represents whether the snake is currently moving down.<br>
Food Location Left: Represents whether the food is located to the left of the snake's head.<br>
Food Location Right: Represents whether the food is located to the right of the snake's head.<br>
Food Location Up: Represents whether the food is located above the snake's head.<br>
Food Location Down: Represents whether the food is located below the snake's head.<br>
##################################################<br>
PARAMETERS<br>
reward for apple 10<br>
reward for being in the same x or y position with the apple 5<br>
reward for score score*10 (gives reason to hunt as many as possible in the timeftrame)<br>
reward for wall -10<br>
reward for hitting itself -15<br>
reward for not being in the same x or y position -1<br>
gamma 0.99<br>
lr 0.001 <br>
unpredictability: self.epsilon =  max(0.1, 80 - self.n_games) gets lower with every game. <br>
##########################################<br>
conditions:<br>
trying to do 3 consecutive l or 3 r turns awards the 3rd with -999999(avoid turning 270)
if previous mone was a turn there is an 0.1 beter chance to go straight.
##########################################<br>
model relu<br> (11,256,3) <br> 100 games
up until 50~60 games dont last long. the ai is exploring the space.<br>
from 50~60 the games ussually take the whole time. the ai starts to learn about the apples.<br>
using one hidden layer of 256 yielded a  best high score of 41 <br>
################################################## <br>
model relu<br> (11,256,128,3) <br>
similar performance<br>
the agent learns extremely fast that the borders are dangerous 5~10 games<br>
funny this is actually bad because every game takes more time because it times out.<br>
this model needs more parameter choosing, the ai learns extremely fast to avoid walls but is to incentivised to go to the apple<br>
bad results!<br>
################################################## <br>
as expected the same things happen with leaky rely. In conclusion relu is better(no diyng relu problem)

in later implementations i want to try halmiltonian paths. and maze traversing algorithms. generative maybe... and surely genetic!!!!!(any adverserial idea is welcome)
