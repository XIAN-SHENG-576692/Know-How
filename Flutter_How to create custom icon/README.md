# Flutter: How to create a custom icon

[[2025-06-17]] 20:47
[[2025-09-22]] 14:12

## 📌 Prerequisites

- Installed Flutter SDK

- Basic knowledge of pubspec.yaml configuration

- Installed a vector graphics editor

## 🚀 Steps to Create a Custom Icon

1. Prepare an SVG File

    Create or obtain an icon in .svg format.

2. Generate Icon Font with FlutterIcon

    Go to [FlutterIcon - Flutter custom icons generator](https://www.fluttericon.com/), upload your SVG file, and download the generated .zip file.

3. Place the Extracted Files

    Unzip the downloaded file and place the files in your project:
    - TTF file → `<WORK_DIR>/<ASSETS_PATH>`
    - Dart file → `<WORK_DIR>/lib/<ASSETS_LIB_PATH>`

4. Update pubspec.yaml

    Add the following content to pubspec.yaml:
    ```yaml
    flutter:
      fonts:
        - family: <ICONS_FAMILY>
          fonts:
            - asset: <ASSETS_PATH>
    ```

5. Fetch Dependencies

    Run the following command:
    ```bash
    flutter pub get
    ```

## 🎨 How to Create SVG Files

Recommended tools:
- [Flowchart Maker & Online Diagram Software](https://app.diagrams.net/)
- [Inkscape - Draw Freely. | Inkscape](https://inkscape.org/)

## 🛠️ Troubleshooting

### ❓ Issue: The generated SVG file contains unsupported tags

Solution:

1. Export the file as a pixel-based format (PNG/JPG) instead of SVG.

2. Use [File Converter - FreeConvert.com](https://www.freeconvert.com/) to convert it back to SVG.

3. (Optional) If it still doesn’t work, try [SVGOMG - SVGO's Missing GUI](https://jakearchibald.github.io/svgomg/).
    - Reference: [svg - Custom icon for flutter app show this error of convert to compound path manually - Stack Overflow](https://stackoverflow.com/questions/62232602/custom-icon-for-flutter-app-show-this-error-of-convert-to-compound-path-manually)

## Others

[material-design-icons/png/device at master · google/material-design-icons · GitHub](https://github.com/google/material-design-icons/tree/master/png/device)

[System icons - Material Design](https://m2.material.io/design/iconography/system-icons.html#system-icon-metrics)

