import random

quiz_data = [
    
    {
        "question": "What is the largest organ in the human body?",
        "options": ["Brain", "Heart", "Skin", "Liver"],

        "correct_answer": "Skin",
    },
    {
         "question": "Which of the following is the powerhouse of the cell?",
        "options": ["Nucleus", "Mitochondria", "Ribosome", "Golgi apparatus"],
        "correct_answer": "Mitochondria",
        
    },{

        "question": "What is the process by which green plants make their own food using sunlight?",
        "options": ["Respiration", "Photosynthesis", "Digestion", "Fermentation"],
        "correct_answer": "Photosynthesis",
    },{
   
        "question": "What is the name of the genetic material found in the nucleus of eukaryotic cells?",
        "options": ["RNA", "DNA", "protein", "Lipid"],
        "correct_answer": "DNA",
        
    },{
       
        "question": "What is the function of red blood cells?",
        "options": ["Carry oxygen", "Produce hormones", "Fight infections", "Store energy"],
        "correct_answer": "Carry oxygen",
    },{
       
        "question": "Which part of the plant is responsible for photosynthesis?",
        "options": ["Roots", "Leaves", "Stem", "Flower"],
        "correct_answer": "Leaves",
    },{
       
        "question": "What is the basic unit of life?",
        "options": ["Cell", "Tissue", "Organisms", "Organ"],
        "correct_answer": "Cell",
    }

    # Add more questions here...
]

def ask_question(question_data):
    print(question_data["question"])
    for i, option in enumerate(question_data["options"], start=1):
        print(f"{i}. {option}")

    user_choice = input("Enter the number corresponding to your answer: ")
    try:
        user_choice = int(user_choice)
        selected_option = question_data["options"][user_choice - 1]
        if selected_option == question_data["correct_answer"]:
            print("Correct!\n")
            return 1
        else:
            print(f"Sorry, the correct answer is {question_data['correct_answer']}.\n")
            return 0
    except (ValueError, IndexError):
        print("Invalid input. Please enter a valid option.\n")
        return 0

def main():
    random.shuffle(quiz_data)  # Shuffle the order of questions
    total_score = 0
    for question in quiz_data:
        total_score += ask_question(question)

    print(f"Your total score: {total_score}/{len(quiz_data)}")

if __name__ == "__main__":
    main()
