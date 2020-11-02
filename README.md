# google-cloud-big-data
Working with Big Data technologies in Google Cloud

## Links

- [Source repo](https://github.com/denisecase/google-cloud-big-data)

## Technologies

- [Google Cloud Dataflow](https://cloud.google.com/dataflow)
- [Apache Beam](https://beam.apache.org/)


## Beam - create data processing pipelines

Beam works with major big data tools and frameworks:

- [Apache Flink](https://flink.apache.org/)
- [Apache Samza](https://samza.apache.org/)
- [Apache Spark](https://spark.apache.org/)
- [Google Cloud Dataflow](https://cloud.google.com/dataflow/)
- [Twister2 (open source project)](https://twister2.org/)

Beam allows a choice of languages:

- [Java](https://beam.apache.org/get-started/quickstart-java/)
- [Python](https://beam.apache.org/get-started/quickstart-py/)
- [Go](https://beam.apache.org/get-started/quickstart-go/)

## Python Setup

Upgrade anaconda3 (or all packages). Open PowerShell as Admin and run either:

```Powershell
choco upgrade anaconda3 -y
choco upgrade all -y
```

Open Ananconda Prompt as Administrator and run:

```Anaconda
python --version
pip --version
python -m pip install --upgrade pip
python -m pip install --upgrade virtualenv
python -m pip install --upgrade setuptools
python -m pip install apache-beam
python -m pip install apache-beam[gcp]
```

## Execute a Pipeline

Explore these example files. 

- wordcount.py
- input/randj.txt

In Ananconda Prompt as Administrator, 
change directory to the examples folder of this repo and run:

```Anaconda
cls
python -m apache_beam.examples.wordcount_minimal --input input/randj.txt --output output/wc01
python -m apache_beam.examples.wordcount --input input/randj.txt --output output/wc02
python -m apache_beam.examples.wordcount_debugging  --input input/randj.txt --output output/wc03
python -m apache_beam.examples.windowed_wordcount  --input input/randj.txt --output output/wc04

```

## Possible Errors

Please install mkl-service package, see http://github.com/IntelPython/mkl-service

Check path variables. Reinstall numpy. 
If no luck, install miniconda "Just for me" to temp-conda as described at 
<https://github.com/conda/conda/issues/7714>. 

Run in Ananconda Prompt as Admin:

```Anaconda
conda install numpy --force-reinstall
```

Run in Windows Command Prompt:

```Windows
C:\temp-conda\Scripts\conda.exe install -p C:\tools\Anaconda3 python=3.5 conda
```

When you ran the new miniconda installer, your "Anaconda Prompt" shortcut may have been changed. If it no longer works correctly, right click on the "Anaconda Prompt" icon, choose "Properties", and make the Target field point to C:\Users\ScoobyDoo\Anaconda3 instead of C:\temp-conda


```Anaconda
conda install numpy --force-reinstall

conda install -c intel mkl-service
```

## More Examples

- [Code Examples](https://github.com/apache/beam/tree/master/sdks/python/apache_beam/examples)

## Resources

- [Apache Beam Quickstart - Python](https://beam.apache.org/get-started/quickstart-py/)
- [Apache Beam WordCount Examples](https://beam.apache.org/get-started/wordcount-example/)
- [Force update numpy](https://stackoverflow.com/questions/52792692/anaconda-python-how-to-reinstall-numpy/55363764)
- [Trouble-shooting setup](https://github.com/conda/conda/issues/7714)