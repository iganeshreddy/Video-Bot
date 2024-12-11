# Video-Bot

This repository contains a Python-based automation bot designed to download videos from platforms like Instagram and TikTok, upload them to a server using an API, and create posts with the uploaded videos. It also monitors a local directory for new `.mp4` files and processes them.

---

## Features


1. **Video Search**:
    - Search videos from given URLs
    
2. **Video Download**:
   - Downloads videos from given URLs using `yt_dlp`.
   
3. **Video Upload**:
   - Fetches a pre-signed upload URL via API and uploads the video using `aiohttp`.

4. **Post Creation**:
   - Creates posts with uploaded video metadata in a specified category.

5. **Directory Monitoring**:
   - Watches a folder for new `.mp4` files and processes them automatically.

6. **Cleanup**:
   - Deletes the local video file after successful upload and post creation.

---

## Prerequisites

- Python 3.8+
- `pip` (Python package installer)
- API access token for `socialverseapp`

---

## Setup and Installation

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/iganeshreddy/Video-Bot.git
   cd Video-Bot
   ```

2. **Create a Virtual Environment**:
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # For Linux/Mac
   venv\Scripts\activate   # For Windows
   ```

3. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Set Environment Variables**:
   Create a `.env` file in the root directory and add your API token:
   ```env
   FLIC_TOKEN=your_flic_token_here
   ```

5. **Prepare the Video Directory**:
   Ensure the `videos` directory exists in the root folder:
   ```bash
   mkdir videos
   ```

---

## Usage

### Run the Bot

```bash
python main.py
```

### Configuration

- **Input Video URLs**:
  Add Instagram/TikTok video URLs to the `VIDEO_URLS` list in the script.

- **Category ID**:
  Update the `CATEGORY_ID` variable with the desired category ID for your posts.

### Monitoring

The bot will monitor the `videos` directory for new `.mp4` files and process them automatically.

---

## File Structure

```
.
├── main.py                 # Main script
├── requirements.txt        # Required Python packages
├── videos/                 # Directory to store videos
```

---

## Dependencies

- `yt-dlp`: For downloading videos from Instagram and TikTok.
- `aiohttp`: For asynchronous HTTP requests.
- `asyncio`: For asynchronous event loops.
- `requests`: For handling API calls.
- `python-dotenv`: For managing environment variables.

---

## Known Issues

- **Hardcoded Configuration**:
  Some variables (e.g., `CATEGORY_ID`) need to be manually updated in the script.

- **File Monitoring**:
  Directory polling may not detect real-time file changes. Consider using `watchdog` for an event-driven approach.

---

## Contributing

1. Fork the repository.
2. Create a new branch for your feature/bug fix.
3. Submit a pull request with detailed explanations of your changes.

---


## Acknowledgments

- [yt-dlp](https://github.com/yt-dlp/yt-dlp) for video downloading.
- [aiohttp](https://docs.aiohttp.org/) for HTTP handling.
- The community for continuous support and improvements.
