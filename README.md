

# What is RECollect?

RECollect is a project forked from OpenRecall, which is an open-source alternative for Windows Recall or other closed-source substitutes. It snapshots the user's screen at short, regular intervals and stores them, allowing the user to navigate through them later through AI-augmented image recognition. RECollect aims to act as a better alternative for Windows Recall which requires Copilot+ PC certified hardwares.

## How does it differ from others?

Windows Recall, which is the service that this project aims to replace, has specific hardware requirements as mentioned above. It is only provided for PCs equipped with NPU with 40 TOPS or above. This results in only certain processors being able to use the service, such as Intel's Lunar Lake(Core Ultra 200V series), AMD's RYZEN AI 300 series(Strix Point/Krackan Point/Strix Halo) and Qualcomm's Snapdragon X series. RECollect aims to expand the hardware support, supporting CPU/GPU usage and even NPU, which has performance of less than 40 TOPS such as NPU 3 in Intel's Meteor Lake(Core Ultra Series 1) and Arrow Lake-H/HX(Core Ultra 200H/HX series). By supporting different hardware acceleration types, RECollect is able to allow the users to choose freely between the benefits provided by different hardware types, such as versatility of CPU, performance of GPU or efficiency of NPU.

## RECollect's features

RECollect utilizes DirectML for inference, providing compatibility for various hardware venders. However, for performance, this project will add support for CUDA/OpenVINO/RYZEN AI acceleration. RECollect also stores all snapshots locally, providing safety in the data management. This project also uses local AI implementation for OCR function.

## Features

- **Time Travel**: Revisit and explore your past digital activities seamlessly across Windows, macOS, or Linux.
- **Local-First AI**: OpenRecall harnesses the power of local AI processing to keep your data private and secure.
- **Semantic Search**: Advanced local OCR interprets your history, providing robust semantic search capabilities.
- **Full Control Over Storage**: Your data is stored locally, giving you complete control over its management and security.


## Comparison



| Feature          | OpenRecall                    | Windows Recall                                  | Rewind.ai                              |
|------------------|-------------------------------|--------------------------------------------------|----------------------------------------|
| Transparency     | Open-source                   | Closed-source                                    | Closed-source                          |
| Supported Hardware | All                         | Copilot+ certified Windows hardware              | M1/M2 Apple Silicon                    |
| OS Support       | Windows, macOS, Linux         | Windows                                          | macOS                                  |
| Privacy          | On-device, self-hosted        | Microsoft's privacy policy applies               | Connected to ChatGPT                   |
| Cost             | Free                          | Part of Windows 11 (requires specialized hardware) | Monthly subscription                   |

## Quick links
- [Roadmap](https://github.com/orgs/openrecall/projects/2) and you can [vote for your favorite features](https://github.com/openrecall/openrecall/discussions/9#discussion-6775473)
- [FAQ](https://github.com/openrecall/openrecall/wiki/FAQ)

## Get Started

### Prerequisites
- Python 3.11
- MacOSX/Windows/Linux
- Git

To install:
```
python3 -m pip install --upgrade --no-cache-dir git+https://github.com/openrecall/openrecall.git
```

To run:
```
python3 -m openrecall.app
```
Open your browser to:
[http://localhost:8082](http://localhost:8082) to access OpenRecall.

## Arguments
`--storage-path` (default: user data path for your OS): allows you to specify the path where the screenshots and database should be stored. We recommend [creating an encrypted volume](docs/encryption.md) to store your data.

`--primary-monitor-only` (default: False): only record the primary monitor (rather than individual screenshots for other monitors)

## Uninstall instructions

To uninstall OpenRecall and remove all stored data:

1. Uninstall the package:
   ```
   python3 -m pip uninstall openrecall
   ```

2. Remove stored data:
   - On Windows:
     ```
     rmdir /s %APPDATA%\openrecall
     ```
   - On macOS:
     ```
     rm -rf ~/Library/Application\ Support/openrecall
     ```
   - On Linux:
     ```
     rm -rf ~/.local/share/openrecall
     ```

Note: If you specified a custom storage path at any time using the `--storage-path` argument, make sure to remove that directory too.

## Contribute

As an open-source project, we welcome contributions from the community. If you'd like to help improve OpenRecall, please submit a pull request or open an issue on our GitHub repository.

## Contact the maintainers
mk2cvmk2cv@gmail.com

## License

RECollect is released under the [AGPLv3](https://opensource.org/licenses/AGPL-3.0), ensuring that it remains open and accessible to everyone.

