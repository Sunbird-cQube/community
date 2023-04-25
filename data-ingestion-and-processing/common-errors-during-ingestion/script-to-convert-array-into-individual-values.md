# Script to convert array into individual values

1. Install Python: If you haven't already, download and install the latest version of Python from the official website: [Download Python](https://www.python.org/downloads/)
2.  Install pandas: Open a terminal (Command Prompt on Windows or Terminal on macOS/Linux) and run the following command to install the pandas library, which the script depends on:

    `pip install pandas`
3. Save the script: Copy the provided Python script and save it as a `.py` file, for example, ConvertArray2MultipleRows.py
4. Prepare the input CSV file: Make sure your input CSV file is formatted correctly, with array values enclosed in double quotes. For example:

`name,age,colors`&#x20;

`Akash,25,"[red,blue,green]"`&#x20;

`Laskshmi,30,"[yellow,purple]"`

Save the CSV file, for example, as input.csv.

5. Run the script: In the terminal, navigate to the folder where you saved the `ConvertArray2MultipleRows.py` script using the `cd` command. For example:

`cd path/to/your/script/folder`

Replace `path/to/your/script/folder` with the actual path to the folder containing the script.

6. Execute the script by running the following command in the terminal:

`python ConvertArray2MultipleRows.py`

7. Provide the input and output file paths: The script will prompt you to enter the input CSV file path and the output CSV file path. Enter the paths and press Enter. For example:

`Please enter input CSV file name(along with path): input.csv`

Replace `input.csv` with the actual file paths if they are located in different folders.

8. Then the program starts conversion and displays the number of arrays converted as

`Total number of Arrays found and Converted = 49841`

9. Finally enter the Output file name where it has to be stored when prompted

`Please enter the output CSV file name: Output.csv`

10. Check the output: The script will process the input CSV file and create a new output CSV file with the specified file path. Open the output CSV file to verify the result.

Python Code (ConvertArray2MultipleRows.py)

```python
import ast
import pandas as pd
import re

# Global counter to know how many arrays are present
v_occurances = 0

#To check if a entry is an array
def is_array(value):
    return isinstance(value, (list, tuple)) or re.match(r'\[.*\]', str(value))

#Which columns are having arrays as values
def find_array_columns(df):
    array_columns = []
    for column in df.columns:
        if df[column].apply(is_array).any():
            array_columns.append(column)
    return array_columns

#Converting arrays to list
def convert_to_list(value):
    global v_occurances
    if is_array(value) and re.search(r'\[.*?,.*?\]',str(value)):
        v_occurances = v_occurances + 1
        ret = ast.literal_eval(value)
        return ret
    return [value]

#Splitting the arrays
def split_rows_by_array(df, array_columns):
    for column in array_columns:
        df[column] = df[column].apply(convert_to_list)
        df = df.explode(column).reset_index(drop=True)
    return df

def main():
    # Get the input CSV file path from the user
    file_path = input("Please enter input CSV file name(along with path): ")
    # Read the CSV file
    df = pd.read_csv(file_path,low_memory=False)
    # Find columns containing array values
    array_columns = find_array_columns(df)
    # Split the rows based on the array values in the identified columns
    new_df = split_rows_by_array(df, array_columns)
    print('Total number of Arrays Found and Converted = ',v_occurances)
    # Get the output CSV file path from the user
    output_file_path = input("Please enter the output CSV file name: ")

    # Save the resulting dataframe to the specified output CSV file
    new_df.to_csv(output_file_path, index=False)

if __name__ == '__main__':
    main()
```



\


