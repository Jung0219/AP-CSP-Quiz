# AP-CSP-Quiz
AP CSP Quiz 2022/04/30
# Your friend will complete this function
def play_once(human_plays_first):
    """
    Must play one round of the game. If the parameter
    is True, the human gets to play first, else the
    computer gets to play first.  When the round ends,
    the return value of the function is one of
    -1 (human wins),  0 (game drawn),   1 (computer wins).
    """
  
    import random          # See Modules chapter ...
    rng = random.Random()
    # Pick a random result between -1 and 1.
    result = rng.randrange(-1,2)
    print("Human plays first={0},  winner={1} "
                    .format(human_plays_first, result))

    return result  

import random

random_boolean = random.choice([True, False])

score = 0
human_score = 0
computer_score = 0
draw_score = 0

def main_program():
  result = play_once(random_boolean)
  global score
  global human_score
  global computer_score
  global draw_score
  
  if result == 1:
    print("I win! ")
    score += result
    computer_score += 1
  elif result == 0:
    print("Game drawn!")
    score += result
    draw_score += 1
  elif result == -1:
    print("You win!")
    score += result
    human_score += 1
  
  print("you = " + str(human_score) + " me = " + str(computer_score) + " ties = " + str(draw_score))

  total_played = human_score + computer_score + draw_score
  percentage = float((human_score / total_played) * 100)
  print("Percentage of human wins = " + str(percentage))
  
  
  response = input("Do you want to play again? (y/n) ")
  response = response.lower()

  if response == "yes" or response == "y":
    main_program()
  else:
    print("Goodbye")

main_program()
