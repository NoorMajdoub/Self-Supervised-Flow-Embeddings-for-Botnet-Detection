## What byol do ?


the goal of byol is to create the right reporenstation aka embedding on an input , intially is it used for images , here i tested it with tabular data ,the goal of it is to 
create (in a self supervised manner ) the right represntation of objects , so for ones with close context we want close embeddings
 just like with simclr , later on whrn you have data you want to classify working with embeddings of that input that is already altered to be make close lements
 with close mebeddings increases your classification sucess


## dummy note:

soo this mean you mess up your "embedded" training , you can later on when you test the res with a linear clasifier you get bad ress 
images your classifer works with three classes cat dog and potato and yuor dummy simclr or byol makes the embeddings of cat and potato close 
that can later mess up your classification , you confuse kitty with potato 

## the augmented views aka pos pairs:

the trick used in both byol and simclr we take an input /batch and make augmtend view of it , aka that data (tabula ) and we cahge it up slightly in a way that will not
have strong impact on their embeddings later  , take like tabular data you add some noise or chage the value of a feaure or twxo , the conecpt is that way 
we are kinda of tricky the dummy model into being like see those two are close , yes they are mean they shuold have close embeddings, this feels like a trcik dont know why
 so here when we say pos pairs mean the input and the aumtened views we made from it, and neg pairs are that input and any other input of the dataset


 ## the neg pairs issue:
 
 suppose we have pic of kityy , the only pos pairs associted with it would be the ones we make right? eveything else wuold be neg buuuuuuut what if in the datasset
 we found another kitty that looks just the same and should have close embedding , by pushing those two far wont we be sabotaging the learning ?

## byol loss :


unlike simclr which uses constracite loss , aka it pushes far ne inputs (aka an input and its views) and push far the negativs , in byol we say i dont care about negativss and only adjust accordng
to the poss
(the loss is between the result of the projecotr of target and predictor of online)

## how the two networks work together

the target works as a helper for the training ofthe online network wich is the main netowkr being trained by gradient decent to update its weights , while the target works essentially as the "teacher that slowly gets smarteer
## how byol works (archi) 

we have two networks , online and target , we take an input (batch) and make two views out of it , each view will go thgough a network , then we compute the loss between both outputs 

## why this works

sth feels off when i first red about it , yes it do ...cause we aitn working with no negativss , it is kinda new to me at least that the loss is kinda in the batch itself and its versions 
