# Echo Robot Picklist Maker

This notebook automates the process of generating picklists for the Echo Robot. The Echo Robot dispenses strands by the specified nanoliter volume. An auxiliary plate is required for the the final solution. Well position `I10` is chose as default, which can be modified on-need basis.

Buffer and scaffold are placed in the last two wells of the last plate. For example, if there are a total of 2 plates in use and the last well position of the second plate is P04, then the buffer and scaffold will need to be deposited on P05 and P06 respectively.

### Installing Dependencies

A minimum set of dependencies is required to run the notebook. To skip installation process, download the notebook and upload to [datahub.berkeley.edu](datahub.berkeley.edu). Otherwise, make sure a version of the `pandas` library is installed on the local computer. See [installation instructions](https://pandas.pydata.org/docs/getting_started/install.html).

### Running Picklist Maker

Run all block in the notebook. To create a picklist, 1) provide the <ins>path to the plate spec</ins> supplied by your DNA synthesis company, 2) <ins>solution in moles</ins>, 3) <ins>solution in volume (liters)</ins>, and 4) <ins>buffer dilution in moles</ins>. Additional options are available, like staple-scaffold ratio and type of scaffold; the default parameters for these are 10:1 and M13mp18 respectively.

**Example:**

```
picklist_maker = PickListMaker(["~/Downloads/example_plates1.csv", "~/Downloads/example_plates2.xlsx"], 10e-09, 50e-06, 10e-3)
picklist_maker.picklist_df
```

![alt text](https://github.com/tilabberkeley/echo_picklist_maker/blob/master/sample_picklist.png?raw=true)

### Export to CSV and Excel

Run `picklist.save_to_csv("__your_file_path__")` to export the picklist to a csv file.

Run `picklist.save_to_excel("__your_file_path__")` to export the picklist to a xlsx file.

