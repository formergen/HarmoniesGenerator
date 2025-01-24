# OpenUtau USTx Auto Harmony Generator

## Description

This Python script is designed to automatically generate harmony parts for USTx files, a MIDI-like format used by OpenUtau and similar vocal synthesis software. It analyzes the notes in your USTx file, detects the key (major or minor), and creates new tracks with harmony notes (lower, upper, or both) based on a user-defined semitone interval.

This tool is helpful for:

*   Quickly creating backing vocals or harmonies for your songs in OpenUtau.
*   Experimenting with different harmony intervals and types.
*   Saving time by automating the process of manual harmony creation.

**Note:** The key detection and harmony generation algorithms are simplified and provide a starting point. For more sophisticated and musically advanced harmonies, further refinements (as outlined in the "Future Enhancements" section) would be beneficial.

## Features

*   **USTx File Format Support:** Reads and writes `.ustx` project files.
*   **Track Selection:** Allows you to choose specific tracks from your USTx project to generate harmonies for.
*   **Harmony Type Options:** Generates lower harmonies, upper harmonies, or both simultaneously.
*   **Key Detection (Major/Minor):**  Attempts to automatically detect the key (major or minor) of your music based on note frequencies.
*   **Manual Key Override:** Option to manually select the key (major or minor) if you prefer to override auto-detection.
*   **Scale-Aware Harmony Generation:**  Basic key correction ensures harmony notes generally stay within the detected major or minor scale.
*   **Customizable Interval:** User-defined semitone interval for harmony generation (e.g., 3 for a major third).
*   **User-Friendly Console Interface:**  Interactive command-line interface with colored text using `colorama` for better readability (especially on Windows).
*   **Automatic File Extension Handling:**  Automatically appends `.ustx` if you forget to include it in the input or output file paths.

## Installation

1.  **Python:** Ensure you have Python 3.x installed on your system. You can download it from [python.org](https://www.python.org).
2.  **Libraries:** Install the required Python libraries using pip:

    ```bash
    pip install pyyaml colorama
    ```

## Usage

1.  **Save the script:** Save the Python code (`main.py`) to your desired location.
2.  **Run the script:** Open your terminal or command prompt, navigate to the directory where you saved `main.py`, and run the script:

    ```bash
    python main.py
    ```

3.  **Follow the prompts:** The script will guide you through the harmony generation process:

    *   **Enter the path to your USTx file:** Provide the path to the `.ustx` file you want to process. You can type the path or drag and drop the file into the terminal. Brackets in the path will be automatically removed, and the `.ustx` extension will be added if missing.
    *   **Select track numbers:**  Choose the tracks for which you want to create harmonies by entering their numbers separated by commas (e.g., `1,2` or `1`).
    *   **Select harmony type:** Choose `1` for lower harmony, `2` for upper harmony, or `3` for both.
    *   **Enter semitone interval:**  Input the semitone interval for the harmony (e.g., `3` for major third, `4` for major third, `7` for perfect fifth).
    *   **Manual key selection?** Choose 'y' if you want to manually select the key and mode, or 'n' (or just press Enter) to use automatic key detection. If you choose manual, you'll be prompted to select the key and mode from lists.
    *   **Enter the path to save the new USTx file:**  Provide a path and filename for the new USTx file that will contain the harmony tracks. Again, brackets will be removed and the `.ustx` extension added if needed.

4.  **Import into OpenUtau:** Open the newly created `.ustx` file in OpenUtau. You will find new tracks added with the generated harmony parts.

## Limitations

*   **Simplified Key Detection:** The automatic key detection is based on statistical profiles and might not be perfect for all musical pieces, especially those with complex harmonies or key changes. Manual key selection is recommended for critical projects.
*   **Basic Harmony Generation:** The script generates parallel harmonies based on a fixed semitone interval. It does not yet implement more advanced harmony techniques like chord-based harmony, voice leading, or counterpoint.
*   **Key Correction is Basic:** The key correction attempts to keep harmony notes within the diatonic scale, but it's a simplified approach and might not always produce musically ideal results in all cases.
*   **Natural Minor Scale Only:** Minor key detection and harmony generation are currently based on the natural minor scale. Harmonic and melodic minor scales are not yet supported.

## Author

[[formergen](https://github.com/formergen)]
