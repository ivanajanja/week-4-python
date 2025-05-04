# week-4-python

def read_and_write_with_error_handling():
    filename = input("Please enter the filename to read: ")

    try:
        # Attempt to open the file in read mode
        with open(filename, 'r') as source_file:
            content = source_file.read()
        
        # Modify the content (for example, convert it to uppercase)
        modified_content = content.upper()  # Example modification: Convert text to uppercase

        # Write the modified content to a new file
        with open('modified_file.txt', 'w') as new_file:
            new_file.write(modified_content)
        
        print(f"File '{filename}' successfully read and modified.")
        print("Modified content has been saved to 'modified_file.txt'.")
    
    except FileNotFoundError:
        print(f"Error: The file '{filename}' does not exist.")
    
    except PermissionError:
        print(f"Error: You do not have permission to read the file '{filename}'.")
    
    except IOError:
        print(f"Error: There was an issue reading or writing the file '{filename}'.")

# Run the function
read_and_write_with_error_handling()







