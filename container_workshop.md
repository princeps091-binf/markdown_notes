- container:
    - mode to share software that makes it safe, easy and scalable
        - similar to virtual machines but faster, more isolated and not as redundant
            - dynamically allocate cpu ressources through kernel
- Docker basic element = docker file (recipe)

    - needs a base: [FROM](ubuntu, Fedora, R, etc)
    - [RUN]:
        - base-specific commands to run
        - install dependencies
            - packages
            - data
    - Once written:
        - docker build -t [container-name]
    - To enter the container:
        - docker run -it [container-name]
        - to run specific commands in the container from outside:
            - docker run [container-name] [command]
        - once exited, we don't have by default access to the last instance
        - to reach previous instance:
            - docker container -ls a
        - Can also run docker with specific files attached to the container:
            - docker run -v [folder-name] -it [container-name]
                - once command ran from container can send output to desired working directory
    - Can run on hpc quite easily through slurm
    - Save container
        - "push" to docker hub
            - docker tag [image.id] [dockerhub.ID/container-name]
            - docker login
                - username + password
            - docker push [dockerhub.ID/container-name]
        - save local copy
            - docker save [image.id]
    - Run container on TSD tricky with docker
        - preffered mode = Singularity
        - can easily convert docker container to singularity with one command
        - Easiest:
            - create container with linux base and Singularity
                - then run the container
            - Already available in DockerHub
                - docker pull singularityware/singularity 