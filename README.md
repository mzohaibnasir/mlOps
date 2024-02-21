# mlOps

: best practices to put ML models in production.

Different stages of ML projects:

1. Designing the problem
2. Train model
3. Deploy

MLOPS is a set of pratices for automating all these steps

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
