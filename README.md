# National Climate Data Center – NOAA

NOAA’s National Climatic Data Center (NCDC) is responsible for preserving, monitoring, assessing, and providing public access to weather data. 

NCDC provides access to daily data from the U.S. Climate Reference Network / U.S. Regional Climate Reference Network (USCRN/USRCRN) via anonymous ftp

let me see a complex mapreduce program on weather dataset. Here I am using one of the dataset of year 2021 of  Austin, Texas . We will do analytics on the dataset and classify whether it was a hot day or a cold day depending on the temperature recorded by NCDC.
NCDC gives us all the weather data we need for this mapreduce project.

### Command to download dataset from ftp
![](https://github.com/Pramodgopinathan/HadoopMinMax/blob/main/download.png)

### After downloading from terminal, it would be in the below mentioned folder
![](https://github.com/Pramodgopinathan/HadoopMinMax/blob/main/download2.png)

### Step 1: Create a new directory with name Weather as shown in the below Weather example
sudo mkdir Weather

### Step 2: Give permission to folder which was created 
sudo chmod -R 777 Weather

### Step 3: To create java files which i have created
![](https://github.com/Pramodgopinathan/HadoopMinMax/blob/main/MaxTemperatureMapper.java)
![](https://github.com/Pramodgopinathan/HadoopMinMax/blob/main/MaxTemperatureReducer.java)
![](https://github.com/Pramodgopinathan/HadoopMinMax/blob/main/MyMaxMinDriver.java)

I have created this java which have function that check min and say its cold day and max to say its hot day.

### Step 4: Now download the files in the folder which was created "Weather"

### Step 5: Check the permission of each files 
ls -all

### Step 6: Now give write permission to each files
sudo chmod +r *.*

### Step 7: Export classpath 
export CLASSPATH="/usr/local/hadoop/share/hadoop/common/hadoop-common-3.3.2.jar:/usr/local/hadoop/share/hadoop/mapreduce/hadoop-mapreduce-client-core-3.3.2.jar"

![](https://github.com/Pramodgopinathan/HadoopMinMax/blob/main/download3.png)

#### Note: hadoop-core is now hadoop-common and mine is 3.3.2 you need to check which version you have. You could do it using 'find' command in terminal.

### Step 8: Compile Java files (these files are present in directory Final-MyMaxMin). Its class files will be put in the package directory

![](https://github.com/Pramodgopinathan/HadoopMinMax/blob/main/download4.png)

### Step 9: Create a new file Manifest.txt (This is to make jar file understand where is the main class)
sudo gedit Manifest.txt

![](https://github.com/Pramodgopinathan/HadoopMinMax/blob/main/Manifest.txt)
Keep it inside the same folder as show above

### Step 10: Create Jar file 
![](https://github.com/Pramodgopinathan/HadoopMinMax/blob/main/download5.png)

### Step 11: Start hadoop hdfs and yarn also put Step 1 data (Weather.txt) into hdfs file

