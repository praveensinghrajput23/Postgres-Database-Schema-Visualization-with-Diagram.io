# dbdiagrams 

this tool helps you quickly generate beautiful database/ER diagrams for your postgres db schema :
- the script auto-generates the code by detecting postgres db schema
- this code([sample](sample_output)) can be then copy pasted onto an online tool called [dbdiagram.io](https://dbdiagram.io/d)


### setup
required : [python3](https://docs.python-guide.org/starting/install3/linux/), [pip3](https://linuxize.com/post/how-to-install-pip-on-ubuntu-18.04/)

(NOTE: in case your ```/usr/bin/python``` doesn't point to anything then just run ```sudo ln -s /usr/bin/python3 /usr/bin/python``` and if you've multiple versions and your python is pointed to python2 and not python3, please use python3/pip3 instead of python/pip in all the steps and change first line of generate_code to ```#!/usr/bin/env python3```


1. git clone https://github.com/nsingla/dbdiagrams.git

2. cd dbdiagrams

3. (optional) - use python virtual environment :
```bash
python -m venv env
source ./env/bin/activate
```

4. install pre-requisite installation for psycopg2 (you could also install postgresql, otherwise libpq-dev and python-dev work):
```bash
sudo apt-get install libpq-dev python3-dev 
pip install -r requirements.txt
```

### settings.conf ```Common``` parameters
- conn_string : this is a database connection string setting
- table_schema : default set to public
- exclude_views : true/false to include/exclude views in the diagram
- exclude_tablenames_like : a comma separated list - if any of the table contains one of these text - it will be excluded, leave empty if nothing needs to be excluded 
- output_filepath : this is the file where the output code will be saved into


### generating the code
- update all the ```Common``` parameters carefully in settings.conf
- run ./generate_code
- copy the generated code from the output file and visit dbdiagram.io [website](https://dbdiagram.io/d), once on the diagram page - paste it onto the code panel on the left. This should generate the diagram, make sure all the info is as desired - specially the references/table relationships. 
- you can screenshot the diagram and save image file or you can create an account if you like the tool (i've no affiliation) !
