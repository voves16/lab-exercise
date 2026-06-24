# Conflict Graph
# An edge between two exams means at least one student is taking both exams
graph = {
    'Math': ['Physics', 'Chemistry'],
    'Physics': ['Math', 'English'],
    'Chemistry': ['Math', 'English'],
    'English': ['Physics', 'Chemistry']
}
# Available Exam Time Slots
time_slots = ["Slot-1", "Slot-2", "Slot-3"]
# Dictionary to store exam schedule
exam_schedule = {}
# Function to check whether a time slot can be assigned
def is_safe(exam, slot):
    for neighbor in graph[exam]:
    if neighbor in exam_schedule and exam_schedule[neighbor] == slot:
    return False
    return True
# Backtracking function
def solve_timetable(exams, index):
    # Base Case: All exams assigned
    if index == len(exams):
    return Tru
    current_exam = exams[index]
    # Try each available time slot
    for slot in time_slots:
    if is_safe(current_exam, slot):
    exam_schedule[current_exam] = slot
 # Recur for next exam
  if solve_timetable(exams, index + 1):
     return True
  # Backtrack
  del exam_schedule[current_exam]
   return False
# Main Program
exams = list(graph.keys())
if solve_timetable(exams, 0):
    print("Exam Timetable")
    print("-" * 25)
    for exam, slot in exam_schedule.items():
        print(f"{exam:10} --> {slot}")
else:
    print("No feasible timetable found.")


    
Output:
Exam Timetable
Math       --> Slot-1
Physics    --> Slot-2
Chemistry  --> Slot-2
English    --> Slot-1
