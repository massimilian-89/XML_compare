
# XML Comparison Script

This Python script allows you to compare two XML files and identify differences between them. It also tracks the latest version of an XML file and updates it when a new version is provided.

## Features

- **Compare XML Files**: The script compares two XML files and generates a unified diff showing the differences.
- **Track Latest Version**: The script maintains a `latest_version.xml` file to keep track of the most recent XML file version.
- **Automatic Update**: After comparison, the script updates the `latest_version.xml` file with the new XML file if there are differences.

## Prerequisites

- Python 3.x
- Standard Python libraries:
  - `xml.etree.ElementTree`
  - `difflib`
  - `os`
  - `sys`
  - `shutil`

## Usage

1. **Command Line Arguments**: The script requires three command-line arguments:
    - `<file1>`: The first XML file to compare (typically the default or latest version).
    - `<file2>`: The second XML file to compare (the new or project file).
    - `<output_file>`: The output file where the differences will be saved.

   Example usage:
   ```bash
   python compare_xml.py file1.xml file2.xml output_diff.txt
   ```

2. **Latest Version Tracking**:
   - The script checks if a `latest_version.xml` file exists. If it doesn't, the script initializes it with the content of `<file1>`.
   - The script then compares the `latest_version.xml` with `<file2>`.
   - Any differences found are written to `<output_file>`.
   - Finally, the script updates the `latest_version.xml` with the contents of `<file2>` if there are changes.

## Example

To compare `default.xml` with `project.xml` and write the differences to `diff_output.txt`, you would run:

```bash
python compare_xml.py default.xml project.xml diff_output.txt
```

If this is the first time running the script, `latest_version.xml` will be created using `default.xml`. The script will then compare `latest_version.xml` with `project.xml`, write any differences to `diff_output.txt`, and update `latest_version.xml` with the contents of `project.xml`.

## Error Handling

- The script checks if the XML files exist before proceeding. If a file does not exist, it will print an error message and terminate.

## Contributing

Feel free to submit issues or pull requests if you find bugs or have improvements to suggest.


---

This README provides an overview of how to use the script, its features, and what to expect when running it.
