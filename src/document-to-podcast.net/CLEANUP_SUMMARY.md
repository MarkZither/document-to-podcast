# Workspace Cleanup Summary

## Changes Made

### 1. Removed Temporary Test Directories
Cleaned up all temporary output directories that were created during development and testing:
- `config-test-output/`
- `demo-output/`
- `final-test/`
- `onnx-download-test/`
- `output/`
- `secrets-test-output/`
- `sk-onnx-test/`
- `test-audio/`
- `test-audio-mock/`
- `test-output/`
- `test-output3/`

### 2. Updated .gitignore
Enhanced the `.gitignore` file to prevent future temporary files from being committed:
```
# Generated audio files
*.wav
*.mp3

# .NET
bin/
obj/
*.user
*.suo
*.csproj.user
packages/

# Output directories
output/
*-output/
*-test/
temp/
models/
```

### 3. Improved CLI Default Behavior
Updated the command-line interface to use sensible defaults for output directories:

#### Before:
- Required both `--input-file` and `--output-folder` parameters
- No default output location

#### After:
- Only requires `--input-file` parameter
- Automatically uses temporary directory (`%TEMP%\document-to-podcast\`) if no output folder specified
- User-friendly message shows where output will be saved
- Updated help text to reflect optional nature of output folder

### 4. Output Directory Strategy
The application now follows best practices for output file management:

1. **User-specified output**: When `--output-folder` is provided, uses that directory
2. **Default temporary output**: Uses `%TEMP%\document-to-podcast\` for automatic cleanup
3. **Model cache**: ONNX models are cached in user profile directories:
   - Primary: `%APPDATA%\document-to-podcast\models\`
   - Fallback: `%USERPROFILE%\.cache\document-to-podcast\models\`
   - Last resort: Application directory (for development)

### 5. Benefits
- **Clean repository**: No temporary files or test outputs in source control
- **Better user experience**: No need to specify output folder for quick tests
- **Automatic cleanup**: Temporary files go to system temp directory
- **Proper caching**: Model files are cached in appropriate user directories
- **Cross-platform**: Uses standard .NET environment folder methods

## Usage Examples

### Quick test (outputs to temp directory):
```bash
dotnet run -- --input-file "document.pdf"
```

### Custom output location:
```bash
dotnet run -- --input-file "document.pdf" --output-folder "C:\MyPodcasts"
```

The application will now automatically handle output file management without cluttering the development workspace.
