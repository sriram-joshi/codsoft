import tkinter as tk

class ToDoListApp:
    def __init__(self, root):
        self.root = root
        self.root.title("To-Do List")
        
        self.tasks = []
        self.task_entry = tk.Entry(root, width=30)
        self.task_entry.grid(row=0, column=0, padx=5, pady=5)
        
        self.add_button = tk.Button(root, text="Add Task", command=self.add_task)
        self.add_button.grid(row=0, column=1, padx=5, pady=5)

        self.update_button = tk.Button(root, text="Update Task", command=self.update_task)
        self.update_button.grid(row=0, column=2, padx=5, pady=5)

        self.delete_button = tk.Button(root, text="Delete Task", command=self.delete_task)
        self.delete_button.grid(row=0, column=3, padx=5, pady=5)

        self.task_list = tk.Listbox(root, width=40, height=10)
        self.task_list.grid(row=1, column=0, columnspan=4, padx=5, pady=5)

        self.load_tasks()

    def add_task(self):
        task_name = self.task_entry.get()
        if task_name:
            self.tasks.append(task_name)
            self.task_list.insert(tk.END, task_name)
            self.task_entry.delete(0, tk.END)

    def update_task(self):
        selected_index = self.task_list.curselection()
        if selected_index:
            new_task_name = self.task_entry.get()
            if new_task_name:
                index = selected_index[0]
                self.tasks[index] = new_task_name
                self.task_list.delete(index)
                self.task_list.insert(index, new_task_name)
                self.task_entry.delete(0, tk.END)

    def delete_task(self):
        selected_index = self.task_list.curselection()
        if selected_index:
            index = selected_index[0]
            del self.tasks[index]
            self.task_list.delete(index)

    def load_tasks(self):
        for task in self.tasks:
            self.task_list.insert(tk.END, task)

if __name__ == "__main__":
    root = tk.Tk()
    app = ToDoListApp(root)
    root.mainloop()
