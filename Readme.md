

Agentic AI Scalable Video Classification with LoRA Fine-Tuning and LangGraph-NLP Based Video Summarization

https://www.kaggle.com/code/rokoyim/human-activity-recognition

Agentic AI Video Classification
Combines video processing with multi-step AI reasoning for intelligent video analysis
"sports", "nature", "urban", "indoor_activity","presentation", "tutorial", "vlog", "news","entertainment", "education", "documentary,Speed, accuracy, 

Video Classification Agent - Setup & Usage Guide
Overview
This is a complete Agentic AI system that combines:
* Multi-step reasoning (agent plans and executes)
*  Video processing (frame extraction and analysis)
*  Computer vision (object detection, scene classification)
*  Memory system (learns from past analyses)
*  MCP integration (works with Claude)

Installation
Step 1: Install Dependencies


bash
# Create virtual environment
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Install packages
pip install fastmcp opencv-python numpy

# Optional: For OCR support
pip install pytesseract
Step 2: Project Structure


video-classification-agent/
├── server.py              # Main MCP server (code above)
├── requirements.txt       # Dependencies
├── test_videos/          # Sample videos
│   ├── sports.mp4
│   ├── nature.mp4
│   └── tutorial.mp4
└── README.md
Step 3: requirements.txt


fastmcp>=0.1.0
opencv-python>=4.8.0
numpy>=1.24.0
pytesseract>=0.3.10

Configuration
Claude Desktop Config
Add to ~/Library/Application Support/Claude/claude_desktop_config.json:


json
{
  "mcpServers": {
    "video-agent": {
      "command": "python",
      "args": ["/path/to/server.py"]
    }
  }
}
Restart Claude Desktop after configuration.

How It Works
Agentic Workflow


1. USER REQUEST
   "Classify this video"
          ↓
2. AGENT PLANNING
   Agent creates multi-step plan
          ↓
3. FRAME EXTRACTION
   Extract key frames (scene changes)
          ↓
4. FRAME ANALYSIS
   Detect objects, scenes, activities
          ↓
5. CLASSIFICATION
   Aggregate evidence, classify category
          ↓
6. INSIGHTS GENERATION
   Human-readable summary
          ↓
7. MEMORY UPDATE
   Store for future reference
Agent Reasoning
The agent uses ReAct pattern (Reasoning + Acting):


"

