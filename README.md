<h2 align="center">🔥 Early LPG Gas Leakage Prediction System using Raspberry Pi and ADC1115 🌬️</h2>

<h3>📝 Description</h3>
<p>Greetings, gas safety enthusiasts! Welcome to my innovative project, an <b>early LPG gas leakage prediction system</b> using <i>Raspberry Pi</i> and <i>ADC1115</i>. With this system, you can have peace of mind knowing that potential gas leaks in your home can be <b>detected and predicted</b> before they become hazardous.</p>
<p>By leveraging the power of the <b>MQ-2 sensor</b>, we can accurately detect multiple gases such as <i>CO, H2, CH4, LPG, propane, alcohol, and smoke</i>. To convert the analog voltage readings to digital format, we utilize the <i>ADC1115</i> module and implement advanced filtering techniques to identify the target gases with precision.</p>
<p>⚠️ Please note that while this system provides valuable insights, it is important to be aware of the sensor's limitations. For critical safety purposes, I recommend using professional-grade gas detection equipment.</p>

<h3>🚀 Process</h3>
<ol>
  <li>Begin by creating a channel named "<b>IOT Gas Leakage Detection</b>" on <a href="https://thingspeak.com/">ThingSpeak</a>. Within the channel, set up eight graphs to visualize the gas concentration values effectively.</li>
  <li>Obtain the <b>write API key</b> for your ThingSpeak channel and update it in the "<b>raspberrypi.py</b>" code, ensuring seamless data transmission.</li>
  <li>For data analysis and storage, follow the instructions provided in this <a href="https://www.youtube.com/watch?v=gQLEOyBK6fg&t=314s">video</a> to upload the data to <b>AWS DynamoDB</b>. Create a data table in DynamoDB and make sure to update the table name and column names in the code.</li>
  <li>Once you have uploaded the "<b>raspberrypi.py</b>" file to your Raspberry Pi, run it to begin the data upload process. This code enables data transmission to ThingSpeak for visualization and AWS DynamoDB for further analysis.</li>
  <li>As the sensor values are being successfully uploaded to AWS DynamoDB, let's proceed with the following steps:</li>
    <ul>
      <li>Access <b>AWS SageMaker</b> and create a notebook instance to perform advanced data analysis.</li>
      <li>Upload the dataset file to the notebook area for seamless integration.</li>
      <li>Copy the code from the "<b>sagemaker.ipynb</b>" file into your notebook and execute it. This code trains an <b>XgBoost model</b> on the dataset, empowering us to predict gas leakages accurately.</li>
      <li>Execute the "<b>EmailAlerts.ipynb</b>" file on your local machine.</li>
      <li>This script fetches the latest uploaded data from DynamoDB and sends it to the endpoint of the trained model to obtain the probability of gas leakage.</li>
      <li>If the probability exceeds <b>0.5</b>, you will receive an <b>email alert</b> notifying you of a possible gas leakage in your house.</

li>
    </ul>
</ol>

<p>For more detailed information on how gas values are calculated and how to work with Raspberry Pi gas sensors, I highly recommend checking out this <a href="https://tutorials-raspberrypi.com/configure-and-read-out-the-raspberry-pi-gas-sensor-mq-x/">comprehensive tutorial</a> on Raspberry Pi Tutorials.</p>

<h3>🔒 Safety Measures</h3>
<p>Safety is my top priority! While this project enhances gas safety, it is essential to prioritize your well-being. Take necessary precautions, follow safety guidelines, and consult professionals when dealing with gas-related systems. Remember, safety always comes first!</p>

<p align="center">Stay safe and protected with our early gas leakage prediction system! Enjoy peace of mind knowing your home is safeguarded against potential hazards. 💪🔐🏠</p>
