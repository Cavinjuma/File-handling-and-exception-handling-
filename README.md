# File-handling-and-exception-handling-

# a program that reads a file and writes a modified version to a new file
# Ask the user for a filename and handle errors if it doesn’t exist or can’t be read

def modify_content(content):
    # Example modification: convert to uppercase
    return content.upper()

def main():
    try:
        # Ask user for the input filename
        input_filename = input("Enter the name of the file to read: ")

        # Read the file
        with open(input_filename, 'r') as infile:
            content = infile.read()

        # Modify the content
        modified_content = modify_content(content)

        # Write to a new file
        output_filename = "modified_" + input_filename
        with open(output_filename, 'w') as outfile:
            outfile.write(modified_content)

        print(f"Modified content written to '{output_filename}' successfully.")

    except FileNotFoundError:
        print("Error: File not found.")
    except IOError:
        print("Error: Could not read or write the file.")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")

if __name__ == "__main__":
    main()
