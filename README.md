<h2> Early LPG Gas leakage prediction system using Raspberry pi and ADC1115 </h2>
<h3> Description </h3>
<p> The MQ-2 sensor can detect multiple gases (CO, H2, CH4, LPG, propane, alcohol, smoke) and outputs analog voltage. 
  This project can convert it to digital using ADS1115 and filter out the target gases.
The sensor can be inaccurate so don't use those measurements if you need them for security purposes. 
  Use some professional measurement device if you need to do this. </p>
<h3> Process </h3>
<p>Go to <a href="https://thingspeak.com/">Thingspeak</a> create a channel named "IOT Gas Leakage Detection" and create 8 graphs in order to show the gases concentration values .</p>
<p>Get the write API key for the channel and update it with your key in the "raspberrypi.py" code</p>
<p>To upload the data in the AWS DynamoDB follow this <a href="https://www.youtube.com/watch?v=gQLEOyBK6fg&t=314s">video</a> ,create your own data table and update the table name and column names in the code above.(Write Correct Column names other wise the code might not work)</p>
<p>
  upload the <b>raspberrypi.py</b> file in your raspberry pi and run it.<br>
  The code will upload the data in thingspeak for data visualization and in AWS DynamoDB for analysis and storage.
</p>
<p>
  once the sensor values started to get uploaded in the AWS DynamoDB. <br>
  -> go to the AWS Sagemaker <br>
  -> create a notebook instance <br>
  -> upload the the dataset file in the notebook area <br>
  -> copy the sagemaker.ipynb file code in to your notebook and execute it .(it will generate an endpoint copy the endpoint name)<br>
  -> The sagemaker.ipynb file contains code to train an XgBoost model on the dataset to predict wheather a leakage occurs or not.<br>
  -> Run the EmailAlerts.ipynb file in your local machine<br>
  -> This will fetch latest uploaded data from dynamoDB and send it to the endpoint of the trained model to get the probability of the gasleakage. <br>
  -> if the Probility is grater than 0.5 the code will send your email an alert saying that "There is possiblity of Gas leakage in your house"<br>
</p>
<p>For more details how the values are calculated you can read <a href="https://tutorials-raspberrypi.com/configure-and-read-out-the-raspberry-pi-gas-sensor-mq-x/">tutorial on Raspberry Pi Tutorials.</a></p>
