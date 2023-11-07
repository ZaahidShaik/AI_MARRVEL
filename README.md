<p align="center">
  <img width="50%" align="center" src="https://raw.githubusercontent.com/LiuzLab/AI_MARRVEL/main/docs/images/logo.v1.png" alt="logo">
</p>
  <h1 align="center">
  AI-MARRVEL
</h1>

<p align="center">
  <a style="text-decoration:none">
    <img src="https://img.shields.io/badge/AI_MARRVEL-v1.0.1-blue.svg"/>
  </a>
  <a href='https://ai-marrvel.readthedocs.io/en/latest/?badge=latest'>
      <img src='https://readthedocs.org/projects/ai-marrvel/badge/?version=latest' alt='Documentation Status' />
  </a>
  <a style="text-decoration:none">
    <img src="http://img.shields.io/badge/Preprint-DOI:10.2139/ssrn.4465963-lightgreen.svg"/>
  </a>
</p>

**AI-MARRVEL (AIM)** is an AI system for rare genetic disease diagnosis.  

It takes as input patient VCF and phenotype (formatted with HPO) to predict the causal variant(s).    
In making prediction, it takes variant annotation from [MARRVEL](https://marrvel.org/) database and more, 
and generates **prediction score** + **confidence score** as output.  


You can use AI-MARRVEL from our [website](https://ai.marrvel.org/) or follow the [documentation](https://ai-marrvel.readthedocs.io/en/latest/) to run locally.



## Quick Start

### Install required data dependencies
AIM utilizes various databases for variant annotation, all of which have been compiled and made available for user download.  
  
We use Globus for data accessing [here](https://app.globus.org/file-manager?origin_id=6810458e-b702-423f-9f0c-070c1691482d&origin_path=%2F)

### Get the software
AIM is released as a Docker image for easy distribution. To get it:
```
docker pull chaozhongliu/aim-lite:latest
```

### Run with your sample
```
docker run -v <Path to VCF File>:/input/vcf.gz \
           -v <Path to HPO file>:/input/hpo.txt \
           -v <Path to downloaded database>:/run/data_dependencies \
           -v <Path to output folder>:/out \
       chaozhongliu/aim-lite /run/proc.sh [Sample ID] [Reference genome: hg19/hg38] [Memory Limit (G)]
```

## License
AI-MARRVEL is licensed under GPL-3.0. You are welcomed to use it for research purpose.  
For business purpose, please contact us for licensing.


## Disclaimer
- Some of the data and software included in the distribution may be subject to third-party constraints. Users of the data and software are solely responsible for establishing the nature of and complying with any such restrictions.
- AI-MARRVEL provides this data and software in good faith, but make no warranty, express or implied, nor assume any legal liability or responsibility for any purpose for which they are used.
