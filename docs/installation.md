# OHRF installation guide

## Installation of the Open Java Development Kit (OpenJDK) version 11
OpenJDK is an open source alternative to Oracle's JDK, offering the same core functionality.

### Prerequisites
- Windows, macOS, or Linux

### Installation steps
1. **Visit the official OpenJDK website**. Download the latest version of [JDK](https://openjdk.org/install/) that corresponds to your operating system.
2. **Run the installer** and follow the on-screen instructions.
3. **After installation, set the JAVA_HOME environment variable** to the JDK installation directory.

### Checking the installation
- Check the Java installation.

```
java -version
```

This should display the Java version, confirming that the installation was successful.

## Anaconda installation
Anaconda is an open source distribution and platform for the Python and R programming languages. It is designed to simplify the installation and management of software packages and environments for data analysis, data science, machine learning and scientific computing in general.

### Prerequisites
- Windows, macOS, or Linux

### Installation steps
1. **Download the Anaconda installer** from the downloads page of the [project website] (https://docs.anaconda.com/free/anaconda/install/index.html).
2. **Run the installer**. Choose the appropriate version for your operating system (Windows, macOS, or Linux) and follow the download instructions.

### Checking the installation
After installation, you can start Anaconda Navigator (a graphical interface) or use the Anaconda prompt (terminal).

#### Anaconda Navigator:
From the start menu (Windows) or using the terminal (macOS/Linux), start Anaconda Navigator.

#### Anaconda Prompt (terminal):
Open Anaconda Prompt or the terminal and type:

```
conda --version
```

This should display the version of Conda, confirming that the installation was successful.

## Jupyter Notebook installation:
Jupyter Notebook is an open source web application that allows you to create and share documents that contain active code, equations, visualizations and narrative text.

### Prerequisites
- Windows, macOS or Linux

### Installation steps
1. **Install Jupyter Notebook with pip**: `pip install notebook`.
2. **Open Anaconda** by:
    - **Anaconda Navigator**, you will see a list of applications. Click on "Home" on the left-hand side and then click on the "Jupyter Notebook" icon. This will open Jupyter Notebook in your default browser. 
    - To run the notebook via command: `jupyter notebook`.
3. **Navigate to the OHRF directory** which contains all the Python notebooks separated by Delta table types: Bronze, Silver and Gold.

Remember that the Jupyter Notebook is a web-based interface, and the browser is used to interact with it. Make sure you keep the browser open while using Jupyter Notebook.

## Installing Apache Spark 3.2.1
Apache Spark is an open source cluster computing platform that provides APIs for in-memory and on-disk data processing. It is used in a wide variety of applications, including machine learning, data analysis and streaming processing.

To install Apache Spark 3.2.1, you will need the following requirements:

### Prerequisites
- The Java Development Kit (JDK) version 11 or higher
- Scala 2.13
- Python 3.8+

### Installation steps

#### Windows
1. **Download Apache Spark 3.2.1** from the downloads page of the [project website] (https://spark.apache.org/docs/3.2.1/).
2. **Unzip the downloaded package**.
3. **Download the WinUtils** for Hadoop 3.2.0 from Apache's [GitHub](https://github.com/cdarlint/winutils/tree/master/hadoop-3.2.0/bin) and place the binaries in Spark's bin directory (e.g. C:\spark-3.2.1-bin-hadoop3.2\bin).
4. **Set the necessary environment variables**:

     ```
     SET HADOOP_HOME=C:\path\to\hadoop
     SET SPARK_HOME=C:\path\to\spark-3.2.1-bin-hadoop3.2
     SET PATH=%SPARK_HOME%\bin;%JAVA_HOME%\bin;%HADOOP_HOME%\bin;%PATH%
     ```

#### Linux/macOS
1. **Download Apache Spark 3.2.1** from the downloads page of the [project website] (https://spark.apache.org/docs/3.2.1/).
2. **Unzip the downloaded package** by running the following command: `tar -xvf spark-3.2.1-bin-hadoop3.2.tgz`.
3. **Set the necessary environment variables** and add the following lines to your profile file (e.g. `.bashrc` or `.zshrc`):

     ```
     export JAVA_HOME=/path/to/jdk
     export HADOOP_HOME=/path/to/hadoop
     export SPARK_HOME=/path/to/spark-3.2.1-bin-hadoop3.2
     export PATH=$SPARK_HOME/bin:$JAVA_HOME/bin:$HADOOP_HOME/bin:$PATH
     ```

Run source `.bashrc` (or source `.zshrc`) to apply the changes.

### Running Spark
Open a terminal or command prompt and navigate to the Spark directory. Run the following command to start PySpark: `bin/pyspark`.

## Installing VSCode
Visual Studio Code (VSCode) is a source code editor developed by Microsoft. You can use VSCode to create, modify and run the OHRF Python notebooks.

### Installation steps
1. **Visit the official VSCode website**. Download the latest version of [VSCode](https://code.visualstudio.com/) that corresponds to your operating system.
2. **Run the installer** and follow the on-screen instructions.
3. **After installation, install the Python extension for VSCode** [from here](https://code.visualstudio.com/docs/languages/python).
5. **Select the Python interpreter** using the 'Python: Select Interpreter' command.
6. **Configure the Python extension** via the settings [from here](https://code.visualstudio.com/docs/languages/python).

## Installing Python Libraries
As principais bibliotecas utilizadas no âmbito do OHRF são as seguintes:

| Package      | Version  | Description                                        |
| ------------ | -------- | -------------------------------------------------- |
| delta-spark  | 1.2.1    | Python APIs for using Delta Lake with Apache Spark |
| findspark    | 2.0.1    | Find pyspark to make it importable                 |
| pyspark      | 3.2.1    | Apache Spark Python API                            |

## Installing Maven packages
The main Maven packages used to run OHRF on Apache Spark are:

| Package                                        | Version                           | Reference                                                                                                                     |
| ---------------------------------------------- | --------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| Apache Commons IO                              | 2.11.0                            | [Download](https://repo1.maven.org/maven2/commons-io/commons-io/2.11.0/commons-io-2.11.0.jar)                                 |
| Delta Core                                     | 1.2.0 - Scala Target 2.13         | [Download](https://repo1.maven.org/maven2/io/delta/delta-core_2.13/1.2.0/delta-core_2.13-1.2.0.jar)                           |
| Delta Storage                                  | 1.2.1                             | [Download](https://repo1.maven.org/maven2/io/delta/delta-storage/1.2.1/delta-storage-1.2.1.jar)                               | 
| Excel Streaming Reader                         | 4.0.1                             | [Download](https://repo1.maven.org/maven2/com/github/pjfanning/excel-streaming-reader/4.0.1/excel-streaming-reader-4.0.1.jar) |
| Apache POI Common                              | 5.2.2                             | [Download](https://repo1.maven.org/maven2/org/apache/poi/poi/5.2.2/poi-5.2.2.jar)                                             |
| Apache POI API Based On OPC and OOXML Schemas  | 5.2.2                             | [Download](https://repo1.maven.org/maven2/org/apache/poi/poi-ooxml/5.2.2/poi-ooxml-5.2.2.jar)                                 |
| POI Shared Strings                             | 2.5.5                             | [Download](https://repo1.maven.org/maven2/com/github/pjfanning/poi-shared-strings/2.5.5/poi-shared-strings-2.5.5.jar)         |
| Spark Excel                                    | 3.3.1\_0.18.5 - Scala Target 2.13 | [Download](https://repo1.maven.org/maven2/com/crealytics/spark-excel_2.13/3.3.1_0.18.5/spark-excel_2.13-3.3.1_0.18.5.jar)     |
| Spark XML                                      | 0.15.0 - Scala Target 2.13        | [Download](https://repo1.maven.org/maven2/com/databricks/spark-xml_2.13/0.15.0/spark-xml_2.13-0.15.0.jar)                     |
| SPOIWO                                         | 2.2.1 - Scala Target 2.13         | [Download](https://repo1.maven.org/maven2/com/norbitltd/spoiwo_2.13/2.2.1/spoiwo_2.13-2.2.1.jar)                              |
| TXW2 Runtime                                   | 3.0.2                             | [Download](https://repo1.maven.org/maven2/org/glassfish/jaxb/txw2/3.0.2/txw2-3.0.2.jar)                                       |
| XmlSchema Core                                 | 2.3.0                             | [Download](https://repo1.maven.org/maven2/org/apache/ws/xmlschema/xmlschema-core/2.3.0/xmlschema-core-2.3.0.jar)              |

To include JAR (Java Archive) packages in Apache Spark, you can use the `--jars` option when starting your Spark application. This allows you to specify paths to JAR files that will be sent to all nodes in the Spark cluster. Here are the basic steps:

1. **Copy the JAR to the Spark cluster nodes**: make sure that the JAR file you want to include is available on all the nodes in your Spark cluster. This can be done by manually copying the JAR to all nodes or by using tools such as HDFS (Hadoop Distributed File System) to distribute the JAR. Example **jars** directory path in Apache Spark: `/path/to/spark-3.2.1/jars`
2. **Start the Spark application with the --jars** option: when starting the Spark application, include the `--jars` option followed by the path of the JAR you want to include. For example: 
    `spark-submit --class your.package.MainClass --master yarn --deploy-mode cluster --jars /path/your/file.jar your-application-spark.jar`

    Make sure you replace **path/your/file.jar** with the actual path of your JAR and your **package.MainClass** with the path of the main class of your Apache Spark application.

    If you're running locally instead of in a cluster, you can use `local` or `local[*]` as the master:

    `spark-submit --class your.package.MainClass --master local[*] --jars /path/of/your/file.jar your-application-spark.jar`
3. **Access the JAR dependencies in the Spark code**: within your Apache Spark code, you can access the classes or resources of the included JAR as normal. Make sure your imports are correct.

    Remember that if the JAR contains external dependencies, you also need to ensure that these dependencies are available on all the nodes in the Spark cluster. Apache Spark will not automatically manage the JAR's external dependencies. You can use the `--packages` or `--repositories` option to manage additional dependencies.
