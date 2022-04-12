
## Running on Viking HPC (York)

Running the calibration model can take a lot of computer processing time. To speed this up you can run on a HPC.
The instructions below are for the Viking HPC at York University.

### Accessing the Viking HPC.

1. Create an account at https://wiki.york.ac.uk/display/RCS/Viking+Quick+Start+Guide.
Ask the project lead for the account code.

2. Follow the instructions for **Login into Viking**.

3. Setup SSH key

Follow the instructions here: https://github.com/sbland/python_for_modellers_guides/blob/main/using_version_control.md#authorization-https-or-ssh

4. Load the required software
Run the following
```
# Setup python environment and install dependencies into the environment
module load anaconda
source activate base
conda create --name pyDO3SE python=3.8
conda load pyDO3SE
pip install git+ssh://git@github.com/SEI-DO3SE/do3se_post@RELEASE
```

Check it is working by running `python -m do3se_post.cli calibration --help`

5. Activate your environment
To load the required software run the following:
```
module load lang/Anaconda3
source activate base
conda activate pyDO3SE
```
It is recommended to add the above into a bash script that can then be ran when you log back in.

6. Setup the project directory as you would locally (See Use Cases below). This should be inside the following location: `~/scratch`. You can create sub directories here if needed.

You will need to make bash scripts editable with `chmod +x FILENAME`.

You will also need to add Viking instructions to the top of the bash file. See below for example:

```sh
#!/bin/bash
#SBATCH --account=INSERT_ACCOUNT_ID
#SBATCH --time=03:20:00
#SBATCH --cpus-per-task=8
#SBATCH --mail-type=END,FAIL
#SBATCH --mail-user=INSERT_EMAIL_HERE
#SBATCH --mem=4gb
#SBATCH --job-name=do3se_calibration

...

# rest of bash script
```

Adjust the time to match the expected run time of the model.

7. To run the script run `sbatch SCRIPTNAME`.
You can then check on it's progress with `squeue -u $USER`

### Troubleshooting

#### Files saved in windows can cause issues on linux...
To fix a file run:
  `sed -i -e '$a\' FILENAME`
and windows carriage returns with:
`dos2unix FILENAME`
