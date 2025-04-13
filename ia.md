# GSoC 2025 Open Library Project Proposal

## Enhancing Digital Book Accessibility: Validating and Preserving Existing URLs

### Basic Info

- Name: Guan-Ming (Wesley), Chiu
- GitHub: <https://github.com/guan404ming>
- Email: <guanmingchiu@gmail.com>
- LinkedIn: <https://www.linkedin.com/in/guan-ming-wesley-chiu-141504283/>
- Location: Taipei, Taiwan (GMT+8)

### About Me

Hi, I'm Guan-Ming Chiu! I'm an Information Management student at National Taiwan University (NTU), and I'm also a member of the NumPy organization. Currently, I'm gaining practical experience as a Frontend Developer intern at Microsoft. I enjoy working with a variety of technologies, including Python, JavaScript/TypeScript, and web frameworks. I'm passionate about making digital resources more accessible and believe in the importance of preserving digital information. I'm eager to apply my skills to enhance the Internet Archive's digital library.

### Why I Choose Open Library

The Internet Archive's mission to preserve and provide universal access to all knowledge deeply resonates with my values. This project, "Enable Links in Archive.org Books," directly addresses the challenge of making digital books more interactive and accessible. By improving the discoverability and preservation of web references within books, we can significantly enhance the utility of these resources for researchers and the general public. I'm particularly excited to contribute to a project that combines web development, data processing, and digital preservation.

### Proposal Summary

This project aims to improve the accessibility and long-term preservation of digital books on Archive.org. It will focus on validating URLs extracted from OCR'd book text and ensuring their preservation through the Wayback Machine's Save Page Now (SPN2) API. Furthermore, the project will implement a BookReader plugin to render these validated URLs as clickable links, enhancing user interaction.

### Goals

1. **Preserving Valid URLs in Wayback:**
    - **Validate Existing URLs:** Develop a robust mechanism to check the liveness of extracted URLs using HTTP HEAD requests. This includes handling various HTTP status codes and potential network errors.
    - **Archive Live URLs via SPN2:** Integrate with the Wayback Machine's SPN2 API to capture snapshots of live URLs. Implement retry logic for API requests to ensure reliable archiving.
    - **Save Archived URLs in `urls.json`:** Store the archived URLs and their corresponding metadata (e.g., page number, item ID) in a structured `urls.json` file associated with each book item. This will facilitate future access and analysis of the archived links.
2. **Clickable URLs in Books:**
    - **Render URLs as Clickable Links in BookReader:** Create a BookReader plugin that identifies and highlights validated URLs within the book content. Users can then click on these highlighted URLs to navigate to the archived versions. This will require integration with the BookReader's text layer and potentially an entities endpoint to identify URL locations.

### Deliverables

1. **Python Script for URL Validation and SPN2 Archiving:**
    - A well-documented Python script that automates the process of validating extracted URLs and archiving live ones using the SPN2 API.
    - The script will generate detailed log files and `urls.json` files for each processed book item.
    - The script should be robust enough to handle large amounts of data.
2. **Enhanced BookReader Plugin:**
    - A BookReader plugin that highlights and renders validated URLs as clickable links within the book content.
    - The plugin will be compatible with the existing BookReader infrastructure and provide a seamless user experience.
3. **Comprehensive Documentation:**
    - Detailed documentation covering the implementation, usage, and maintenance of the developed tools and enhancements.
    - This includes API documentation, code comments, and user guides.

### Project Plan and Milestones

#### Stage 1: URL Validation and Preservation (Weeks 1-7)

- **Weeks 1-2: Pipeline Integration**
  - Set up the development environment and gain access to the existing URL extraction pipeline.
  - Thoroughly understand the data structure and formats of the extracted URLs.
  - Plan the structure of the item processing log and `urls.json` file.
    - **Sample Validation/Archiving Code:**

            ```python
            import requests, json, logging, os
            logging.basicConfig(level=logging.INFO)

            def validate_url(url):
                try: return requests.head(url, timeout=5).status_code == 200
                except: return False

            def archive_url(url):
                try: return requests.get(f"[https://web.archive.org/save/](https://web.archive.org/save/){url}").status_code == 200
                except: return False

            def process_urls(urls, item_id, output_dir):
                valid, archived, log = [], [], []
                for url in urls:
                    if validate_url(url):
                        valid.append(url)
                        if archive_url(url): archived.append(url); log.append({"url": url, "status": "archived"})
                        else: log.append({"url": url, "status": "archive_failed"})
                    else: log.append({"url": url, "status": "validation_failed"})
                os.makedirs(output_dir, exist_ok=True)
                json.dump(log, open(os.path.join(output_dir, f"{item_id}_log.json"), "w"), indent=4)
                json.dump(archived, open(os.path.join(output_dir, f"{item_id}_urls.json"), "w"), indent=4)
            ```

    - **Sample GitHub Actions Pipeline (`.github/workflows/main.yml`):**

            ```yaml
            name: URL Validation and Archiving

            on:
              push:
                branches:
                  - main
              pull_request:
                branches:
                  - main

            jobs:
              build:
                runs-on: ubuntu-latest

                steps:
                - name: Checkout code
                  uses: actions/checkout@v3

                - name: Set up Python
                  uses: actions/setup-python@v4
                  with:
                    python-version: '3.9'

                - name: Install dependencies
                  run: pip install requests

                - name: Run URL validation and archiving script
                  run: python your_script_name.py  # Replace with your script name
            ```

- **Weeks 3-4: URL Validation Development**
  - Develop and implement the URL validation logic using HTTP HEAD requests.
  - Implement error handling and retry logic.
- **Weeks 5-6: SPN2 Integration & Data Storage**
  - Integrate with the Wayback Machine's SPN2 API to archive live URLs.
  - Implement data storage to maintain logs and `urls.json` files.
- **Week 7: Testing**
  - Thoroughly test the validation and archiving script with a diverse set of extracted URLs.
  - Refine the script based on test results and feedback.
- **Milestone:** Validating and archiving script completed and tested.

#### Stage 2: Clickable URLs in BookReader (Weeks 8-13)

- **Weeks 8-10: BookReader Plugin Core Development**
  - Develop the core functionality of the BookReader plugin.
  - Integrate the plugin with the BookReader's text layer.
- **Weeks 11-12: Entities Endpoint Integration & UI Enhancement**
  - Integrate with the entities endpoint to identify URL locations.
  - Enhance the plugin's UI to highlight clickable URLs.
- **Week 13: Testing & Refinement**
  - Test the plugin with various books and URLs.
  - Refine the plugin based on test results and feedback.
- **Milestone:** BookReader plugin completed.

#### Stage 3: Documentation (Week 14)

- **Week 14: Documentation and Final Submission**
  - Document the code, implementation details, and usage instructions for the developed tools and enhancements.
  - Finalize the project and submit the deliverables.
- **Milestone:** Comprehensive documentation and final submission completed.

### Approximate schedule

|   **Week** |   **Date Range** |   **Tasks** |
| ---------: | ---------------: | :---------------------------------------------- |
|     Week 1 |        5/8-6/1 |   Pipeline Integration                         |
|     Week 2 |        6/2-6/8 |   Pipeline Integration                         |
|     Week 3 |       6/9-6/15 |   URL Validation Development                   |
|     Week 4 |      6/16-6/22 |   URL Validation Development                   |
|     Week 5 |      6/23-6/29 |   SPN2 Integration & Data Storage              |
|     Week 6 |      6/30-7/6 |   SPN2 Integration & Data Storage              |
|     Week 7 |       7/7-7/13 |   Testing                                      |
|     Week 8 |      7/14-7/20 |   BookReader Plugin Core Development          |
|     Week 9 |      7/21-7/27 |   BookReader Plugin Core Development          |
|    Week 10 |       7/28-8/3 |   BookReader Plugin Core Development          |
|    Week 11 |       8/4-8/10 |   Entities Endpoint Integration & UI Enhancement |
|    Week 12 |      8/11-8/17 |   Entities Endpoint Integration & UI Enhancement |
|    Week 13 |      8/18-8/24 |   Testing & Refinement                         |
|    Week 14 |      8/25-8/31 |   Documentation and Final Submission           |