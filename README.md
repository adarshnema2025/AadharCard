# Aadhar Card Information Extractor

A React-based web application that uses Google's Gemini AI to extract information from Aadhar card images. This application provides a user-friendly interface to upload Aadhar card images and automatically extract key information such as name, date of birth, Aadhar number, gender, and address.

## 🚀 Features

- **AI-Powered Extraction**: Uses Google Gemini 1.5 Flash model for accurate information extraction
- **Secure Processing**: Aadhar numbers are automatically masked for privacy
- **Image Preview**: Preview uploaded images before processing
- **Responsive Design**: Works seamlessly on desktop and mobile devices
- **File Validation**: Supports JPG, JPEG, PNG formats with size limits
- **Age Calculation**: Automatically calculates age from date of birth
- **Error Handling**: Comprehensive error messages and validation
- **Real-time Processing**: Fast extraction with loading indicators

## 🛠️ Technologies Used

- **React.js** - Frontend framework
- **Tailwind CSS** - Styling and responsive design
- **Lucide React** - Beautiful icons
- **Google Gemini AI** - Image processing and text extraction
- **JavaScript ES6+** - Modern JavaScript features

## 📋 Prerequisites

Before running this application, make sure you have:

- Node.js (version 14 or higher)
- npm or yarn package manager
- Google Gemini API key

## 🔧 Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/aadhar-extractor.git
   cd aadhar-extractor
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Install additional packages**
   ```bash
   npm install lucide-react
   npm install -D tailwindcss postcss autoprefixer
   ```

4. **Initialize Tailwind CSS**
   ```bash
   npx tailwindcss init -p
   ```

5. **Configure Tailwind CSS**
   
   Update `tailwind.config.js`:
   ```javascript
   /** @type {import('tailwindcss').Config} */
   module.exports = {
     content: [
       "./src/**/*.{js,jsx,ts,tsx}",
     ],
     theme: {
       extend: {},
     },
     plugins: [],
   }
   ```

6. **Update src/index.css**
   ```css
   @tailwind base;
   @tailwind components;
   @tailwind utilities;
   
   * {
     margin: 0;
     padding: 0;
     box-sizing: border-box;
   }
   
   body {
     font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', 'Oxygen',
       'Ubuntu', 'Cantarell', 'Fira Sans', 'Droid Sans', 'Helvetica Neue',
       sans-serif;
     -webkit-font-smoothing: antialiased;
     -moz-osx-font-smoothing: grayscale;
   }
   ```

## 🔑 Getting Google Gemini API Key

1. Visit [Google AI Studio](https://aistudio.google.com/app/apikey)
2. Sign in with your Google account
3. Click "Get API Key" and then "Create API Key"
4. Copy the generated API key
5. Replace the API key in `AadharExtractor.jsx`:
   ```javascript
   const GEMINI_API_KEY = "your_api_key_here";
   ```

## 🚀 Running the Application

1. **Start the development server**
   ```bash
   npm start
   ```

2. **Open your browser**
   Navigate to `http://localhost:3000`

3. **Upload an Aadhar card image**
   - Click "Select Image File"
   - Choose a JPG, JPEG, or PNG image
   - Click "Extract Information"

## 📁 Project Structure

```
aadhar-extractor/
├── public/
│   ├── index.html
│   └── favicon.ico
├── src/
│   ├── components/
│   │   └── AadharExtractor.jsx
│   ├── App.jsx
│   ├── App.css
│   ├── index.js
│   └── index.css
├── package.json
├── tailwind.config.js
├── postcss.config.js
└── README.md
```

## 🔒 Security Features

- **Data Privacy**: Images are processed client-side and not stored on servers
- **Aadhar Masking**: Aadhar numbers are automatically masked (XXXX-XXXX-1234)
- **Secure API**: Uses HTTPS for all API communications
- **Input Validation**: File type and size validation
- **Error Handling**: Comprehensive error messages without exposing sensitive data

## 📝 Extracted Information

The application extracts the following information from Aadhar cards:

- **Full Name**: As printed on the card
- **Date of Birth**: In DD/MM/YYYY format
- **Age**: Automatically calculated from DOB
- **Aadhar Number**: 12-digit number (masked for security)
- **Gender**: Male/Female
- **Address**: If visible on the card

## 🎨 UI Components

- **Upload Section**: File input with drag-and-drop support
- **Image Preview**: Shows uploaded image before processing
- **Loading States**: Animated loading indicators
- **Results Cards**: Beautifully formatted information display
- **Error Messages**: User-friendly error notifications
- **Responsive Design**: Mobile-first approach

## 🔧 Customization

### Changing API Model
To use a different Gemini model:
```javascript
const GEMINI_API_URL = `https://generativelanguage.googleapis.com/v1beta/models/gemini-pro:generateContent?key=${GEMINI_API_KEY}`;
```

### Modifying Extraction Prompt
Update the prompt in the `extractAadharInfo` function to extract additional fields or change the format.

### Styling Changes
Modify Tailwind classes in the component or add custom CSS in `App.css`.

## 🚨 Troubleshooting

### Common Issues

1. **API Key Error**
   - Ensure your Gemini API key is valid
   - Check if the API key has necessary permissions
   - Verify the API key is correctly placed in the code

2. **Image Upload Issues**
   - Check file format (JPG, JPEG, PNG only)
   - Ensure file size is under 5MB
   - Try with a clearer image

3. **Extraction Failures**
   - Use high-quality, well-lit images
   - Ensure the Aadhar card is fully visible
   - Try different angles or lighting

### Error Messages

- `"API key not valid"` - Invalid or missing API key
- `"Unable to extract complete information"` - Poor image quality or unreadable text
- `"File size should be less than 5MB"` - Image too large
- `"Please select a valid image file"` - Unsupported file format
