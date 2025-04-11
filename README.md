  # BurpSuite Request Filter Plugin

A powerful BurpSuite extension that helps security professionals and developers filter, analyze, and export HTTP requests captured during proxy sessions.

## Features

- **Custom Tab Integration**: Adds a dedicated "Request Filter" tab to BurpSuite
- **Right-Click Integration**: Send requests from HTTP history to the plugin with right-click
- **Multiple Filter Options**:
  - HTTP method filtering (GET, POST, PUT, DELETE, etc.)
  - File type filtering (js, gif, jpg, png, css)
  - Multiple URI pattern filters with OR logic
- **Interactive UI**:
  - Fully resizable split panes between request list and details
  - Request and response viewer panels
  - Navigation buttons for browsing through requests
- **Export Functionality**:
  - Save individual requests as HTTP files
  - Save all filtered requests to a directory at once
  - Automatic filename generation based on URI

## Installation

1. Open BurpSuite
2. Go to Extender > Extensions
3. Click "Add"
4. Set Extension Type to "Python"
5. Select the `burp_request_filter.py` file
6. Click "Next" to load the extension

## Usage Examples

### Example 1: Filtering API Requests

Imagine you're testing a web application and want to focus only on API requests:

1. Browse the application through Burp Proxy to capture traffic
2. In HTTP history, select interesting requests (or all requests)
3. Right-click and select "Send to Request Filter"
4. In the Request Filter tab:
   - Check only POST and GET methods
   - Uncheck the "Include" box for file types (to exclude them)
   - Add "/api/" in a URI filter
5. Click "Apply Filter"

The plugin will now show only API requests made using POST or GET methods, and you can easily navigate through them.

### Example 2: Analyzing Authentication Flow

To analyze the authentication flow of an application:

1. Clear your browser cookies and capture a complete login sequence
2. Send all requests to the Request Filter tab
3. Add URI filters for "/login", "/auth", "/token", etc.
4. Sort by timestamp (ID column)
5. Use the navigation buttons to step through each request
6. Examine headers, cookies, and request/response bodies

This makes it much easier to understand the authentication mechanism and identify potential vulnerabilities.

### Example 3: Exporting Requests for Documentation

When preparing documentation or reports:

1. Filter the requests to include only those relevant to the feature being documented
2. Click "Save All Requests to Folder"
3. Select a destination directory
4. The plugin will save each request as a separate .http file named after the last part of the URI

These files can be included in your documentation or used for automated testing.

### Example 4: Focusing on Static Resources

To analyze static resources of a specific type:

1. Check the "Include" box in file types section
2. Select only the file type you're interested in (e.g., only "js")
3. Apply the filter
4. All JavaScript files loaded by the application will be displayed

This is useful for inspecting frontend code, finding hardcoded secrets, etc.

## Tips & Tricks

- **Multiple URI Filters**: Add multiple patterns by clicking the "+" button. Requests matching ANY pattern will be shown.
- **Resizing Panels**: Drag the dividers between panels to adjust the layout based on your needs.
- **Navigating Requests**: Use the "Previous Request" and "Next Request" buttons instead of clicking in the table.
- **File Type Filtering**: Use the "Include" checkbox to toggle between including or excluding the selected file types.
- **Batch Export**: Use "Save All Requests to Folder" to quickly export all filtered requests for offline analysis.

## Troubleshooting

- If the plugin doesn't load, ensure you have Jython correctly configured in BurpSuite
- If no requests appear after sending them to the plugin, check your filter settings
- If you encounter errors when saving files, verify you have write permissions to the destination folder

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
