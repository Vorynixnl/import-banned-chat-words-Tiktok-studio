#  tiktok banned Chat words by Vorynix

A Windows desktop tool that adds words one at a time to the TikTok LIVE Studio keyword filter.

## Getting started

1. Run `dist\Verboden TikTok Woorden Tool by Vorynix.exe`.
2. The tool does not require a separate Python installation. TikTok LIVE Studio must be installed. The **Open TikTok LIVE Studio** button launches `C:\Program Files\TikTok LIVE Studio\TikTok LIVE Studio Launcher.exe`.
3. In LIVE Studio, open **Instellingen > Chat** and navigate to the keyword filter.
4. In the tool, check the number of keywords already in LIVE Studio. The default is 27; change it if the actual count is different. LIVE Studio allows up to 500 keywords.
5. Edit the displayed word list if needed, or click **Importeer woordenlijst** (Import word list) to load a `.txt` or `.csv` file. Use one word per line in a text file. For CSV files, the tool recognizes column headers such as `word`, `keyword`, or `trefwoord`; without a recognized header, it treats the cells as words.
6. Review the list and click **Voeg maximaal ... woorden toe** (Add up to ... words). Confirm when prompted. The keyword field in LIVE Studio must be empty.

The included list contains 566 unique words and variants, grouped in English, Dutch, German, and French. Each run uses at most the first 473 words, and never more than the available capacity calculated from the existing-keyword count you entered. Changes made to the list in the app are not automatically saved to the source file.

## While adding words

- The tool brings the LIVE Studio settings window to the foreground, pastes each word into the keyword field, and clicks **Toevoegen** (Add) after every word.
- It visually checks that the field is empty again after each click before continuing. If it cannot recognize the interface or a word was not visibly added, it stops and displays an error.
- Words longer than 30 characters are skipped. The tool does not compare the words against keywords already in LIVE Studio.
- Stop with **Ctrl+Shift+F12**, or move the mouse to the upper-left corner. The tool may minimize while automation is running; the hotkey and mouse fail-safe remain available.
- Avoid using the mouse or keyboard in LIVE Studio while the tool is running so that input and clicks go to the intended controls.

## How it works

The tool does not use a TikTok API or change account settings remotely. It automates the visible LIVE Studio interface using mouse, keyboard, and clipboard input. A bundled image of the empty `0/30` counter is used to visually confirm that the keyword field is empty. The tool restores the previous clipboard contents after automation.

LIVE Studio and the tool must be accessible on the same desktop. Keep the keyword filter visible and empty, and do not change the interface scale or position while words are being added. If LIVE Studio is running as administrator, Windows may ask for UAC permission to restart the tool at the same privilege level.

## Troubleshooting

- **LIVE Studio not found:** Start LIVE Studio and open **Instellingen > Chat** with the keyword filter visible.
- **Empty counter not recognized:** Clear the keyword field, make sure the filter is visible, and check that the interface is not changed or obscured.
- **A word was not added:** Check the filter list and the 500-keyword limit. Make sure the existing-keyword count in the tool is not lower than the actual count.
- **Launcher not found:** Install TikTok LIVE Studio at the default location, `C:\Program Files\TikTok LIVE Studio\`, or start LIVE Studio yourself.

The standalone executable is at `dist\Verboden TikTok Woorden Tool by Vorynix.exe`. The source code, word list, and build files are alongside this README.
