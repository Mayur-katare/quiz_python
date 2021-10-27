
def quiz():

    guesses = []
    correct_guesses = 0
    question_num = 1

    for key in questions:
        print("-------------------------")
        print(key)
        for i in options[question_num-1]:
            print(i)
        guess = input("Enter (A, B, C, or D): ")
        guess = guess.upper()
        guesses.append(guess)

        correct_guesses += check_answer(questions.get(key), guess)
        question_num += 1

    display_score(correct_guesses, guesses)

# -------------------------
def check_answer(answer, guess):

    if answer == guess:
        print("CORRECT!")
        return 1
    else:
        print("WRONG!")
        return 0


#-----------------------------
questions = {
 "Which one is correct team name in NBA?: ": "D",
 "5 + 7 = ?:": "C",
"12 - 8 = ?:": "D"
}

options = [
                ["A.New York Bulls",
                  "B.Los Angeles Kings",
                  "C.Golden State Warriros",
                  "D.Huston Rocket"],
                  ["A.10",
                  "B.11",
                  "C.12",
                  "D.13"],
                  
                  [ "A.1",
                  "B.2",
                  "C.3",
                  "D.4"]]

quiz()


# -------------------------
