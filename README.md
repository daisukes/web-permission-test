# Web Permission Test

A simple web application to test browser video and audio permission requests using native HTML and JavaScript.

## Features

- **Automatic Permission Request**: Requests both camera and microphone permissions automatically on page load
- **Native Implementation**: Built with vanilla HTML, CSS, and JavaScript (no frameworks or libraries)
- **Visual Feedback**: Clear status indicators showing permission states (granted, denied, pending)
- **Live Preview**: Displays live video feed when permissions are granted
- **Error Handling**: Comprehensive error messages for different scenarios

## How It Works

When you open the page, the browser will automatically prompt you to allow access to your camera and microphone. The page uses the `navigator.mediaDevices.getUserMedia()` API to request permissions.

## Usage

### Online (GitHub Pages)

Visit the live demo: [https://daisukes.github.io/web-permission-test/](https://daisukes.github.io/web-permission-test/)

### Local Testing

1. Clone this repository:
   ```bash
   git clone https://github.com/daisukes/web-permission-test.git
   cd web-permission-test
   ```

2. Open `index.html` in a modern web browser:
   - **Note**: For security reasons, `getUserMedia()` requires HTTPS or localhost
   - Open directly: `file:///path/to/index.html` (may have restrictions)
   - Use a local server (recommended):
     ```bash
     # Python 3
     python -m http.server 8000
     
     # Python 2
     python -m SimpleHTTPServer 8000
     
     # Node.js (with npx)
     npx http-server
     ```
   - Then navigate to `http://localhost:8000`

## Browser Compatibility

This application uses the `getUserMedia()` API, which is supported by:
- Chrome 53+
- Firefox 36+
- Safari 11+
- Edge 12+
- Opera 40+

**Note**: HTTPS is required for permission requests (except on localhost).

## Permission States

- **Granted**: Access to camera and microphone is allowed
- **Denied**: User denied permission or browser blocked access
- **Requesting...**: Waiting for user response to permission prompt
- **Not Found**: No camera or microphone device detected
- **Error**: Other errors (device in use, constraints not satisfied, etc.)

## GitHub Pages Setup

To enable GitHub Pages for this repository:

1. Go to repository Settings
2. Navigate to "Pages" section
3. Under "Source", select the branch (e.g., `main`)
4. Click "Save"
5. The site will be available at `https://daisukes.github.io/web-permission-test/`

## Technical Details

- **getUserMedia API**: Used to request access to media input devices
- **MediaStream**: Represents the stream of media content
- **Error Handling**: Handles various error types (NotAllowedError, NotFoundError, NotReadableError, etc.)
- **Cleanup**: Properly stops media tracks when page is closed

## Security Notes

- Modern browsers require HTTPS for accessing camera and microphone (localhost is an exception)
- Users must explicitly grant permission for each origin
- Permissions can be revoked at any time through browser settings

## License

This project is open source and available under the MIT License.