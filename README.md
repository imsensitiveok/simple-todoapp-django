# simple-django

In this lab we are going to run a simple Django application, and make a minor change to it.

The main purpose of this lab is to familiarize yourself with the different components of a simple Django application, and to give you some experience setting up a local development environment.

Submit the lab by committing your changes to this README as well as to the Django application, and pushing those changes to the remote repository.

Note that the lab computers may have vim as a default editor for commits if you are using git on the terminal. Vim can be scary. I recommend using nano. You can ensure you are using nano by running this command: `git config --global core. editor "nano"`

## Steps to get this django app running on your own PC

1) Open a terminal and navigate to the folder you want to create your project in (e.g. `cd ~Documents/Code`)
2) Clone this repository with `git clone https://github.com/Carleton-BIT/simple-todoapp-django.git`
3) Open the repository with PyCharm. You can do this by going file->open and selecting the cloned folder called `simple-todoapp-django`
4) Configure your project interpreter. Go to file->settings, and selecting Python Interpreter under `Project: simple-todoapp-django`, and clicking Add Interpreter->Add Local Interpreter
![screenshot for adding interpreter](readme_assets/add-interpreter.PNG)
5) Choose the default settings and click OK
![screenshot for virtualenv settings](readme_assets/confirm-interpreter.PNG)
6) Then, you can install dependencies using `pip install -r requirements.txt`
7) Create a run configuration:
![edit run configs](readme_assets/edit-run-configuration.png)
8) Configure it to run manage.py with the parameter runserver:
![finished run config](readme_assets/finished-run-configuration.png)
9) Create a file called `.env` in the simple-todoapp-django folder
10) Generate a secret key by running `python -c 'from django.core.management.utils import get_random_secret_key; print(get_random_secret_key())'` in the terminal. Copy the output.
11) Edit `.env` (created in part 9) with a text editor like notepad, and add a line that says `SECRET_KEY="your-secret-key-here"`. Paste the output from part 10 into 'your-secret-key-here'.
12) On the terminal, navigate to `simple-todoapp-django` and run `python manage.py migrate`
13) Run the server by clicking the play button for the run configuration you set up
14) Navigate to 127.0.0.1:8000! Your app should load.

## Lab instructions

1) Once you've set up the app, demonstrate that the application is running to your TA by navigating to http://127.0.0.1:8000
2) Find the terminal that displays live server logs. It will initially display something that looks like this
```
System check identified no issues (0 silenced).
September 21, 2024 - 19:53:51
Django version 4.2.16, using settings 'lecturefivedemo.settings'
Starting development server at http://127.0.0.1:8000/
Quit the server with CTRL-BREAK.
```
3) When you access the root endpoint (http://127.0.0.1:8000/) you get output that looks like `[21/Sep/2024 19:53:53] "GET / HTTP/1.1" 200 527`. What output do you get when you add a task? Edit this file (README.md) and paste the output below this question.
[23/Sep/2024 17:40:43] "POST /add/ HTTP/1.1" 302 0
[23/Sep/2024 17:40:43] "GET / HTTP/1.1" 200 683
[23/Sep/2024 17:40:43] "GET /static/css/styles.css HTTP/1.1" 304 0

4) Edit views.py so that the server [prints out](https://www.w3schools.com/python/ref_func_print.asp) "task added" to the terminal when a task is added
done!
5) Edit templates/index.html so that the server shows a thumbs up emoji when a task is completed and a thumbs down when a task is incomplete. Note that right now, there is no functionality to mark a task as complete
👍
6) Commit and push your changes using git to submit your lab
done!