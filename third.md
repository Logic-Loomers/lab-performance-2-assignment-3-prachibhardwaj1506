Assume you oversee a small library and would like to develop a program that looks up books using their ISBNs. A list of books with their corresponding ISBN digits is in front of you. After the librarian inputs an ISBN, your software will look through the list to locate the relevant book.  The book's title and other details will be shown if the book is located. A notice stating that the book is not available in the library will appear if it cannot be located.
#include <iostream>
using namespace std;
class library
{
public:
    string author, title;
    double ISBN, searchisbn;
    void getdata();
    void displaydata();
    bool search(double);
};
void library ::getdata()
{
    cout << "Enter the ISBN of the book: ";
    cin >> ISBN;
    cout << "Enter the author of the book: ";
    cin >> author;
    cout << "Enter the title of the book: ";
    cin >> title;
}

bool library ::search(double x)
{
    return x == ISBN;
    
}

void library ::displaydata()
{
    cout << "ISBN : " << ISBN << endl;
    cout << "Title : " << title << endl;
    cout << "Author: " << author << endl;
}

int main()
{
	cout<<"Prachi Bhardwaj 2310997209";
	
    int number, size;
    
    cout << "Enter the number of books for details: ";
    cin >> size;
    library obj1[size];
    for (int i = 0; i < size; i++)
    {
        obj1[i].getdata();
    }

    cout << "Enter the ISBN of book to search: ";
    cin >> number;
    bool found = false;
    for (int i = 0; i < size; i++)
    {
        if (obj1[i].search(number))
        {
            cout << "Book found!";
            obj1[i].displaydata();
            found = true;
            break;
        }
    }
        if(!found)
        cout<<"Book not found!";
}
