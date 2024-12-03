#!/bin/bash

# File path to check
file="/home/ubuntu/my-scripts/mock-file.sh"

# Check if the file exists
if [ ! -f "$file" ]; then
    echo "File $file does not exist."
    read -p "Do you want to create it? (y/n): " user_input

    if [[ "$user_input" == "y" || "$user_input" == "Y" ]]; then
        touch "$file"  # Create the file
        echo "File $file created."
    else
        echo "File creation aborted."
    fi
else
    echo "File $file already exists."
fi
