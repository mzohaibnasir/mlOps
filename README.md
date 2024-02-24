# mlOps

: best practices to put ML models in production.

Different stages of ML projects:

1. Designing the problem
2. Train model
3. Deploy

MLOPS is a set of pratices for automating all these steps

# ML Project Lifecycle

● scoping
● Define project: what you are working on. X->Y
● Data acquiring
● Define data & establish baseline
● Label and organize data
● Train Model
● Select & train Model
● Reform error analysis
● Deployment
● Deploy in production
● Monitor and maintain system
● Update data distribution

# Setting up ENV

    ssh -i ~/.ssh/mlopsKeypair.pem ubuntu@54.197.195.218
    # username@publicIP

To automate this in /.ssh/config
put

###############################################################"""
Host mlops-zoomcamp
----HostName 54.197.195.218 # need to be updated wverytime you start instance becuase its public ip
----User ubuntu
----IdentityFile /home/zohaib/.ssh/mlopsKeypair.pem
----StrictHostKeyChecking no
"""################################################################

Now we can just do like `ssh mlops-zoomcamp`

"""

# Experiment Tracking

Important concepts

● ML experiment: the process of building an ML model
● Experiment run: each trial in an ML experiment
● Run artifact: any file that is associated with an ML run
● Experiment metadata: information about an ML experiment like the source
code used, the name of the user, etc.

What’s experiment tracking?

Experiment tracking is the process of keeping track of all the relevant information
from an ML experiment, which includes:
● Source code
● Environment
● Data
● Model
● Hyperparameters
● Metrics

"""
