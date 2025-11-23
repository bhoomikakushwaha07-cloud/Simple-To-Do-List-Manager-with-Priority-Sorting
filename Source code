# Simple To-Do List Manager with Priority Sorting

def add_task(tasks, description, priority):
    """Add a new task with description and priority (1=High, 2=Medium, 3=Low)"""
    task = {
        'description': description,
        'priority': priority,
        'completed': False
    }
    tasks.append(task)
    print(f"Task added: '{description}' with priority {priority}")

def view_tasks(tasks):
    """Display all tasks sorted by priority"""
    if not tasks:
        print("\nNo tasks in your list!")
        return
    
    # Sort tasks by priority (1, 2, 3)
    sorted_tasks = sort_by_priority(tasks)
    
    print("\n--- Your To-Do List ---")
    for i in range(len(sorted_tasks)):
        task = sorted_tasks[i]
        status = "✓" if task['completed'] else " "
        priority_name = get_priority_name(task['priority'])
        print(f"{i + 1}. [{status}] {task['description']} - Priority: {priority_name}")

def sort_by_priority(tasks):
    """Sort tasks by priority using bubble sort"""
    sorted_tasks = tasks.copy()
    n = len(sorted_tasks)
    
    for i in range(n):
        for j in range(0, n - i - 1):
            if sorted_tasks[j]['priority'] > sorted_tasks[j + 1]['priority']:
                # Swap tasks
                temp = sorted_tasks[j]
                sorted_tasks[j] = sorted_tasks[j + 1]
                sorted_tasks[j + 1] = temp
    
    return sorted_tasks

def get_priority_name(priority):
    """Convert priority number to name"""
    if priority == 1:
        return "High"
    elif priority == 2:
        return "Medium"
    elif priority == 3:
        return "Low"
    else:
        return "Unknown"

def mark_complete(tasks, task_number):
    """Mark a task as completed"""
    sorted_tasks = sort_by_priority(tasks)
    
    if task_number < 1 or task_number > len(sorted_tasks):
        print("Invalid task number!")
        return
    
    # Find the task in original list and mark it
    selected_task = sorted_tasks[task_number - 1]
    for task in tasks:
        if task == selected_task:
            task['completed'] = True
            print(f"Task '{task['description']}' marked as complete!")
            break

def delete_task(tasks, task_number):
    """Delete a task from the list"""
    sorted_tasks = sort_by_priority(tasks)
    
    if task_number < 1 or task_number > len(sorted_tasks):
        print("Invalid task number!")
        return
    
    # Find and remove the task from original list
    selected_task = sorted_tasks[task_number - 1]
    for i in range(len(tasks)):
        if tasks[i] == selected_task:
            removed = tasks.pop(i)
            print(f"Task '{removed['description']}' deleted!")
            break

def show_menu():
    """Display the menu options"""
    print("\n=== To-Do List Menu ===")
    print("1. Add task")
    print("2. View tasks")
    print("3. Mark task as complete")
    print("4. Delete task")
    print("5. Exit")

def main():
    """Main program loop"""
    tasks = []
    
    print("Welcome to Simple To-Do List Manager!")
    
    while True:
        show_menu()
        choice = input("\nEnter your choice (1-5): ")
        
        if choice == '1':
            description = input("Enter task description: ")
            print("Priority: 1=High, 2=Medium, 3=Low")
            priority = input("Enter priority (1-3): ")
            
            if priority in ['1', '2', '3']:
                add_task(tasks, description, int(priority))
            else:
                print("Invalid priority! Please enter 1, 2, or 3.")
        
        elif choice == '2':
            view_tasks(tasks)
        
        elif choice == '3':
            view_tasks(tasks)
            if tasks:
                task_num = input("Enter task number to mark complete: ")
                if task_num.isdigit():
                    mark_complete(tasks, int(task_num))
                else:
                    print("Please enter a valid number!")
        
        elif choice == '4':
            view_tasks(tasks)
            if tasks:
                task_num = input("Enter task number to delete: ")
                if task_num.isdigit():
                    delete_task(tasks, int(task_num))
                else:
                    print("Please enter a valid number!")
        
        elif choice == '5':
            print("Thank you for using To-Do List Manager. Goodbye!")
            break
        
        else:
            print("Invalid choice! Please enter a number between 1 and 5.")

# Run the program
if __name__ == "__main__":
    main()
