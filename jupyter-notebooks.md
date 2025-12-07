## New project using uv & pyCharm
1. Create a new project directory:
```
uv init my-data-project
cd my-data-project
```

2. Create the virtual environment:
```
uv venv
```

3. Add Jupyter dependencies
```
uv add jupyter pandas
```

4. Configure PyCharm
- Open the Project
- Set the Interpreter
   > If you are using PyCharm 2024.3 or later, PyCharm now has native support for uv. In the "Add Interpreter" menu, you may see a "uv" option directly. If so, you can select that, and it will auto-detect your setup.
- Create and Run a Notebook
   > New > Jupyter Notebook. 

## Export data file
```
import pandas as pd
from IPython.display import FileLink

# export existing file
FileLink('my_file.csv')

# export dataFrame
df.to_csv('my_export.csv', index=False)
FileLink('my_export.csv')
```
