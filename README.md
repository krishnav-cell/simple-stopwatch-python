# simple-stopwatch-python
a beginner friendly python stopwatch application that measures elapsed time it provides start,stop,reset,exit and display Elapsed Time
import time

start_time = None
elapsed_time = 0
running = False

while True:
    print("\n--- Simple Stopwatch ---")
    print("1. Start")
    print("2. Stop")
    print("3. Reset")
    print("4. Display Elapsed Time")
    print("5. Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        if running:
            print("Stopwatch is already running!")
        else:
            start_time = time.time() - elapsed_time
            running = True
            print("Stopwatch started.")

    elif choice == "2":
        if not running:
            print("Stopwatch has not been started!")
        else:
            elapsed_time = time.time() - start_time
            running = False
            print("Stopwatch stopped.")

    elif choice == "3":
        start_time = None
        elapsed_time = 0
        running = False
        print("Stopwatch reset.")

    elif choice == "4":
        if running:
            current_time = time.time() - start_time
        else:
            current_time = elapsed_time

        print(f"Elapsed Time: {current_time:.2f} seconds")

    elif choice == "5":
        print("Thank you!")
        break

    else:
        print("Invalid choice. Please try again.")
