# Financial Time Series Analysis Using Python

This repository contains Python code for preprocessing, visualizing, and analyzing financial time series data. The primary goal is to explore key financial metrics, process missing data, and generate visual insights for better understanding.

## Features

- **Data Preprocessing**: Converts dates, interpolates missing values, and structures data for analysis.
- **Data Visualization**: Generates a comprehensive set of plots for multiple financial metrics.
- **Time Series Analysis**: Implements ARIMA, SARIMAX, and seasonal decomposition for advanced forecasting.
- **Statistical Tools**: Includes RMSE, MSE, and other performance metrics for evaluating models.

---

## Requirements

To execute this code, install the following dependencies:
```bash
pip install -U -q PyDrive
pip install --user --upgrade statsmodels
from pydrive.auth import GoogleAuth
from pydrive.drive import GoogleDrive
from google.colab import auth
from oauth2client.client import GoogleCredentials 

auth.authenticate_user()
gauth = GoogleAuth()
gauth.credentials = GoogleCredentials.get_application_default()
drive = GoogleDrive(gauth)

file_id = '1AVbnOfblP2lJTOowA1JFTZ-wS-wYc6b3'
downloaded = drive.CreateFile({'id': file_id})
downloaded.GetContentFile('cherat-final-dataset.csv')
columns_names = ['Net_Margin', 'ROE', 'Quick_Ratio', ...]
interpolate_df = []

for col in columns_names:
    interpolate_df.append(preprocessed_df[col].interpolate(method='time'))

interpolate_df = pd.DataFrame(interpolate_df).T
import matplotlib.pyplot as plt

fig = plt.figure(figsize=(30, 30))
ax1 = plt.subplot2grid((6, 6), (0, 0), rowspan=1, colspan=5)
ax1.set_title('Open Price')
ax1.plot(df.index, df.Open, c='b')
plt.savefig('All_variables.png', transparent=True)
This `README.md` is tailored for your repository to explain its purpose, features, and usage. Replace placeholders with your contact information or any additional details.
