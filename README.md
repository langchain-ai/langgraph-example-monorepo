# Setup

Edit the `.env.example` file to create a proper `.env` file with your API keys. The only thing to copy over exactly is the `PYTHONPATH`, because without it LangGraph will not be able to find the `utils` module when you import it in `main.py`. If you wish to add more modules, just ensure that you add them to your `PYTHONPATH` environment variable.