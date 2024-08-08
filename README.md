# LangGraph Cloud Example Monorepo

![](static/agent_ui.png)

This is an example monorepo with multiple agents to deploy with LangGraph Cloud.

[LangGraph](https://github.com/langchain-ai/langgraph) is a library for building stateful, multi-actor applications with LLMs. The main use cases for LangGraph are conversational agents, and long-running, multi-step LLM applications or any LLM application that would benefit from built-in support for persistent checkpoints, cycles and human-in-the-loop interactions (ie. LLM and human collaboration).

LangGraph shortens the time-to-market for developers using LangGraph, with a one-liner command to start a production-ready HTTP microservice for your LangGraph applications, with built-in persistence. This lets you focus on the logic of your LangGraph graph, and leave the scaling and API design to us. The API is inspired by the OpenAI assistants API, and is designed to fit in alongside your existing services.

In order to deploy this agent to LangGraph Cloud you will want to first fork this repo. After that, you can follow the instructions [here](https://langchain-ai.github.io/langgraph/cloud/) to deploy to LangGraph Cloud.

# Explanation

## File Structure

This repository shows a few potential file structures all in one monorepo. To start with, all of the projects we build are inside of the subdirectory `all_projects`. Inside of this subdirectory we have two more subdirectories.

The first is called `my_project`, which could contain multiple projects, but in our case just contains one called `project_one`. Inside of `project_one` we setup a Python package using a `pyproject.toml` file to manage our dependencies. You will also notice that `project_one` doesn't just contain a `main.py` file, but also a `utils` folder that is imported into the `main.py` file. 

The second subdirectory is called `project_two` which is a standalone Python package with the same overall structure as `project_one` but it uses `requirements.txt` instead of `pyproject.toml` to manage dependencies.

## Configuration file

Inside our `langgraph.json` file you will first notice that our dependencies value is a list that includes the directories of both of our dependency files, and we also register both of our graphs, showcasing the ability of Langgraph to host multiple graphs from the same deployment. 

This use case shows how LangGraph can be configured for hosting multiple graphs from within the same repo, even if the projects are nested in different subdirectories and use different dependency systems.