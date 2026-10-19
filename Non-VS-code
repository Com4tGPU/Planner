#include <iostream> 
#include <limits>
#include <cstring>
using namespace std;
/*
Difference between main-code and this:
main-code will work in VS only, but this
will work in about any other IDE.
Hence I needed two code files.
*/
int main() {
    char tasks[5][50];
    int count = 0;
    int choice = 0;

    while (choice != 4) {
        cout << "\n==== Tasks ====\n";
        cout << "1. View Tasks\n";
        cout << "2. Add Task\n";
        cout << "3. Remove Task\n";
        cout << "4. Exit\n";
        cout << "Pick an option: ";

        if (!(cin >> choice)) {
            cout << "Please enter a number.\n";
            cin.clear();
            cin.ignore(numeric_limits<streamsize>::max(), '\n');
            continue;
        }

        cin.ignore(numeric_limits<streamsize>::max(), '\n');

        if (choice == 1) {
            cout << "\n====== Current Tasks ======\n";

            if (count == 0) {
                cout << "No tasks yet, try adding some!\n";
            } else {
                for (int i = 0; i < count; ++i) {
                    cout << i + 1 << ". " << tasks[i] << '\n';
                }
            }
        } else if (choice == 2) {
            if (count == 5) {
                cout << "The task list is full.\n";
            } else {
                cout << "Enter a task (up to 49 characters): ";
                cin.getline(tasks[count], 50);

                if (cin.fail()) {
                    cin.clear();
                    cin.ignore(numeric_limits<streamsize>::max(), '\n');
                    cout << "Task was too long; please try again.\n";
                } else if (strlen(tasks[count]) > 0) {
                    ++count;
                    cout << "Task added.\n";
                } else {
                    cout << "Empty task not added.\n";
                }
            }
        } else if (choice == 3) {
            if (count == 0) {
                cout << "There are no tasks to remove.\n";
            } else {
                cout << "====== Current Tasks ======\n";
                for (int i = 0; i < count; ++i) {
                    cout << i + 1 << ". " << tasks[i] << '\n';
                }

                int taskNumber;
                cout << "Enter the number of the task to remove: ";

                if (!(cin >> taskNumber)) {
                    cout << "Please enter a number.\n";
                    cin.clear();
                    cin.ignore(numeric_limits<streamsize>::max(), '\n');
                } else {
                    cin.ignore(numeric_limits<streamsize>::max(), '\n');

                    if (taskNumber < 1 || taskNumber > count) {
                        cout << "That task number is not in the list.\n";
                    } else {
                        int index = taskNumber - 1;

                        for (int i = index; i < count - 1; ++i) {
                            strcpy(tasks[i], tasks[i + 1]);
                        }

                        --count;
                        cout << "Task removed.\n";
                    }
                }
            }
        } else if (choice == 4) {
            cout << "Goodbye!\n";
        } else {
            cout << "Invalid option. Choose 1, 2, 3, or 4.\n";
        }
    }

    return 0;
}
