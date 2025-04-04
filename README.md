# week-4-Python
--------------------
def modify_file(input_filename, output_filename):
    try:
        # Open the input file for reading
        with open(input_filename, "r") as file:
            content = file.read()
        
        # Modify the content (convert to uppercase as an example)
        modified_content = content.upper()
        
        # Write the modified content to a new file
        with open(output_filename, "w") as file:
            file.write(modified_content)
        
        print(f"✅ File '{input_filename}' processed successfully!")
        print(f"🎉 Modified content saved to '{output_filename}'.")
    
    except FileNotFoundError:
        print(f"❌ Error: The file '{input_filename}' does not exist.")
    except PermissionError:
        print(f"❌ Error: Permission denied for '{input_filename}'.")
    except Exception as e:
        print(f"⚠️ Unexpected error: {e}")

# Ask the user for a filename
input_filename = input("Enter the filename to read: ")
output_filename = "modified_" + input_filename  # Create a new file name

modify_file(input_filename, output_filename)
