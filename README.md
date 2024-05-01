import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# a) Read test and label files
test_data = pd.read_csv('test.csv')
test_labels = pd.read_csv('test_labels.csv')

# b) Draw time series plots with anomaly regions
def plot_time_series_with_anomalies(data, labels):
    plt.figure(figsize=(12, 6))
    plt.plot(data.index, data.values, label='Time Series Data')
    for _, anomaly in labels.iterrows():
        plt.axvspan(anomaly['Start_Time'], anomaly['End_Time'], color='red', alpha=0.3, label='Anomaly Region')
    plt.xlabel('Time')
    plt.ylabel('Value')
    plt.title('Time Series Data with Anomaly Regions')
    plt.legend()
    plt.show()

# Assuming 'Start_Time' and 'End_Time' are the columns in the labels indicating anomaly regions
plot_time_series_with_anomalies(test_data, test_labels)

# c) Perform EDA and find out root cause
# You can perform various statistical and visual analyses to identify patterns or irregularities in the data

# d) Find out the variables which are the root cause for the anomaly
# Use techniques like correlation analysis, feature importance, or domain knowledge to identify variables contributing to anomalies
