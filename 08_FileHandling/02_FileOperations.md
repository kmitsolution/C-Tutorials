`ofstream` is a class in C++ provided by the Standard Template Library (STL) to perform output operations on files. The `ofstream` class is derived from the `ostream` class and is specifically designed for writing to files.

Here's a basic example of how you can use `ofstream` to write data to a file:

```cpp
#include <iostream>
#include <fstream>

int main() {
    // Open a file for writing (creates if not exists, truncates if exists)
    std::ofstream outputFile("example.txt");

    // Check if the file was opened successfully
    if (!outputFile.is_open()) {
        std::cerr << "Error opening file for writing!" << std::endl;
        return 1; // Return with error code
    }

    // Write data to the file
    outputFile << "Hello, world!\n";
    outputFile << "This is a line written to the file.\n";

    // Close the file
    outputFile.close();

    // Inform the user that writing is complete
    std::cout << "Data has been written to the file successfully." << std::endl;

    return 0;
}
```

In this example:

- We include the necessary headers: `<iostream>` for input/output streams and `<fstream>` for file streams.
- We create an `ofstream` object named `outputFile` and open the file "example.txt" for writing.
- We check if the file was opened successfully.
- We write data to the file using the `<<` operator, just like writing to `cout`.
- Finally, we close the file using the `close()` method.

Remember, if the file already exists, opening it with `ofstream` in the mode provided by default (`ios::out`) will truncate it, i.e., remove all its contents. If you want to append data to the end of an existing file, you should open it with `ios::app` flag (using `ofstream::app` constructor) instead of `ios::out`.

```cpp
std::ofstream outputFile("example.txt", std::ios::app); // Open in append mode
```

Always remember to close the file using `close()` when you're done with it.

### Example to search a string in a file
To search for a string in a file in C++, you can read the file line by line and search for the desired string in each line. Here's a simple example:

```cpp
#include <iostream>
#include <fstream>
#include <string>

int main() {
    std::ifstream inputFile("example.txt");

    // Check if the file was opened successfully
    if (!inputFile.is_open()) {
        std::cerr << "Error opening file!" << std::endl;
        return 1; // Return with error code
    }

    std::string searchString = "desired_string";
    std::string line;
    int lineNumber = 0;
    bool found = false;

    // Read the file line by line
    while (std::getline(inputFile, line)) {
        lineNumber++;
        // Search for the string in the current line
        if (line.find(searchString) != std::string::npos) {
            found = true;
            std::cout << "String found at line " << lineNumber << ": " << line << std::endl;
            // If you want to find multiple occurrences, remove the break statement
            break;
        }
    }

    // If the string was not found
    if (!found) {
        std::cout << "String '" << searchString << "' not found in the file." << std::endl;
    }

    // Close the file
    inputFile.close();

    return 0;
}
```

In this example:

- We open the file "example.txt" for reading.
- We define the string we want to search for (`searchString`).
- We read the file line by line using `std::getline`.
- For each line, we check if the desired string is present using `find` method of the `std::string` class.
- If the string is found, we print the line number and the line itself.
- If the string is not found, we print a message indicating that it wasn't found.
- Finally, we close the file.

You can adjust this code as needed, depending on whether you want to find all occurrences or just the first one, and whether you want case-sensitive or case-insensitive search, among other considerations.
