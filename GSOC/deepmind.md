# GSoC 2025 Google DeepMind Project Proposal

## Modernizing Gemini SDK Learning Resources: Migration, Tutorials, and Library Updates

### Basic Info

- Name: Guan-Ming (Wesley), Chiu
- GitHub: <https://github.com/guan404ming>
- Email: <guanmingchiu@gmail.com>
- LinkedIn: <https://www.linkedin.com/in/guan-ming-wesley-chiu-141504283/>
- Location: Taipei, Taiwan (GMT+8)

### About Me

Hi, I'm Guan-Ming Chiu! I'm an Information Management student at National Taiwan University (NTU), and I'm also a member of the NumPy organization. Currently, I'm gaining practical experience as a Frontend Developer intern at Microsoft. I enjoy working with a variety of technologies, including Python, JavaScript/TypeScript, and web frameworks like React and Next.js. Also, I'm enthusiastic about contributing to open-source projects, particularly those focused on creating awesome technologies to help people build better software. I'm also very keen to contribute to Google Summer of Code (GSoC) and give back to the open-source community.

### Why I Choose DeepMind

I have frequently used the Google Gemini SDK in my projects, and through this experience, I’ve come to appreciate its powerful capabilities. This has inspired me to give back to the open-source community, as I believe in the importance of contributing to the technologies I rely on.

Since my tech stack spans both Python and TypeScript, I feel this project is a perfect fit for my skill set, allowing me to apply my knowledge in both languages. Additionally, my experience with open-source contributions, particularly with the NumPy organization, has equipped me with the communication and collaboration skills necessary to work effectively within a community. I’m confident that my background will allow me to contribute meaningfully to the project, and I’m eager to create resources that will not only support developers but also help advance technologies in the process.

### Proposal Summary

Google DeepMind's Gemini SDK offers powerful capabilities for various machine learning applications, but many developers rely on outdated examples. This project aims to enhance Gemini learning resources by migrating existing tutorials, upgrading examples, and developing new end-to-end tutorials in Python and JavaScript / TypeScript, thus increasing adoption through up-to-date and accessible materials.

Additionally, I propose a automated code optimization and conversion tutorial based on my hackathon project, [DevopsCode](https://github.com/guan404ming/hack-devopscode), recognized at the TSMC Hackathon. This tutorial will try to simply the application to demonstrate basic code optimization using the Gemini SDK in TypeScript, focusing on core features and also leveraging LangChain related tools.

### Deliverables

1. Migrate 10-12 existing Python examples from the Gemini Cookbook to JavaScript / TypeScript or to the newest version, ensuring adherence to best practices and providing comprehensive documentation.
2. Building a comprehensive chatbot tutorial using Gemini’s text generation, covering advanced conversational flow management and dynamic content generation.
3. Create a detailed tutorial based on DevopsCode, showcasing code optimization and conversion using the Gemini SDK in TypeScript, including integration with LangChain related tools.
4. Identify and update 2 open-source libraries using outdated Gemini API versions to support the latest SDKs, ensuring proper documentation. Specifically targeting the migration of `darrenburns/elia` and `latitude-dev/latitude-llm` due to their high community activity and popularity.
5. Deliver comprehensive documentation for all tutorials and examples, ensuring clarity and ease of understanding.

### Project Plan and Milestones

The project will be structured into sequential stages to ensure efficient execution and high-quality deliverables.

#### Stage 1: Cookbook Migration (Weeks 2-4)

- Migrate existing Python examples from the Gemini Cookbook to JavaScript / TypeScript.
  - Develop the tutorial template for extensibility and reusability.
    - Ensure code adheres to best practices.
    - Use the latest features and libraries in the Gemini SDK.
  - Provide clear, comprehensive documentation explaining the code and underlying Gemini concepts.
  - Rigorously test and verify the accuracy of the migrated examples.
- Help address the issues raised in [google-gemini/cookbook#446 Update everything to use google-genai SDK](https://github.com/google-gemini/cookbook/issues/446).
- **Milestone:** 10-12 Python examples migrated to JavaScript / TypeScript or to the newest version, tested, and documented by the end of Week 4.

#### Stage 2: New Tutorials Development (Weeks 5-10)

- Build a comprehensive chatbot tutorial using Gemini’s text generation:
  - Focus on creating an interactive chatbot using Gemini’s text generation capabilities, with an emphasis on advanced conversational flow management, dynamic content generation, and context retention.
  - Build a user-friendly interface, allowing users to interact with the chatbot in real-time and visualize the conversational flow.
  - Cover setting up the Gemini API, handling complex user input, generating nuanced responses, managing multi-turn conversations, and deploying the chatbot using Streamlit.
  - I've built a chat interface prototype using Python([guan404ming/st-chat-ui](https://github.com/guan404ming/st-chat-ui)) and TypeScript(using package like [chat-ui](https://github.com/run-llama/chat-ui)), and I'll try to build a more comprehensive chatbot tutorial using Gemini's text generation capabilities.
- Develop a tutorial based on DevopsCode, demonstrating code optimization and conversion using the Gemini SDK in TypeScript.
  - Focus on core optimization features, showing how to suggest code quality improvements, detect errors, and recommend best practices.
  - Include a section demonstrating how to use LangChain related tools, including LangGraph and LangSmith, for graph-based code optimization and conversational debugging workflows.
- **Milestone:** 2 tutorials completed, tested, and documented; DevopsCode tutorial with LangChain related tools section completed by the end of Week 8.

#### Stage 3: Library Updates (Weeks 11-12)

Specifically, I will focus on migrating the following two repositories to the latest Gemini SDK due to their high popularity and active community involvement:

- **[darrenburns/elia](https://github.com/darrenburns/elia)**: That is a keyboard-centric terminal user interface for interacting with large language models. It allows users to chat with different large language models through a terminal interface.
  
- **[latitude-dev/latitude-llm](https://github.com/latitude-dev/latitude-llm)**: Latitude is an open-source prompt engineering platform that helps users build, evaluate, and refine prompts with AI. It provides a collaborative interface for prompt engineering and evaluation.

The update will include:

- Migrating `darrenburns/elia` and `latitude-dev/latitude-llm`** to the latest Gemini SDK.
- Updating any examples and code snippets that use outdated Gemini APIs to work with the current SDK.
- Providing clear documentation to ensure users can easily follow the updated processes.
- Demonstrating best practices for using the Gemini SDK within these repositories, ensuring the community can easily adopt and integrate the new version.
- **Milestone:** 2 libraries updated with the latest Gemini SDK examples, tested, and documented by the end of Week 10.

#### Stage 4: Documentation (Weeks 13-14)

- Ensure all examples, including the DevopsCode tutorial, migrated examples, are thoroughly documented.
- Provide clear explanations of code functionality and underlying Gemini concepts.
- Review all tutorials and examples for accuracy and clarity.
- Finalize documentation and submit the final work product for review.
- **Milestone:** All examples and tutorials fully documented and submitted for review by the end of Week 12.

#### Extra and Experiment (If time available)

- **Gemini and Numpy Use Case:**
  - Implement a tutorial demonstrating how to use Gemini to generate and analyze numerical data using Numpy.
  - Use Gemini to generate descriptions of datasets, then use Numpy to perform statistical analysis or create visualizations based on those descriptions.
  - Show how Gemini can be used to generate explanatory text for Numpy operations, enhancing understanding and accessibility for users.

### Approximate schedule

| **Week** | **Date Range** | **Tasks** |
|----------|----------------|-----------|
| Week 1   | 5/8-6/1       | Planning and scoping: Review existing Gemini SDK documentation. |
| Week 2   | 6/2-6/8       | Development phase 1: Develop the JavaScript / TypeScript example template. |
| Week 3   | 6/9-6/15      | Development phase 1: Write and test migrated examples. (6 examples) |
| Week 4   | 6/16-6/22      | Development phase 1: Write and test migrated examples. (6 examples) |
| Week 5   | 6/23-6/29       | Development phase 2: Develop the chatbot interface. |
| Week 6   | 6/30-7/6       | Development phase 2: Make the chatbot interface work with Gemini SDK. |
| Week 7   | 7/7-7/13        | Development phase 2: Develop the code optimization and conversion interface. |
| Week 8   | 7/14-7/20        | Development phase 2: Make the code optimization and conversion interface work with Gemini SDK. |
| Week 9   | 7/21-7/27      | Development phase 2: Test tutorials and integrate LangChain tools. |
| Week 10  | 7/28-8/3      | Development phase 2: Finalize tutorial documentation. |
| Week 11  | 8/4-8/10       | Development phase 3: Identify and update open-source libraries. |
| Week 12  | 8/11-8/17       | Development phase 3: Test and document library updates. |
| Week 13  | 8/18-8/24       | Development phase 4: Comprehensive documentation and review. |
| Week 14  | 8/25-8/31       | Final review and submission. |
