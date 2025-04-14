import streamlit as st
import pandas as pd

# LINK da tua planilha transformado em CSV
sheet_url = st.secrets["sheet_url"]
csv_url = sheet_url.replace("/edit#gid=", "/export?format=csv&gid=")

df = pd.read_csv(csv_url)

st.title("📊 Dashboard Google Planilhas")
st.dataframe(df)
