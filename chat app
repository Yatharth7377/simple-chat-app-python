import time
import tkinter as tk

class Message:
    def __init__(self, sender, content, timestamp):
        self.sender = sender
        self.content = content
        self.timestamp = timestamp

class ChatApp:
    def __init__(self, root):
        self.root = root
        self.root.title("Simple Chat App")
        self.message_list = []

        # Create UI elements
        self.message_frame = tk.Frame(root)
        self.message_frame.pack(fill=tk.BOTH, expand=True)
        self.message_text = tk.Text(self.message_frame, state=tk.DISABLED)
        self.message_text.pack(fill=tk.BOTH, expand=True)

        self.input_frame = tk.Frame(root)
        self.input_frame.pack(fill=tk.X)
        self.input_entry = tk.Entry(self.input_frame)
        self.input_entry.pack(side=tk.LEFT, fill=tk.BOTH, expand=True)
        self.send_button = tk.Button(self.input_frame, text="Send", command=self.send_message)
        self.send_button.pack(side=tk.RIGHT)

    def send_message(self):
        message_content = self.input_entry.get()
        if message_content:
            message = Message("You", message_content, time.strftime("%H:%M:%S"))
            self.message_list.append(message)
            self.display_messages()
            self.input_entry.delete(0, tk.END)

    def display_messages(self):
        self.message_text.config(state=tk.NORMAL)
        self.message_text.delete(1.0, tk.END)
        for message in self.message_list:
            self.message_text.insert(tk.END, f"{message.timestamp} - {message.sender}: {message.content}\n")
        self.message_text.config(state=tk.DISABLED)

root = tk.Tk()
chat_app = ChatApp(root)
root.mainloop()
