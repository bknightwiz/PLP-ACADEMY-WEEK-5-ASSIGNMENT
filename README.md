# PLP-ACADEMY-WEEK-5-ASSIGNMENT

def read_and_modify_file():
    # Ask user for a filename
    filename = input("Enter the name of the file to read: ")

    try:
        # Try to open the input file for reading
        with open(filename, 'r') as infile:
            lines = infile.readlines()

        # Modify the content — reverse each line
        modified_lines = [line[::-1] for line in lines]

        # Create a new output filename
        output_filename = f"modified_{filename}"

        # Write the modified content to the new file
        with open(output_filename, 'w') as outfile:
            outfile.writelines(modified_lines)

        print(f"✅ Success: '{output_filename}' has been created with modified content.")

    except FileNotFoundError:
        print(f"❌ Error: The file '{filename}' was not found.")
    except IOError:
        print(f"❌ Error: Could not read from the file '{filename}'.")
    except Exception as e:
        print(f"❌ An unexpected error occurred: {e}")

# Run the function
read_and_modify_file()
