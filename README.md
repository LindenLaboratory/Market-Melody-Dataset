# What is Market Melody?
Market Melody is a dataset focused on finding a profitable pattern between the concentrations of various natural gases (Carbon Monoxide, Nitrogen Dioxide and Ammonia) in the air of rural areas of the UK and UK Feed Wheat Futures + UKA Futures. The thesis is simple:

- When farmers are harvesting wheat or other crops, emmissions in rural areas should go up
- The harvesting process should happen at similar dates nationally, and to ensure accuracy the program can be run in multiple rural areas simultanously or at the same times of different years, so this should be able to predict in some effect a change in UK wheat futures
- Additionally, the level of emmisions may affect the UKA Futures Market as this is a market that is directly correlated with pollution
  - UK politics have a far greater effect on this however so we will taking on a market neutral position whenever we trade this, for example if we believe pollution will go up we will buy UKA Futures and sell EUA Futures simultaniously
- So, by tracking these concentrations, we can:
  - Track harvesting times to profit from UK Feed Wheat Futures (increased Nitrogen Dioxide from Combine Harvesters)
  - ... to profit from UKA futures (...)
  - Track fertilising stages to profit from UK Feed Wheat Futures (increased Ammonia from fertilisers)

## What is the Market Melody Dataset?
This repository contains the programs that were used to make the dataset in the [Programs Folder](Programs) and instructions for how to use them in [EXECUTE.md](EXECUTE.md). The program should be run for at least **1-3 months** in order to attempt to form some kind of pattern. Once this has been done, the resulting **dataset.csv** file can be analysed for patterns.

The [**dataset.csv** file already calculated](data.csv) has been trained for **6 months**. See [DATASET.md](DATASET.md) for more detail on the dataset and the patterns found.

## How does the program work?
The Market Melody Dataset is calculated using custom software in conjunction with the [Borealis network](https://github.com/LindenLaboratory/Borealis/tree/main). Several computers are put under the control of an instance of the network and a program is sent using the **code:.** prefix. This program will iterate through a list of commands where it will get price data from all 4 assets we are investigating and send the data back to the _Conductor_. The more computers, the more Data Per Unit Time (DPUT), with the network working with as low as one computer running but with a very low DPUT and a maximum of 5 computers connected per Borealis instance (multiple networks can be connected together and run in conjunction - see [EXECUTE.md](EXECUTE.md) for more detail - for even higher DPUT) for very high DPUT. We would recommend a minimum of 4 computers connected together, one for each asset we are tracking, for an optimum price to DPUT ratio.
