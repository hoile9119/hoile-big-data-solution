# Written by Martin Karlsson
Github : [big-data-solution](https://github.com/martinkarlssonio/big-data-solution

# BigData Solution written in Python based on Hadoop and Spark.
### Scale your data management by distributing workload and storage on Hadoop and Spark Clusters, explore and transform your data in Jupyter Notebook.

<!--
*** Written by Martin Karlsson
*** www.martinkarlsson.io
-->

[![LinkedIn][linkedin-shield]][linkedin-url]


<!-- ABOUT THE PROJECT -->
## About The Project

Purpose for this tutorial is to show how to get started with Hadoop, Spark and Jupyter for your BigData solution, deploy as Docker Containers.

![Architecture overview][arch]

## Pre-requisite
- Only confirmed working on Linux/Windows (Apple Silicon might have issues).
- Ensure Docker is installed.

## Start

Execute `bash master-build.sh` to start the the build and start the containers.

### Hadoop
Access Hadoop UI on ' http://localhost:9870 '

### Spark
Access Spark Master UI on ' http://localhost:8080 '

### Jupyter
Access Jupyter UI on ' http://localhost:8888 '

<!-- CONTRIBUTING -->
## Contributing

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/featureName`)
3. Commit your Changes (`git commit -m 'Add some featureName'`)
4. Push to the Branch (`git push origin feature/featureName`)
5. Open a Pull Request


<!-- CONTACT -->
## Contact

### Martin Karlsson

LinkedIn : [martin-karlsson][linkedin-url] \
Twitter : [@HelloKarlsson](https://twitter.com/HelloKarlsson) \
Email : hello@martinkarlsson.io \
Webpage : [www.martinkarlsson.io](https://www.martinkarlsson.io)


Project Link: [github.com/martinkarlssonio/big-data-solution](https://github.com/martinkarlssonio/big-data-solution)


<!-- MARKDOWN LINKS & IMAGES -->
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/martin-karlsson
[arch]: arch.png


# Contributing by Hoi Le At (VN)

## Update jupyter docker file
1. Add Spark into Jupyter Container to be able run spark-submit inside the container

## Note spark-submit
1. I want to use spark-submit to submit python scripts instead of using Jupyter Notebook by default. So I started to add Spark into jupyter-notebook Dockerfile
2. I ran the build command, but it seemed create another image with repository = 'None'
3. I started to do other things like:
    - Rename the repository from 'None' to 'hoile-jupyter-notebook' and run `docker compose up -d` => nothing really happend. It used the old image for jupyter notebook. I want to rename docker image by using `docker image tag image_id hoile-jupyter-notebook:latest ` but it created other image with the same id (other name). I tried to rm duplicated image by using `docker image rm image_name`. All stuffs but nothing really happened.
    - I started to use `docker compose up --force-recreate --build -d` and it updated my old image ( the image i want to rm and replace with my new built image). But it turned out updated -> so thing was basically done. LOL
4. I used jupyter-notbook alongside with VSCode to access to jupyter container and check if Spark was installed in this container and it did. 
5. I tried to run some basic bash scripts and python scripts and it worked. I even tried to use spark-submit to submit job to master link and it worked 
6. Things were basically done and I can submit my spark job to master       