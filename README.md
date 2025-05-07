# CommentIntel

**A Domain-Specific Assistant for YouTube Comment Sentiment Analysis**

## Overview

CommentIntel is an LLM-powered assistant built using the OpenAI Assistants API. It enables users to:

- Search for YouTube videos on arbitrary topics.
- Retrieve and summarise top comments.
- Classify comment sentiment (positive, neutral, negative).
- Produce on-the-fly visualisations (e.g. pie charts) via a built-in code interpreter.
- Compare sentiment across multiple videos in a single conversational workflow.

Designed with a “Tony Stark” persona, CommentIntel demonstrates retrieval-augmented generation, structured function-calling, and dynamic code execution, all orchestrated in a seamless chat interface.

## Features

1. **Video Search**  
   Uses `youtube_search(query, max_results)` to fetch relevant videos.

2. **Video Selection & Comment Retrieval**  
   Maps user selections to video IDs via `select_video(index)`, then calls  
   `get_video_comments(video_id, max_comments)` to obtain up to 100 top-level comments.

3. **Thematic Summaries**  
   Automatically groups comments into “Praise,” “Complaints,” and “Memes/Sarcasm.”

4. **Sentiment Analysis**  
   Invokes `analyze_sentiment(comments)` to label each comment as positive, neutral, or negative.

5. **Dynamic Visualization**  
   Generates Python code for charts and executes it via `execute_python(code)` to embed plots directly in the conversation.

6. **Cross-Video Comparison**  
   Performs side-by-side sentiment comparisons between any two user-selected videos.

## Repository Structure

```
├── README.md
├── CommentIntel.ipynb           # Main Colab notebook with code and narrative
```

## Setup

1. **Clone the repository**  
   ```bash
   git clone https://github.com/your-username/commentintel.git
   cd commentintel
   ```
2. **Obtain API Keys**  
   - **OpenAI key:** [https://platform.openai.com/account/api-keys](https://platform.openai.com/account/api-keys)  
   - **YouTube Data API key:** [https://console.cloud.google.com/apis/credentials](https://console.cloud.google.com/apis/credentials)

3. **Configure keys**  
   Store your keys as environment variables, or provide them via `getpass()` prompts in the notebook.

## Usage

1. **Open and run** `CommentIntel.ipynb` in Google Colab or Jupyter.  
2. **Execute cells sequentially** to install libraries, define tools, and create the assistant.  
3. **Interact** with the assistant in the chat loop:
   ```bash
   Welcome to CommentIntel. Type 'exit' to quit.
   User: Can you find videos about renewable energy?
   Assistant: [lists top 5 videos]
   User: Select video 2
   Assistant: [summarises comments, sentiment chart…]
   ```

## Examples

- **Example 1:** Compare sentiment on a recent Kashmir-attack video vs. a historical India–Pakistan conflict video.  
- **Example 2:** Analyse and contrast viewer reactions to two AI-jobs videos.  
- **Example 3:** Evaluate IPL highlights comments and quantify team allegiance.

## Future Work

- Incorporate topic modelling to surface comment trends.  
- Extend to other social platforms (e.g. Reddit, Twitter).  
- Add real-time alerting for sentiment spikes on breaking news.  

## Acknowledgements

Developed by **Jivesh Shioshankar Dhakate**  
Generative AI: Language Models, University College Dublin, Spring 2025.
