# File Organizer using AI

A Python script to intelligently organize a large number of files based on file type, content, and name. The script utilizes AI techniques, including natural language processing, to categorize files into appropriate folders. It includes a progress bar with percentage completed and estimated time remaining (ETA).

## Features

- **AI-Powered Categorization**: Uses pre-trained NLP models to classify files based on content.
- **File Type and Name Analysis**: Categorizes files using file extensions and keywords in file names.
- **Progress Bar with ETA**: Displays a progress bar indicating the percentage completed and estimated time remaining.
- **Parallel Processing**: Processes files in parallel to improve performance on multi-core CPUs.
- **Error Handling**: Robust exception handling to continue processing even if some files cause errors.
- **Duplicate Handling**: Automatically handles duplicate file names when moving files.
- **Customizable**: Easily adjust settings like maximum file size for content analysis and the number of worker threads.

## Prerequisites

- Python 3.x
- Required Python libraries:
  - `transformers`
  - `torch`
  - `PyPDF2`
  - `docx2txt`
  - `tqdm`

## Installation

1. **Clone the Repository**

   ```bash
   git clone https://github.com/yourusername/file-organizer-ai.git
   cd file-organizer-ai
   ```

2. **Install Dependencies**

   Install the required Python libraries:

   ```bash
   pip install -r requirements.txt
   ```

   *Alternatively, install them individually:*

   ```bash
   pip install transformers torch PyPDF2 docx2txt tqdm
   ```

## Usage

1. **Set the Base Directory**

   Edit the script to set the `base_directory` variable to the path containing your files:

   ```python
   base_directory = "/path/to/your/folder"  # Replace with your directory path
   ```

2. **Adjust Settings (Optional)**

   - **`MAX_WORKERS`**: Number of threads for parallel processing.
   - **`MAX_FILE_SIZE`**: Maximum file size (in bytes) for content analysis.
   - **`MAX_TEXT_LENGTH`**: Maximum number of characters from the file content to use for classification.

3. **Run the Script**

   ```bash
   python organize_files_advanced.py
   ```

4. **Monitor Progress**

   The script will display a progress bar showing the percentage completed and the estimated time remaining.

## Example

Suppose you have a folder with mixed files:

- `Assignment1.pdf`
- `BankStatement.pdf`
- `VacationPhoto.jpg`
- `Resume.docx`
- `Installer.exe`

After running the script, the files will be organized into:

- `Academic/Assignment1.pdf`
- `Financial/BankStatement.pdf`
- `Images/VacationPhoto.jpg`
- `Personal/Resume.docx`
- `Software/Installer.exe`

## Customization

- **Candidate Labels**: Modify the `candidate_labels` list to add or remove categories.
- **Name Keywords**: Update the `name_keywords` dictionary with keywords relevant to your files.
- **File Type Groups**: Adjust the file extensions in `document_types`, `media_types`, etc.

## Performance Tips

- **Adjust `MAX_WORKERS`**: Increase or decrease based on your CPU capabilities.
- **Limit Content Analysis**: Setting `MAX_FILE_SIZE` appropriately can significantly reduce processing time.
- **Use a Smaller Model**: The script uses a smaller model (`distilbert-base-uncased-mnli`) for faster processing on CPUs.

## Error Handling

- The script includes exception handling to skip files that cause errors without stopping the entire process.
- Errors are printed to the console. You can redirect them to a log file if desired.

## Dependencies

- **transformers**: For NLP models.
- **torch**: Required by transformers.
- **PyPDF2**: To extract text from PDF files.
- **docx2txt**: To extract text from DOCX files.
- **tqdm**: For the progress bar.

## License

This project is licensed under the Apache License.

## Contributing

Contributions are welcome! Please submit a pull request or open an issue to discuss any changes.

## Disclaimer

- **Backup Your Data**: It's recommended to back up your files before running the script.
- **Test First**: Try the script on a small subset of files to ensure it works as expected.

## Contact

For questions or support, please open an issue on the GitHub repository.
