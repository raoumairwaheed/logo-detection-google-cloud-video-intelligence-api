# Video Logo Detection Tool (Google Cloud Video Intelligence Api)

This script utilizes the Google Cloud Video Intelligence API to detect logos in a video file. The detected logos, along with their descriptions, confidence scores, and positions in the video frames, are saved in a JSON file for further analysis.

> **Note**: Before using this tool, make sure to replace the `GOOGLE_APPLICATION_CREDENTIALS` environment variable with the path to your own Google Cloud Service Account key file (`loyal-vent-356807-b0c9c97dce30.json`) generated from the Google Cloud Console.

## Prerequisites

- Python 3.x installed
- Google Cloud Video Intelligence API enabled
- Google Cloud Service Account key file (JSON) with appropriate permissions

## Installation

1. Clone this repository to your local machine.
2. Install the required Python dependencies using the following command:

```bash
pip install -r requirements.txt
```

## Usage

To detect logos in a video file, use the following command in your terminal or command prompt:

```bash
python detect_logo.py
```

The tool will process the video (`sample_video.mp4`) and generate a JSON file (`logo_detection.json`) containing the detected logos, their descriptions, confidence scores, and their positions in the video frames.

```python
# Replace these values with your desired video file and output JSON file paths
filename = "sample_video.mp4"
output = "logo_detection.json"
detect_logo(filename, output)
```

Please ensure that you have properly set up the Google Cloud Service Account key file and enabled the necessary APIs in your Google Cloud Console before running the tool.

## Output

After running the tool, the `logo_detection.json` file will contain the detected logos and their information in the following format:

```json
{
    "logo_detection_results": [
        {
            "entity_id": "/m/0dgrtq",
            "description": "Google",
            "logo_tracks": [
                {
                    "start_time": "0s",
                    "end_time": "95.566666s",
                    "confidence": 0.9200875,
                    "bounding_box": {
                        "left": 0.028109048217058182,
                        "top": 0.02630182906973362,
                        "right": 0.13220174610614777,
                        "bottom": 0.11288830614089966
                    },
                    "attributes": [
                        {
                            "name": "logo",
                            "confidence": 0.9200875,
                            "value": "Google"
                        }
                    ]
                },
                ...
            ],
            "logo_segments": [
                {
                    "start_time": "0s",
                    "end_time": "95.566666s"
                },
                ...
            ]
        },
        ...
    ]
}
```

## Bounding Box on Videos

For drawing bounding boxes on the video using the JSON responses from Google Cloud Vision API, you can use the following repository: [draw-bounding-boxes-on-google-cloud-vision-api-response](https://github.com/raoumairwaheed/draw-bounding-boxes-on-google-cloud-vision-api-response). Please follow the instructions in that repository to visualize the detected labels with bounding boxes on your video.

## Reference

For more information about the Google Cloud Video Intelligence API, please visit the [official documentation](https://cloud.google.com/video-intelligence).
