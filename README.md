# Geography Answer Quality Review Skill

A reusable Agent Skill for reviewing and revising high school geography answers using knowledge retrieval and LLM-based quality checks.

## Overview

This Skill was developed as part of a personal AI geography tutoring project. It provides a structured approach for evaluating AI-generated answers, identifying knowledge errors, and improving responses based on available reference materials.

The Skill is designed for use with a Dify Agent and three independently configured tools.

## Key Features

- **Knowledge Retrieval:** Search a reference knowledge base for relevant geography concepts and scoring points.
- **Quality Review:** Identify factual errors, incorrect causal relationships, and missing key points.
- **Answer Revision:** Revise answers based on quality feedback while preserving correct information.
- **Verification Awareness:** Distinguish between knowledge-base-supported reviews and general LLM judgments.
- **Tool Usage Control:** Limit repeated retrieval attempts to avoid unnecessary tool calls.

## Agent Integration

The Skill works alongside three Dify Workflow tools:

| Tool | Function |
|---|---|
| `geography_knowledge_retrieval` | Retrieves candidate reference knowledge |
| `geography_quality_checker` | Reviews answers against available references |
| `geography_answer_reviser` | Revises answers based on review feedback |

The Skill defines the task execution guidelines. The actual retrieval, review, and revision operations are performed by the separately configured tools.

## Example

**Question:** What causes thermal circulation?

**Incorrect Answer:** Thermal circulation is directly caused by Earth's rotation. Warm air sinks, while cold air rises.

**Expected Revision:** Thermal circulation results from uneven heating of the Earth's surface. Warm air rises and cool air sinks, creating pressure differences that drive horizontal air movement and form a circulation system.

**Observed Test Behavior:**

- The Agent attempted knowledge retrieval twice.
- It proceeded to quality review when no matching reference was retrieved.
- It invoked the answer revision tool to correct the identified errors.
- It distinguished general model-based corrections from teacher-verified knowledge.

## Limitations

- Knowledge retrieval depends on the availability and quality of the configured knowledge base.
- The current knowledge base has limited coverage, and retrieval performance remains inconsistent.
- LLM-based quality reviews may miss errors or produce incorrect judgments.
- The Skill has been integrated and tested in example tasks, but its independent impact on accuracy has not been quantitatively evaluated.
- The three Dify tools and their knowledge base are not included in this repository.

## Project Status

**Prototype completed — basic Agent integration and functional testing performed.**

This repository documents an experimental Agent Skill developed for learning and portfolio demonstration. It is not a production-ready geography tutoring system.
