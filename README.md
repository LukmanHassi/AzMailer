Here's a refined and more modern version of your GitHub README template, written in Markdown:

---

# AzMailer

**AzMailer** is a powerful software solution designed to automate document processes. Automation can be driven through command instructions, predefined profiles, or manual workflows, providing flexibility and efficiency in executing routine tasks.

For example, workflows can be automatically triggered when files are placed in a user-defined folder.

## Key Features

- **File Renaming**: Automatically rename files based on custom rules.
- **PDF Editing**: Merge PDFs, insert images, and add text seamlessly.
- **XRechnung Support**: Create and validate XRechnungen following the latest standards.
- **File Copying**: Automate file copying locally or to network locations.
- **Email Sending**: Send files via SMTP in HTML format with customizable email limits (e.g., per minute, hour, or day), supporting email lists or CSV imports.
- **Printing Functionality**: Send files to physical or virtual printers with options for color, tray selection, or number of copies.
- **FTP Upload**: Upload files automatically to FTP servers.
- **Event Triggering**: Trigger workflows based on schedules or custom events.

All actions in AzMailer are designed to be flexible, repeatable, and customizable to fit your specific needs, streamlining document processing tasks.

---

## Getting Started

### Prerequisites

- **AzMailer**: [Download AzMailer](https://download.obynt.com/azmailer/azmailer.zip)
- **.NET Runtime**: [Download .NET Runtime](https://dotnet.microsoft.com/en-us/download/dotnet/thank-you/runtime-8.0.8-windows-x64-installer)
- **WebView2 Runtime**: [Download WebView2 Runtime](https://msedge.sf.dl.delivery.mp.microsoft.com/filestreamingservice/files/05e60450-4888-45df-a717-74150a661bcd/Microsoft.WebView2.FixedVersionRuntime.128.0.2739.79.x64.cab)

### Installation

1. Install the **.NET Runtime** and **WebView2 Runtime**.
2. Extract the AzMailer `.zip` file and create a shortcut to `azmailer.exe` on your desktop.
3. Upon first launch, the software will automatically set up a database and default configurations in `%userprofile%\AppData\Local\azmailer\DB`. 
   - A workflow pool folder will also be created in `%userprofile%\AppData\Local\azmailer\pool\AzMailer`.
   - A PDF printer named **AzMailer** will be added. The printer's output will be saved to `%userprofile%\AppData\Local\azmailer\pool\AzMailer`.

### Multi-User Setup

For multi-user access from different computers sharing the same database:

1. Migrate the database to a shared folder.
2. Update the path in `path.json` found in the AzMailer installation folder (`\AzMailer\Environment\path.json`) to point to the new database location.

---

## Workflow Creation

Workflows in AzMailer automate the processing of files. You can define the sequence of operations to be performed when a file arrives in the pool folder.

### Steps to Create a Workflow

1. **Start the Workflow Profile Wizard**:
   - **Name**: The name of the workflow.
   - **Pool**: The folder where files will be processed.
   - **User & Password**: Required if the pool folder has restricted permissions.
   - **Search Pattern**: Define which files to process (e.g., `*` for all files, `*.pdf` for PDFs, `anyname.csv` for specific file types).
   - **Target**: Default profile applies to all users, or create user-specific profiles for multi-user environments.
   - **Note**: Add optional notes (no effect on functionality).
   - **Active**: The workflow will only run if activated (checked).

2. **Define Workflow Actions**: Actions are written in JSON format. For example:

   - To print a file:
     ```json
     [{
       "Print": {}
     }]
     ```
   - To copy and print a file:
     ```json
     [{
       "Copy": {},
       "Print": {}
     }]
     ```

   You can also embed these commands directly into a PDF or TXT file for execution when the file enters the workflow.

---

## Documentation

For detailed documentation, refer to our [Wiki](https://github.com/your-repo/wiki).

---

## License

AzMailer is licensed under [Your License](LICENSE).

---

This template modernizes the README with stylized sections and proper formatting, making it easier to follow and understand.
