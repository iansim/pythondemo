# Example Package

This is a simple example package. You can use
[Github-flavored Markdown](https://guides.github.com/features/mastering-markdown/)
to write your content.



Follow below URL to create package:
https://www.mssqltips.com/sqlservertip/6802/create-wheel-file-python-package-distribute-custom-code/
https://timothybramlett.com/How_to_create_a_Python_Package_with___init__py.html

==============
create .pypirc

[distutils]
index-servers =
    nexus

[nexus]
repository: http://192.168.1.84:8081/repository/pypi/
username: xxx
password: xxxxx

====================
chmod 600 $HOME/.pypirc


python3 setup.py bdist_wheel
check-wheel-contents dist
twine upload --repository nexus  hive-0.0.1-py3-none-any.whl


#Install 

option 1. pip install --trusted-host 192.168.1.84 http://192.168.1.84:8081/repository/pypi/packages/hive/0.0.1/hive-0.0.1-py3-none-any.whl

option 2. 
add  http://192.168.1.84:8081/repository/pypi/packages/hive/0.0.1/hive-0.0.1-py3-none-any.whl to requirements.txt

pip install -r requirements.txt
