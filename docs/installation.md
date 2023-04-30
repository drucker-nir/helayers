<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-baqh{text-align:center;vertical-align:top}
.tg .tg-c3ow{border-color:inherit;text-align:center;vertical-align:top}
.tg .tg-9353{border-color:inherit;font-weight:bold;text-align:center;text-decoration:underline;vertical-align:top}
.tg .tg-7btt{border-color:inherit;font-weight:bold;text-align:center;vertical-align:top}
.tg .tg-fymr{border-color:inherit;font-weight:bold;text-align:left;vertical-align:top}
</style>

There are two ways to get started with HElayers using [Dockers](https://www.docker.com/) or directly through [Python](https://www.python.org/). 

- [The Docker option](#docker-image-installation) is recommended for new HElayers users who wish to explore the various [demos]() that HElayers provides, which may have dependencies on 3rd-party libraries such as [scikit-learn](https://scikit-learn.org/). The Docker images come with these dependencies already installed, together with C++ or Python IDE, where the users can immediately start programming some HE-based applications. 
- [The import to Python option](#importing-the-pyhelayers-python-packge) is recommended for users who already have a Python environment of choice installed and wish to simply import the `pyhelayers` package and start programming.

## Importing the `pyhelayers` Python packge

Install and import one of the following packages to use HElayers from your Python environment of choice.

<table class="tg">
<thead>
  <tr>
    <th class="tg-baqh" colspan="10"><span style="font-weight:bold;text-decoration:underline">Python packages</span></th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-7btt" rowspan="2">Docker image name</td>
    <td class="tg-7btt" colspan="3">Supported OS</td>
    <td class="tg-7btt" colspan="6">Supported backends (HE libraries)</td>
  </tr>
  <tr>
    <td class="tg-7btt">Linux (x86, IBM Z)</td>
    <td class="tg-7btt">MacOS</td>
    <td class="tg-7btt">Windows</td>
    <td class="tg-7btt">SEAL</td>
    <td class="tg-7btt">HeaaN</td>
    <td class="tg-7btt">HElib</td>
    <td class="tg-7btt">Palisade</td>
    <td class="tg-7btt">OpenFHE</td>
    <td class="tg-7btt">Lattigo</td>
  </tr>
  <tr>
    <td class="tg-fymr"><a href=https://pypi.org/project/pyhelayers/>pyhelayers</a></td>
    <td class="tg-c3ow">&#x2714;</td>
    <td class="tg-c3ow">&#x2714;</td>
    <td class="tg-c3ow"></td>
    <td class="tg-c3ow">&#x2714;</td>
    <td class="tg-c3ow">&#x2714;</td>
    <td class="tg-c3ow">&#x2714;</td>
    <td class="tg-c3ow">&#x2714;</td>
    <td class="tg-c3ow">&#x2714;</td>
    <td class="tg-c3ow">&#x2714;</td>
  </tr>
  <tr>
    <td class="tg-fymr"><a href=https://pypi.org/project/pyhelayerslite/>pyhelayerslite</a></td>
    <td class="tg-c3ow"></td>
    <td class="tg-c3ow"></td>
    <td class="tg-c3ow">&#x2714;</td>
    <td class="tg-c3ow">&#x2714;</td>
    <td class="tg-c3ow">&#x2714;</td>
    <td class="tg-c3ow"></td>
    <td class="tg-c3ow"></td>
    <td class="tg-c3ow"></td>
    <td class="tg-c3ow"></td>
  </tr>
</tbody>
</table>

To install a package e.g., `pyhelayers` from your command line run:

    pip install pyhelayers

??? info "If the pip Python package manager is not installed on your system use these instructions."
    First verify that [Python](https://www.python.org/) and [pip](https://pip.pypa.io/en/stable/installation/) are installed on your system:

        > python --version
        Python 3.9.2
        > pip --version
        pip 20.0.2 from /usr/local/lib/python3.8/site-packages/pip (python 3.8)

    - Goto [Python](https://www.python.org/) if it is not installed.
    - Goto [pip](https://pip.pypa.io/en/stable/installation/) if pip is not installed.

    In some cases, you may need to upgrade pip to the latest version:

        pip install --upgrade pip
    
    On Windows, some of the above commands may not work out-of-the-box. A workaround is to preface every Python command with `python -m` as follows:
    
        python -m pip install pyhelayers


## Docker image installation

### System Requirements

- A system that is capable of running a Docker container, with the necessary user privileges to run docker commands. 
- A working internet connection.

???+ warning "Do not expose the HElayers containers to unauthorized access." 
    Anyone with access to the container web interface will be able to execute code inside it. Only start the HElayers containers on platforms with controlled access.

??? info "Getting Started with HELayers - instructional setup video"
    For your convenience, an instructional setup video of how to use the Python demos of HELayers on Z systems is available [here](https://www.youtube.com/watch?v=_bEMWffloas&ab_channel=IBMResearch). The exact details are also listed in the next sections. 

    [![Fully Homomorphic Encryption](http://img.youtube.com/vi/_bEMWffloas/0.jpg)](https://www.youtube.com/watch?v=_bEMWffloas "Getting Started with HELayers")

### Docker types and supported systems

Two Docker image types are provided:

- **helayers-lab**: Provides C++ APIs. When the container is running, interactions are through the [VS Code](https://code.visualstudio.com/) C++ IDE accessed via the browser. 
- **helayers-pylab**: Provides Python APIs. When the container is running, interactions are through a [Python Jupyter](https://jupyter.org/) notebook accessed via the browser.

The tables below show the support OSs and HE backends per image.

<table class="tg">
<thead>
  <tr>
    <th class="tg-baqh" colspan="10"><span style="font-weight:bold;text-decoration:underline">C++ Docker images</span></th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-7btt" rowspan="2">Docker image name</td>
    <td class="tg-7btt" colspan="3">Supported OS</td>
    <td class="tg-7btt" colspan="6">Supported backends (HE libraries)</td>
  </tr>
  <tr>
    <td class="tg-7btt">Linux</td>
    <td class="tg-7btt">MacOS</td>
    <td class="tg-7btt">Windows</td>
    <td class="tg-7btt">SEAL</td>
    <td class="tg-7btt">HeaaN</td>
    <td class="tg-7btt">HElib</td>
    <td class="tg-7btt">Palisade</td>
    <td class="tg-7btt">OpenFHE</td>
    <td class="tg-7btt">Lattigo</td>
  </tr>
  <tr>
    <td class="tg-fymr">helayers-lab-x86-64</td>
    <td class="tg-c3ow">&#x2714;</td>
    <td class="tg-c3ow">&#x2714;</td>
    <td class="tg-c3ow">&#x2714;</td>
    <td class="tg-c3ow">&#x2714;</td>
    <td class="tg-c3ow">&#x2714;</td>
    <td class="tg-c3ow">&#x2714;</td>
    <td class="tg-c3ow"></td>
    <td class="tg-c3ow"></td>
    <td class="tg-c3ow"></td>
  </tr>
  <tr>
    <td class="tg-fymr">helayers-lab-s390x</td>
    <td class="tg-c3ow">&#x2714;</td>
    <td class="tg-c3ow"></td>
    <td class="tg-c3ow"></td>
    <td class="tg-c3ow">&#x2714;</td>
    <td class="tg-c3ow">&#x2714;</td>
    <td class="tg-c3ow"></td>
    <td class="tg-c3ow"></td>
    <td class="tg-c3ow"></td>
    <td class="tg-c3ow"></td>
  </tr>
</tbody>
</table>

<br/>

<table class="tg">
<thead>
  <tr>
    <th class="tg-baqh" colspan="10"><span style="font-weight:bold;text-decoration:underline">Python Docker images</span></th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-7btt" rowspan="2">Docker image name</td>
    <td class="tg-7btt" colspan="3">Supported OS</td>
    <td class="tg-7btt" colspan="6">Supported backends (HE libraries)</td>
  </tr>
  <tr>
    <td class="tg-7btt">Linux</td>
    <td class="tg-7btt">MacOS</td>
    <td class="tg-7btt">Windows</td>
    <td class="tg-7btt">SEAL</td>
    <td class="tg-7btt">HeaaN</td>
    <td class="tg-7btt">HElib</td>
    <td class="tg-7btt">Palisade</td>
    <td class="tg-7btt">OpenFHE</td>
    <td class="tg-7btt">Lattigo</td>
  </tr>
  <tr>
    <td class="tg-fymr">helayers-pylab-x86-64</td>
    <td class="tg-c3ow">&#x2714;</td>
    <td class="tg-c3ow">&#x2714;</td>
    <td class="tg-c3ow">&#x2714;</td>
    <td class="tg-c3ow">&#x2714;</td>
    <td class="tg-c3ow">&#x2714;</td>
    <td class="tg-c3ow">&#x2714;</td>
    <td class="tg-c3ow"></td>
    <td class="tg-c3ow"></td>
    <td class="tg-c3ow"></td>
  </tr>
  <tr>
    <td class="tg-fymr">helayers-pylab-s390x</td>
    <td class="tg-c3ow">&#x2714;</td>
    <td class="tg-c3ow"></td>
    <td class="tg-c3ow"></td>
    <td class="tg-c3ow">&#x2714;</td>
    <td class="tg-c3ow">&#x2714;</td>
    <td class="tg-c3ow"></td>
    <td class="tg-c3ow"></td>
    <td class="tg-c3ow"></td>
    <td class="tg-c3ow"></td>
  </tr>
</tbody>
</table>

??? info "Supported zSystems architectures" 
    s390x images are built to run on all zSystems architectures including Linux on IBM Z (z16 and LinuxOne III), and zCX Container Extensions.

### Installation

#### Step 1: Pull the Docker image
In your terminal pull the relevant Docker image from the IBM Container Registry to your local repository. Use the `helayers docker name` from the tables above and specify `:latest` to pull the most recent version. To specify a specific release version replace `:latest` with the version number, such as `:1.0`.

    docker pull icr.io/helayers/`helayers docker name`:latest

If the fetch is successful, it will download the image and you will now have an image in your local repository named `icr.io/helayers/'helayers docker name':latest`.  Check that this image exists with

    docker images

#### Step 2: Running the image

Once the image download is complete, `run` the image as a container in Docker.  

    docker run -p 8443:8443 -d --rm --name helayers-lab icr.io/helayers/`helayers docker name`:latest
    
This command runs the image and sets the container to be accessed via port 8443. It also gives the container a name called `helayers-lab`, which is used for finding it in the list of other running containers.

#### Step 3: Accessing HElayers and running the tutorials

- **For Python users**: 
    - Connect to the Juptyer notebook welcome page by opening a web browser on your host machine (not the docker container instance), and browse to [http://127.0.0.1:8443/lab/?token=demo-experience-with-fhe-and-python ](http://127.0.0.1:8443/lab/?token=demo-experience-with-fhe-and-python).  
    - Open (double click) the `00_Getting_Started.ipynb` notebook. It contains information about the avialable tutorials, as well as instructions on how to run them.
- **For C++ users**: 
    - Connect to the VS Code welcome page by openning a web browser on your host machine (not the docker container instance), and browse to [http://127.0.0.1:8443/ ](http://127.0.0.1:8443/).
    - Click on the application menu (three bars icon, top left), and choose *Terminal > New Terminal*
    - In the terminal change directory to `examples/<demoName>`, where the list of demos and their description is found [here](demos.md)
    - Follow the directions in the readme file of that demo.

???+ info "Running from a remote machine." 
    Remember to change the IP address `127.0.0.1` when running the web browser on a different machine other than the docker container.

