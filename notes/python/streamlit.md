## Streamlit

Streamlit is an open-source app framework for Machine Learning and Data Science projects.  
It allows you to create beautiful, interactive web applications for your machine learning and data science projects using simple Python scripts. Streamlit is designed to make it easy for data scientists and machine learning engineers to quickly build and share custom web apps for their work, without requiring any front-end web development experience.

### Key Features

- **Easy to Use:** Build apps with pure Python. No need for HTML, CSS, or JavaScript.
- **Reactive UI:** Widgets like sliders, buttons, and text inputs automatically update your app when interacted with.
- **Live Reload:** Changes to your script are automatically reloaded in the browser.
- **Data Display:** Effortlessly display dataframes, charts, images, audio, and video.
- **Integration:** Works well with popular Python libraries such as Pandas, Matplotlib, Plotly, Altair, and more.
- **Deployment:** Easily share your apps with others using Streamlit Cloud or by deploying on your own server.

### Basic Usage

- **Install Streamlit:**  
  `pip install streamlit`
- **Run a Streamlit app:**  
  `streamlit run <your_script.py>`
- **Add UI elements:**  
  Use functions like `st.write()`, `st.title()`, `st.slider()`, `st.button()`, etc., to add content and interactivity to your app.
- **Automatic Reload:**  
  When you save changes to your script, Streamlit automatically updates the app in your browser.

### Commonly Used Streamlit Functions

- `st.title("Title")` — Add a title to your app.
- `st.header("Header")` — Add a header.
- `st.subheader("Subheader")` — Add a subheader.
- `st.write("Text or Data")` — Display text, data, or even charts.
- `st.markdown("Markdown text")` — Render Markdown-formatted text.
- `st.dataframe(df)` — Display a Pandas DataFrame.
- `st.line_chart(data)` — Display a line chart.
- `st.slider("Label", min, max, value)` — Add a slider widget.
- `st.button("Label")` — Add a button.
- `st.text_input("Label")` — Add a text input box.
- `st.file_uploader("Label")` — Add a file uploader.

### Example: Simple Streamlit App

```python
import streamlit as st

st.title("Hello Streamlit")
st.write("This is a simple Streamlit app.")

number = st.slider("Pick a number", 0, 100, 25)
st.write(f"You selected: {number}")

if st.button("Say hello"):
    st.write("Hello there! 👋")
```

### Example: Displaying a DataFrame

```python
import streamlit as st
import pandas as pd

df = pd.DataFrame({
    "A": [1, 2, 3],
    "B": [4, 5, 6]
})

st.write("Here is a sample DataFrame:")
st.dataframe(df)
```

### Workflow

1. **Write your app** in a Python script using Streamlit functions.
2. **Run the app** with `streamlit run your_script.py`.
3. **Interact** with your app in the browser.
4. **Edit and save** your script to see live updates.

### Resources

- [Streamlit Documentation](https://docs.streamlit.io/)
- [Streamlit Gallery](https://streamlit.io/gallery)
- [Streamlit Community Forum](https://discuss.streamlit.io/)

---