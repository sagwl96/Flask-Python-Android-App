# Flask-Python-Android-App
A basic Flask server and an accompanying Android App written using kivy in Python and built using buildozer

##Note
When using 'requests' library in the python code and building using 'buildozer', simply mentioning 'requests' in requirements of the buildozer.spec file is not going to work. In my case the build was successful but the app crashed as soon as it was started. This has something to do with the recipe of requests. In order to successfully build in such a situation, please do the following (github.com/kivy/python-for-android/issues/1072): 

Go to the folder where buildozer.spec file is. Use Ctrl+H to show hidden files and go to .buildozer -> android -> platform -> python-for-android-new-toolchain -> pythonforandroid -> recipies
Once inside, delete 'requests' and 'idna' folders if they exist.
Next, add 'requests','urllib3','chardet','certifi','idna' to the requirements line in the buildozer.spec file before building (add them without the single quotes).
