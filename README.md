# treemap-resources

This repository hosts the resources used in the paper **Quantitative Comparison of Time-Dependent Treemaps**,
by Eduardo Vernier, Max Sondag, Joao Comba, Bettina Speckmann, Alexandru Telea, and Kevin Verbeek. 

The `./Datasets` directory contains the dynamic hierarchy datasets used in the benchmark and the code that generated them. Note that there are more than the 11 datasets shown in the paper.

`./Treemapping Code` has the Java implementations of Approximate (APP), Hilbert (HIL), Local Moves using zero (LM0) or four (LM4) local moves, Moore (MOO), Ordered with Pivot-by-Middle (PBM), Pivot-by-Size (PBZ), and Pivot-by-Split (PBS),
Slice-and-Dice (SND), Spiral (SPI), Squarified (SQR), and Strip (STR).

`./Figures` contains the plots and code for the figures present in the paper. Due to the limited space, we could only show a small subset of the low aggregation results. The complete results (for both datasets in the paper and not) are available here. 

### Generating Treemaps   [[code](https://github.com/vis2018/treemap-resources/tree/master/Treemapping%20Code/LayoutGeneratorAndVisualizer/src)]

This project contains all the code to generate the treemap layouts for 11 different algorithms, visualize them and classify the datasets. Datasets can be classified using DatasetClassifier.DataSetClassifier.java as the main class
A folder can be specified here from where to read the data from as well as where to output the classification.

Layouts can be generated by running `UserControl.Simulator.java`
This method can be be called from the commandline.
An example commandline run is:
`-width 1000 -height 1000 -technique moore -inputfolder D:/datasets/ -outputfolder D:/output/ -baseline true`

In case -baselines is set to true, baselines will be generated for each algorithm.
In the function getTReeMapGenerators one can specify for which algorithms to run the simulation and generate the output.

If one want to generate baselines for an algorithm not implemented in this codebase, they can use the class statistics.Baseline.BaseLineGenerator
In the main method one can specify where their folder with layouts and dataset is contained, and where to output the generated baselines
In case one want to visualize the datasets, UserControl.Visualiser.Visualizer.java should be chosen as the main class.
One can add additional datasets to be selected in GUI.java.

### Generating datasets from the Movielens database   [[code](https://github.com/vis2018/treemap-resources/blob/master/Datasets/MovieDataBaseFiltererSourceCode.zip)]

This project contains the code used to filter and partition the Movielens database into smaller sized datasets.
The datasets used in the paper can be generated by using finalSetting2 from Moviedatabase.DataSetSetting using Moviedatabase.DataSetCreator as the main class.

One can generate additional datasets by creating a new DataSetSetting using a combination of filters, and setting this filter in DataSetCreator.
The inputFolder and the outputFolder are specified using commandline arguments "-inputFolder X" and "-outputFolder Y".
Example command is `-inputFolder D:\MovieDatabase\data\ml-20m -outputFolder D:MovieDatabase\data\processed\`

### Generating the figures [[code](https://github.com/vis2018/treemap-resources/tree/master/Figures/Code)]

TODO
