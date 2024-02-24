# mlOps

: best practices to put ML models in production.

Different stages of ML projects:

1. Designing the problem
2. Train model
3. Deploy

MLOPS is a set of pratices for automating all these steps

# ML Project Lifecycle

● scoping
----● Define project: what you are working on. X->Y
● Data acquiring
----● Define data & establish baseline
----● Label and organize data
● Train Model
----● Select & train Model
----● Reform error analysis
● Deployment
----● Deploy in production
----● Monitor and maintain system
--------● Update data distribution

# Deployment Challenges

● Concept drift & data drift
----● Concept drift
--------●mapping from X->Y changes i.e. price of houses goes up in inflation
----● Data drift
--------● X changes i.e. exposure of images in test dataset changes
● SE issues
----● Realtime vs batch predictions? base on time
----● Cloud vs Edge/browser
----● Compute issues (CPU/GPU/memory)
----● Latency / throughput(Query per second)
----● Loggings
----● Security and privacy issues

# Deployment Patterns

● Shadow mode: compare model with human judgment
_----● ML system shadows the human and runs in parallel
_----● ML system is not used for any decision making process in this process
● Canary deployment
_----● roll out(launch) to a small fraction of traffic initially i.e. 5%
_----● monitor system and ramp up traffic gradually.
● blue Green Development
_----● Send images to both old and new model service
_----● if anything goes wrong, you will easily rollback to old model service

(human) -> shadow mode -> AI assistance -> partial automation -> full automation(fully AI)

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

MLFLOW :open source platform for ML lifecycle
----● `mlflow ui --port 8080 --backend-store-uri sqlite:///mlruns.db`

"""
