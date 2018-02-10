# CS231n: Convolutional Neural Networks for Visual Recognition
This repository is the collection of solutions to the problem sets in Stanford
University's CS231n course from Spring 2017. The `assignments` directory of the
source tree includes the original bare problem sets. The `src` directory contains my solutions. The `datasets` directory contains compressed archives of the data sets used in the problem sets. The `lectures` directory contains the contents of the accompanying course website for Spring 2017. Licensing information, etc. is stored with the website inside the corresponding `7zip` archive.

## Assignemnt Setup
Each assignment has its own setup instructions. Here I am assuming that you are running the machine learning pipelines locally. If you want to do it remotely on something like Google Cloud or Amazon Web Services, you should see the original CS231 lectures for that.

### Assignment 1
In order to set up problem set 1, enter the `assignment1` directory and do the following:
```bash
cd src/assignment1
virtualenv -p python3 .env
source .env/bin/activate
pip install -r requirements.txt
```
Whenever you want to work with the problem set, you should run
```bash
source .env/bin/activate
```
and whenever you are done, you should deactivate the virtual environment by running
```bash
deactivate
```
to get out of the virtual environment. Next, you must fetch the CIFAR-10 data set for the problems. To do this, run the following from inside the `assignment1` directory.
```bash
cd cs231n/datasets
./get_datasets.sh
```
Should the shell script no longer work, I have also provided archives of the data sets used in the `datasets` directory in the project root.

## Using the Data Sets Locally
If for whatever reason the shell scripts for fetching the data sets for each assignment no longer work, you can also dump them from the `datasets` directory in the project root locally. Enter the project root and run the following commands to dump the files locally:
```bash
cd datasets
7z x <dataset>.7z
mv -r <dataset> ../src/assignmentN/cs231n/datasets/
```
where `N` is the assignment number (1, 2, or 3), and `<dataset>` is the name of the dataset. For example, to dump the CIFAR-10 dataset used in assignment 1, do the following:
```bash
cd datasets
7z x cifar-10-batches-py.7z.001
mv -r cifar-10-batches-py ../src/assignment1/cs231n/datasets/
```
and you're ready to roll.

## Notes
* Andrej Karpathy's lecture notes for the course can be found (here)[https://cs231n.github.io].
* The original course website is (here)[https://cs231n.stanford.edu/].
* I keep an archive of the accompanying lecture notes (here)[https://github.com/stallmanifold/cs231n.github.io/] for Spring 2017.