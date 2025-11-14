# faucet-config
This repository has become the main configuration repo for MeshGuard, not just the faucet controller.

Multiple other repositories are needed to run the whole project. These should be cloned in the parent directory of this repo.
To setup the Faucet/MUDManager:
```
├── faucet              Cloned from [https://anonymous.4open.science/r/faucet-CA68/README.rst](https://anonymous.4open.science/r/faucet-CA68/README.rst)
├── faucet-config       This repo
└── mud-manager         Cloned from [https://anonymous.4open.science/r/mud-manager-5CDF/README.md](https://anonymous.4open.science/r/mud-manager-5CDF/README.md) 
```

To build the demo application for the nRF52840 or nRF52833 to act as FTDs or MTDs: see [https://anonymous.4open.science/r/mt-cli-C008/README.md](https://anonymous.4open.science/r/mt-cli-C008/README.md)
This repo overrides the normal openthread library with my version: [https://github.com/openthread/openthread](https://github.com/openthread/openthread)
This openthread fork includes the DistriMUD functionality for sharing MUD URLs inside a Thread network.


This is a clone of the normal openthread border router repo, but with a MUD Forwarder service.
For running the demo environment, build the docker container image for the border router. Be sure to update the name of the image in the `./scripts/run_demo.sh` script with your name.


The directory sturcture of this repo is as follows:
```
.
├── docker              Contains docker overrides for Faucet as well as the MUD Manager.
├── mudfiles            Contains MUD files used by the mudfileserver (see docker-compose.yaml), rebuild to update fileserver container.
├── scripts             Contains setup scripts for demo environment, see ./scripts/README.md for further explanations.
│   └── experiments     Contains scripts for running my experiments, see ./scripts/experiments/README.md for further explanations.
└── volumes             Directory containing volumes mounted in Faucet, set environment variable FAUCET_HOME=/PATH/TO/REPO/faucet-config/volumes
    ├── etc
    │   └── faucet      Contains config files for Faucet, see ./volumes/etc/faucet/README.md for further explanations.
```
