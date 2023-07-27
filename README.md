### Experiment Data Used in Paper "PTdetector: Automated JavaScript Front-end Library Detector"

The tool `PTdetector` can be found [here](https://github.com/aaronxyliu/PTdetector).

For each of the charts in the paper, we consolidated both the associated dataset files and the code in a folder, presented as a Jupyter Notebook.

#### Data Files

All the related experiment data is arranged into the following four files.

`pt_stat.csv` @ Each entry represents a JavaScript file and its pTree statistics
- `file_id`: The ID of the file
- `library`: The library name
- `file`: The file name
- `size`: The number of vertices in the pTree
- `depth`: The depth of the pTree
- `# back edges`: The number of back edges during pTree generation
- `# identifiers`: The number of identifiers in the pTree
- `# random_vertices`: The number of random-generated vertices removed during the feature generation workflow

`ranks.SEMrushRanks-us.csv` @ Download from SEMRUSH websites US traffic ranking on Feb 23, 2023.

`detection_result.csv` @ The detection result after applying LDC, Wappalyzer, and PTdetector on 80 top-traffic web pages.
- `domain`: The domain name
- `rank`: The domain rank
- `url`: The home page url under the domain
- `ground truth`: The ground truth library loaded on the web page
- `LDC`: The libraries identified by LDC
- `Wappalyzer`: The libraries identified by Wappalyzer
- `PTdetector`: The libraries identified by PTdetector
- `comment`: Optional comment

`result_diff_set.csv` @ The detection result of PTdetector under different settings.
- `domain`: The domain name
- `rank`: The domain rank
- `url`: The home page url under the domain
- `ground truth`: The ground truth library loaded on the web page
- `auto_5_<size limit>`: The detection result of PTdetector under a given `<size limit>` (depth limit is 5)
- `time_5_<size limit>`: The average detection overhead (ms) of PTdetector under a given `<size limit>` (depth limit is 5). For each web page, we run the detection five times and calculate the average value.

#### Note

In our dataset, we use the string with format <libname> @ <version> : <score> ! <depth> to represent the library identified by detectors. For example, string jQuery@3.6.3:99.8!1 means that jQuery (v3.6.3) is identified with a score of 99.8 at the first layer of the web page pTree.

