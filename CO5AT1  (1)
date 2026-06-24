# Employees and their skills
employees = {
    "E1": ["Programming"],
    "E2": ["Programming""Testing"],
    "E3": ["Testing"]
}
# Jobs: (required_skill, start_time, end_time)
jobs = [
("J1", "Programming", 9, 11),
("J2", "Testing", 10, 12),
("J3", "Programming", 11, 13)
]
# Store assignments
assignment = {}
# Check if employee is free during job time
def is_valid(employee, start, end):
 for job, emp in assignment.items():
 if emp == employee:
 for j in jobs:
 if j[0] == job:
 s, e = j[2], j[3]
 if not (end <= s or start >= e):
 return False
 return True
# Backtracking function
def schedule(job_index):
    if job_index == len(jobs):
    return True
    job_name, skill, start, end = jobs[job_index]
    for employee in employees:
    if skill in employees[employee]:
    if is_valid(employee, start, end):
    assignment[job_name] = employee
    if schedule(job_index + 1):
    return True
    del assignment[job_name]
    return False
# Run scheduling
if schedule(0):
    print("Job Assignment:")
    for job, emp in assignment.items():
    rint(job, "->", emp)
else:
    print("No valid schedule found")


Output:
Job Assignment:
J1 -> E1
J2 -> E3
J3 -> E1
