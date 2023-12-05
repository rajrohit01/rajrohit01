- 👋 Hi, I’m @rajrohit01import os

# Function to add a task to the to-do list
def add_task(task_description):
    with open("todo_list.txt", "a") as file:
        file.write(f"{task_description}\n")
    print(f"Task added: {task_description}")

# Function to display the current to-do list
def display_tasks():
    if os.path.exists("todo_list.txt"):
        with open("todo_list.txt", "r") as file:
            tasks = file.readlines()
            if tasks:
                print("Tasks:")
                for i, task in enumerate(tasks, start=1):
                    print(f"{i}. {task.strip()}")
            else:
                print("No tasks found.")
    else:
        print("No tasks found.")

# Function to mark a task as complete
def mark_as_complete(task_index):
    tasks = []
    if os.path.exists("todo_list.txt"):
        with open("todo_list.txt", "r") as file:
            tasks = file.readlines()

    if 1 <= task_index <= len(tasks):
        completed_task = tasks.pop(task_index - 1)
        with open("todo_list.txt", "w") as file:
            file.writelines(tasks)
        print(f"Task marked as complete: {completed_task.strip()}")
    else:
        print("Invalid task index.")

# Main function to run the to-do list application
def main():
    while True:
        print("\nMenu:")
        print("1. Add Task")
        print("2. Display Tasks")
        print("3. Mark Task as Completed")
        print("4. Exit")

        choice = input("Enter your choice (1-4): ")

        if choice == "1":
            task_description = input("Enter task description: ")
            add_task(task_description)
        elif choice == "2":
            display_tasks()
        elif choice == "3":
            task_index = int(input("Enter task index to mark as complete: "))
            mark_as_complete(task_index)
        elif choice == "4":
            print("Exiting application. Goodbye!")
            break
        else:
            print("Invalid choice. Please enter a number between 1 and 4.")

if __name__ == "__main__":
    main()

- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
rajrohit01/rajrohit01 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
