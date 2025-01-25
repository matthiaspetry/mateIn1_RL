# mateIn1_RL
**Implementation of DeepSeek R1 Style RL for Chess Mate-in-1 Detection**

Inspired by the advancements in reinforcement learning (RL) from DeepSeek R1, along with implementations like [TinyZero](https://github.com/Jiayi-Pan/TinyZero) and [simpleRL-reason](https://github.com/hkust-nlp/simpleRL-reason), this project aims to train language models (LLMs) to identify mate-in-1 positions in chess.

## Project Overview

The goal is to enhance LLMs' capabilities in chess, specifically focusing on:

- **Recognizing Mate-in-1 Situations**: A fundamental chess tactic where one move leads to checkmate.

## Methodology

### Step-by-Step Approach:

1. **Dataset Preparation**:
   - **Source**: Utilize the [Lichess Chess Puzzles Dataset](https://huggingface.co/datasets/Lichess/chess-puzzles) to curate a subset specific to mate-in-1 scenarios. This involves filtering and annotating positions where checkmate can be achieved in a single move.

2. **Chain of Thought (CoT) Dataset Creation**:
   - **Tools**: Employ Google Gemini 2 Flash Thinking and DeepSeek R1 for generating reasoning paths or explanations for each mate-in-1 puzzle.
   - **Objective**: Create a dataset where each puzzle is paired with a detailed thought process leading to the solution, to be used for supervised fine-tuning (SFT).

3. **Simplification for Training**:
   - **Dataset**: Convert the CoT explanations into a simpler form of (query, final answer) pairs, focusing on the immediate move needed for checkmate.

4. **RL Application**:
   - **Fine-Tuning**: Apply RL techniques similar to those used in DeepSeek R1 to a pre-trained model like Llama 8B or Qwen 2.5 7B which has been initially fine-tuned using the SFT dataset.
   - **Reference Implementations**: Leverage insights from [TinyZero](https://github.com/Jiayi-Pan/TinyZero) and [simpleRL-reason](https://github.com/hkust-nlp/simpleRL-reason) for RL implementation.

5. **Evaluation**:
   - **Hopes and Expectations**: The aim is to see if this method can effectively teach LLMs to recognize and solve mate-in-1 puzzles with high accuracy.

## Future Directions

- **Generalization**: Extend the model to handle more complex chess tactics like mate-in-2 or strategic play.
- **Performance Analysis**: Compare the performance of RL-trained models against baseline models to quantify improvement in chess understanding.

