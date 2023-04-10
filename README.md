# Malicious Software Packages Dataset

<p align="center">
  <img src="./image.png" height="400" />
</p>

This repository is an **open-source dataset of <span id="num-samples">954</span> malicious software packages** (and counting) identified by Datadog, as part of our security research efforts in software supply-chain 
security. Most of the malicious packages have been identified by [GuardDog](https://github.com/DataDog/guarddog).

Current ecosystems:
- PyPI

## Usage

Malicious samples are available under the **[samples/](samples/)** folder and compressed as an encrypted ZIP file with the password `infected`. The date indicated as part of the file name is the 
discovery date, not necessarily the package publication date.

You can use the script [extract.sh](./samples/pypi/extract.sh) to automatically extract all the samples to perform local analysis on them. Alternatively, you can extract a single sample using:

```
$ unzip -o -P infected samples/pypi/2023-03-20-pydefender-v1.0.0.zip -d /tmp/
Archive:  samples/pypi/2023-03-20-pydefender-v1.0.0.zip
   creating: /tmp/2023-03-20-pydefender-v1.0.0/
```

## License

This dataset is released under the Apache-2.0 license. You're welcome to use it with attribution.

You can cite it using:

```
@misc{OpenSourceDatasetMaliciousSoftwarePackages, 
    month     = Mar,
    day       = 20,
    date      = 2023,
    journal   = {Open-Source Dataset of Malicious Software Packages},
    publisher = {Datadog Security Labs},
    url       = https://github.com/datadog/malicious-software-packages-dataset, 
}
```

Malicious software packages provided as part of this repository may contain legitimate, licensed code. In that case, the applicable license is the one of the original package, indicated in the metadata of its `setup.py` file.

## Disclaimers

* This repository contains actively malicious software that was published by threat actors. Do not run it on your machine.

* This dataset may suffer from selection biais, as it was mostly identified by a single ruleset ([GuardDog](https://github.com/datadog/guarddog)). As such, it may not accurately represent the landscape of software supply-chain security malware.

* Some of the packages in this dataset are very similar. As of March 20st 2023, we estimate that the dataset contains around 50 clusters of highly similar packages. One of the clusters is very 
large (more than 500 packages highly similar to [this one](./samples/pypi/2023-03-12-rawrequest-v2.19.zip)), which might skew the dataset.

## FAQ

### Are you maintaining this dataset?

We will be regularly adding new packages to the dataset.

### How do you know these packages are malicious?

Every single software package included in this dataset has been manually triaged by a human.

### How are you clustering these packages?

At the time, we did not make available the clustering algorithm we use internally to group similar samples and ease analysis. If you have interest, please reach out at securitylabs@datadoghq.com - 
we'll be happy to talk!

### Do you accept contributions? 

At the time, the repository is not accepting contributions. However, if you'd like to share an interesting finding with us, reach out at securitylabs@datadoghq.com!
