# DSA-LAB 1:
****code****
#include<iostream>
using namespace std;
int main() {
    int arr[8] = {10, 20, 30, 40, 50, 60, 70, 80};
    cout << "Original array: ";
    for (int i = 0; i < 8; i++) {
        cout << arr[i] << " ";
    }
    cout << endl;
    for (int i = 0; i < 7; i++) {
        arr[i] = arr[i + 1];
    }
    arr[6] = 0;
    cout << "Array after deleting the first and last elements: ";
    for (int i = 0; i < 7; i++) {
        cout << arr[i] << " ";
    }
    cout << endl;
    return 0;
}
  *****code 2******
#include <iostream>
using namespace std;
int main() {
    int arr[8] = {10, 20, 30, 40, 50, 60, 70, 80};
    int index, newValue;
    cout << "Original array: ";
    for (int i = 0; i < 8; i++) {
        cout << arr[i] << " ";
    }
    cout << endl;
    cout << "Enter the index : ";
    cin >> index;
    if (index >= 0 || index < 8) {
        cout << "Enter the new value: ";
        cin >> newValue;
        arr[index] = newValue;
        cout << "Updated array: ";
        for (int i = 0; i < 8; i++) {
            cout << arr[i] << " ";
        }
        cout << endl;
    } else {
        cout << "Invalid index." << endl;
    }
    return 0;
}
 *****code 3*****  
#include <iostream>
using namespace std;
int main() {
    int arr[8] = {10, 20, 30, 40, 50, 60, 70, 80};
    cout << "Original array: ";
    for (int i = 0; i < 8; i++) {
        cout << arr[i] << " " << endl;
    }
    cout << "enter elements in reverse order:";
    for (int i = 7; i > 0; i--) {
        cout << arr[i] << " " << endl;
    }
    return 0;
}
*****LAB 2*****
                                                                                               ****code 1****
#include <iostream>
using namespace std;
int main()
{
    int arr[5] = {10, 20, 30, 40, 50};
    int *ptr = arr;
    for (int i = 0; i < 5; ++i)
{
        cout << "Element" << i+1 <<" : " << *ptr << endl;
        ptr++;
    }
    return 0;
}
                                                                                             *****code 2*****
#include <iostream>
using namespace std;
void change(int *a, int *b) {
    int temp = *a;  
    *a = *b;        
    *b = temp;      
}
int main() {
    int x = 5, y = 10;
    cout << "Before changing x: "<<endl;
cout<<  x << " y = " << y << endl;
    change(&x, &y);
    cout << "After changing x:"<<endl;
cout << x << " y = " << y << endl;
    return 0;
}                                                                                               

                                                                                    
                                                                                       *****LAB 3*****                                                                                         
 ***code:***      
 #include <iostream>
using namespace std;
int main() {
    int n;
    cout << "Enter the size of the array: ";
    cin >> n;
    int* arr = new int[n];
    cout << "Enter " << n << " elements: ";
    for (int i = 0; i < n ; i++) {
        cin >> arr[i];
}
 for (int i = 0; i < n ; i++)
 {
      int even=0, odd=0;
        if (arr[i] % 2 == 0)
            even++;
        else
 odd++;
        }
    }
    cout << "even numbers: " << even << endl;
    cout << "odd numbers: " << odd << endl;
    delete[] arr;
    return 0;
}
                                                                                          ******Code 02:*****
#include <iostream>
using namespace std;
int main()
 {
    int n;
    cout << "Enter number of elements: ";
    cin >> n;
    int* arr = new int[n];
    cout << "Enter numbers: ";
     for (int i = 0; i < n ; i++)
{
    cin >> arr[i];
}
    int max = arr[0], min = arr[0];
    for (int i = 1; i < n; i++) {
        cin >> arr[i];
        if (arr[i] > max) max = arr[i];
 if (arr[i] < min) min = arr[i];
    }
    cout << "Maximum: " << max  << endl;
    cout << "Minimum: " << max  << endl;
    delete[] arr;
    return 0;
}
                                                                                          ***LAB NO 4***
******code insert node at the end of linked list****** :
*****code*****
#include <iostream>
using namespace std;
class Node {
public:
    int data;
    Node* next;

    Node(int value) {
        data = value;
        next = NULL;
    }
};
class LinkedList {
public:
    Node* head;
    LinkedList() {
        head = NULL;
    }
    void insertAtEnd(int value) {
        Node* newNode = new Node(value);
        if (head == NULL) {
            head = newNode;
            return;
        }
        Node* temp = head;
        while (temp->next != NULL) {
            temp = temp->next; 
        }
        temp->next = newNode;
    }

    void display() {
        Node* temp = head;
        while (temp != NULL) {
            cout << temp->data << " -> ";
            temp = temp->next;
        }
        cout << "NULL" << endl;
    }
};
int main() {
    LinkedList list;
    list.insertAtEnd(10);
    list.insertAtEnd(20);code
    list.insertAtEnd(30);
    cout << "Linked List: ";
    list.display();
    return 0;
}
*****code to delete node at the start,at specific psition and at the end of linked list*****
****code***
#include <iostream>
using namespace std;
struct Node {
    int data;
    Node* next;
    Node(int value) { 
        data = value;
        next = NULL;
    }
};
class LinkedList {
public:
    Node* head;

    LinkedList() { 
        head = NULL;
    }
    void insertAtEnd(int value) {
        Node* newNode = new Node(value);
        if (head == NULL) { 
            head = newNode;
            return;
        }
        Node* temp = head;
        while (temp->next != NULL) { 
            temp = temp->next;
        }
        temp->next = newNode;
    }
    void deleteAtStart() {
        if (head == NULL) {
            cout << "List is empty!\n";
            return;
        }
        Node* temp = head;
        head = head->next;
        delete temp;
    }
    void deleteAtPosition(int position) {
        if (head == NULL) {
            cout << "List is empty!\n";
            return;
        }
        if (position == 1) { 
            deleteAtStart();
            return;
        }
        Node* temp = head;
        Node* prev = NULL;
        int count = 1;
        while (temp != NULL && count < position) {
            prev = temp;
            temp = temp->next;
            count++;
        }
        if (temp == NULL) {
            cout << "Position out of range!\n";
            return;
        }
        prev->next = temp->next;
        delete temp;
    }
    void deleteAtEnd() {
        if (head == NULL) {
            cout << "List is empty!\n";
            return;
        }
        if (head->next == NULL) { 
            delete head;
            head = NULL;
            return;
        }
        Node* temp = head;
        while (temp->next->next != NULL) { 
            temp = temp->next;
        }
        delete temp->next;
        temp->next = NULL;
    }
    void display() {
        Node* temp = head;
        while (temp != NULL) {
            cout << temp->data << " -> ";
            temp = temp->next;
        }
        cout << "NULL" << endl;
    }
};
int main() {
    LinkedList list;
    list.insertAtEnd(10);
    list.insertAtEnd(20);
    list.insertAtEnd(30);
    list.insertAtEnd(40);
    list.insertAtEnd(50);
    cout << "Original Linked List: ";
    list.display();
    list.deleteAtStart();
    cout << "After deleting first node: ";
    list.display();
    list.deleteAtPosition(3);
    cout << "After deleting node at position 3: ";
    list.display();
    list.deleteAtEnd();
    cout << "After deleting last node: ";
    list.display();
    return 0;
}
                                                                                                 ********lab 5********
                                                                               ****code:to delete node from doubly linked list:*****                                     

#include <iostream>
using namespace std;
struct Node {
    int data;
    Node* next;
    Node* prev;
};
void print_data(Node* head) {
    if (head == NULL) {
        cout << "Linked list is empty" << endl;
        return;
    }
    Node* ptr = head;
    while (ptr != NULL) {
        cout << ptr->data << " ";
        ptr = ptr->next;
    }
    cout << endl;
}
Node* at_start(Node* head) {
    if (head == NULL) {
        cout << "The list is empty." << endl;
        return NULL;
    }
    Node* temp = head;
    head = head->next;  
    if (head != NULL) {
        head->prev = NULL;  // Set the previous pointer of the new head to NULL
    }
    delete temp;  // Free the memory of the old head node
    return head;   // Return the new head
}
int main() {
    // Dynamically allocating nodes for linked list
    Node* node1 = new Node();
    Node* node2 = new Node();
    Node* node3 = new Node();
    cout << "Enter value for Node 1: ";
    cin >> node1->data;
    node1->prev = NULL;
    node1->next = node2;
    cout << "Enter value for Node 2: ";
    cin >> node2->data;
    node2->prev = node1;
    node2->next = node3;
    cout << "Enter value for Node 3: ";
    cin >> node3->data;
    node3->prev = node2;
    node3->next = NULL;
    Node* head = node1; 
    head = at_start(head);
    cout << "Linked list after deleting first node: ";
    print_data(head);
    while (head != NULL) {
        Node* temp = head;
        head = head->next;
        delete temp;  // Free each node
    }
    return 0;
}
                                                                                                    ******code 2******
                                                                           ****code: after deleting last node at doubly linked list:****

   #include <iostream>
using namespace std;
struct Node {
    int data;
    Node* next;
    Node* prev;
};
void print_data(Node* head) {
    if (head == NULL) {
        cout << "Linked list is empty" << endl;
        return;
    }
    Node* ptr = head;
    while (ptr != NULL) {
        cout << ptr->data << " ";
        ptr = ptr->next;
    }
    cout << endl;
}
Node* at_end(Node* head) {
    if (head == NULL) {
        cout << " empty." << endl;
        return NULL;
    }
    Node* temp = head;

    if (head->next == NULL) {
        delete head;
        return NULL;
    }
    while (temp->next != NULL) {
        temp = temp->next;
    }
    temp->prev->next = NULL;

    delete temp;
    return head;
}
int main() {
    Node node1, node2, node3, node4;
    cout << "Enter value for Node 1: ";
    cin >> node1.data;
    node1.prev = NULL;
    node1.next = &node2;
    cout << "Enter value for Node 2: ";
    cin >> node2.data;
    node2.prev = &node1;
    node2.next = &node3;
    cout << "Enter value for Node 3: ";
    cin >> node3.data;
    node3.prev = &node2;
    node3.next = &node4;
    cout << "Enter value for Node 4: ";
    cin >> node4.data;
    node4.prev = &node3;
    node4.next = NULL;
    Node* head = &node1;
    head = at_end(head);
    cout << "Linked list after deleting  last : ";
    print_data(head);
    return 0;
}
                                                                                                 *****code 3:****   
                                                                     ****code:deleting node at the specific position in doubly linked list****
#include <iostream>
using namespace std;
struct Node {
    int data;
    Node* next;
    Node* prev;
};
void print_data(Node* head) {
    Node* temp = head;
    while (temp != NULL) {
        cout << temp->data << " ";
        temp = temp->next;
    }
    cout << endl;
}
Node* at_position(Node* head, int position) {
    if (head == NULL) {
        cout << "The list is empty, nothing to delete." << endl;
        return NULL;
    }
    Node* temp = head;
    int count = 0;
    while (temp != NULL) {
        count++;
        temp = temp->next;
    }
    if (position < 1 || position > count) {
        cout << "Invalid position!" << endl;
        return head;
    }
    temp = head;
    if (position == 1) {
        head = head->next;  
        if (head != NULL) {
            head->prev = NULL;
        }
        delete temp;
        return head;
    }
    for (int i = 1; temp != NULL && i < position; i++) {
        temp = temp->next;
    }
    if (temp->prev != NULL) {
        temp->prev->next = temp->next;
    }
    if (temp->next != NULL) {
        temp->next->prev = temp->prev;
    }
    delete temp;  
    return head;
}
int main() {
    Node node1, node2, node3, node4;
    node1.data = 60; 
	node1.prev = NULL;
	 node1.next = &node2;
    node2.data = 70; 
	node2.prev = &node1; 
	node2.next = &node3;
    node3.data = 80;
	 node3.prev = &node2;
	  node3.next = &node4;
    node4.data = 90; 
	node4.prev = &node3; 
	node4.next = NULL;
    Node* head = &node1;
    cout << "Original linked list: ";
    print_data(head);
    int position;
    cout << "Enter position to delete: ";
    cin >> position;
    head = at_position(head, position);
    cout << "Linked list after deletion: ";
    print_data(head);
    return 0;
}
                                                                                                          ****lab 6*****
                                                                                                ****circular linked list:****
code:
#include <iostream>
using namespace std;
struct Node {
    int data;
    Node* next;
    Node* prev;
};
Node* head = NULL;
void insertAtStart(int value) {
    Node* newNode = new Node();
    newNode->data = value;
    if (head == NULL) {
        newNode->next = newNode;
        newNode->prev = newNode;
        head = newNode;
    } else {
        Node* tail = head->prev;

        newNode->next = head;
        newNode->prev = tail;

        tail->next = newNode;
        head->prev = newNode;
        head = newNode;
    }
}
void display() {
    if (head == NULL) {
        cout << "List is empty." << endl;
        return;
    }
    Node* temp = head;
    cout << "Circular Doubly Linked List: "<<endl;
    do {
        cout << temp->data << " ";
        temp = temp->next;
    } while (temp != head);
    cout << endl;
}
int main() {
    insertAtStart(40);
    insertAtStart(50);
    insertAtStart(60);
    display(); 
    return 0;
}
                                                                                              *****code 2:inserion at specific position*:#include <iostream>
using namespace std;
struct Node {
    int data;
    Node* next;
    Node* prev;
};
Node* head = NULL;
void insertAtPosition(int value, int position) {
    Node* newNode = new Node();
    newNode->data = value;
    if (head == NULL && position == 1) {
        newNode->next = newNode;
        newNode->prev = newNode;
        head = newNode;
        return;
    }
    if (position == 1) {
        Node* tail = head->prev;
        newNode->next = head;
        newNode->prev = tail;
        tail->next = newNode;
        head->prev = newNode;
        head = newNode;
        return;
    }
    Node* temp = head;
    int count = 1;

    while (count < position - 1 && temp->next != head) {
        temp = temp->next;
        count++;
    }
    Node* nextNode = temp->next;
    newNode->next = nextNode;
    newNode->prev = temp;
    temp->next = newNode;
    nextNode->prev = newNode;
}

void display() {
    if (head == NULL) {
        cout << "List is empty." << endl;
        return;
    }

    Node* temp = head;
    cout << "Circular Doubly Linked List: "<<endl;
    do {
        cout << temp->data << " ";
        temp = temp->next;
    } while (temp != head);
    cout << endl;
}
int main() {
    insertAtPosition(40, 1); 
    insertAtPosition(50, 2);
    insertAtPosition(60, 1);
    insertAtPosition(70, 3); 
    display(); 

    return 0;
}
                                                                                        *****code 3: insertion at end*****
#include <iostream>
using namespace std;
struct Node {
    int data;
    Node* next;
    Node* prev;
};
Node* head = NULL;
void insertAtEnd(int value) {
    Node* newNode = new Node();
    newNode->data = value;
    if (head == NULL) {
        newNode->next = newNode;
        newNode->prev = newNode;
        head = newNode;
    } else {
        Node* tail = head->prev;
        newNode->next = head;
        newNode->prev = tail;
        tail->next = newNode;
        head->prev = newNode;
    }
}
void display() {
    if (head == NULL) {
        cout << "List is empty." << endl;
        return;
    }
    Node* temp = head;
    cout << "Circular Doubly Linked List: ";
    do {
        cout << temp->data << " ";
        temp = temp->next;
    } while (temp != head);
    cout << endl;
}
int main() {
    insertAtEnd(40);
    insertAtEnd(50);
    insertAtEnd(60);
    insertAtEnd(70);
    display();  
    return 0;
}
                                                                                                    *****LAB 7******
                                                                                            **************code:1*************
#include <iostream>
using namespace std;
class PlateStack {
public:
    int stack[3];  
    int top;       
    PlateStack() {  
        top = -1;  
    }
    void addPlate(int plate) {
        if (top < 2) { 
            stack[++top] = plate;
            cout << "Plate " << plate << " added to the stack." << endl;
        } else {
            cout << "Stack is full! Cannot add more plates." << endl;
        }
    }
    void removePlate() {
        if (top >= 0) {  
            cout << "Plate " << stack[top--] << " removed from the stack." << endl;
        } else {
            cout << "Stack is empty! No plates to remove." << endl;
        }
    }
    void checkTopPlate() {
        if (top >= 0) {
            cout << "The top plate is plate " << stack[top] << "." << endl;
        } else {
            cout << "Stack is empty! No plates on top." << endl;
        }
    }
};
int main() {
    PlateStack stack;
    stack.addPlate(1);  
    stack.addPlate(2);  
    stack.addPlate(3);  
    stack.addPlate(4);  
    stack.checkTopPlate();  
    stack.removePlate();  
    stack.removePlate();  
    stack.removePlate();  
    stack.removePlate();  
    stack.checkTopPlate();  
    return 0;
}
                                                                                                *****code 2*****
#include <iostream>
#include <string>
using namespace std;
struct Node {
    string item;   
    Node* next;    
};
class GroceryList {
public:
    Node* head; 
    GroceryList() {
        head = nullptr;
    }
    void addItem(const string& newItem) {
        Node* newNode = new Node();
        newNode->item = newItem;
        newNode->next = head;  
        head = newNode;        
        cout << newItem << " added to the list." << endl;
    }
    void removeItem(const string& itemToRemove) {
        Node* current = head;
        Node* previous = nullptr;
        while (current != nullptr) {
            if (current->item == itemToRemove) {
                if (previous == nullptr) {
                    head = current->next;
                } else {
                    previous->next = current->next;
                }
                delete current;  
                cout << itemToRemove << " removed from the list." << endl;
                return;
            }
            previous = current;
            current = current->next;
        }
        cout << itemToRemove << " not found in the list." << endl;
    }

    void displayList() {
        if (head == nullptr) {
            cout << "The list is empty." << endl;
            return;
        }  
        Node* current = head;
        cout << "Grocery List:" << endl;
        while (current != nullptr) {
            cout << "- " << current->item << endl;
            current = current->next;
        }
    }
};
int main() {
    GroceryList list;
    list.addItem("Milk");
    list.addItem("Bread");
    list.addItem("Eggs");
    list.addItem("Butter");
    list.displayList();  
    list.removeItem("Bread");  
    list.removeItem("Cheese"); 
    list.displayList();  
    return 0;
}
