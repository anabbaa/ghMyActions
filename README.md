# ghMyActions

# composite

- you can make it in another reposoitory or in the existing project
- add folder name it actions in the same level of workflows folder under it another folder inside the last one a yml file and in composite action you only need this one file this file must name action
- note you do not need get code action because this action sjould be triggered after get code from reposoitory
- here we do not have events
- name it the in the same level add description then in the same level add runs inside runs add using add to it as a value composite then in the same value add steps the add shell key add to it a shell value
- use it as before in uses key reference to the path position of subfolder only
- inputs - to use input add key after description inputs in the same level of description then inside add a varable from your choice inside it add description required value for required if set to true means user must gives a value and to be sure your app still working there is default field so add to it value true inide double quote - then add if to the step you want to turn of caching by users add context inputs. name of the variable inide inputs == true here we apply it to cavhing so we will add it to install dependienc< step by adding if inputs. name of the variable != true - to use it in the main file under where you want to use it under uses key add with key inide it add your variable which you define under inputs in your action gives it a value if false so caching will be stopped for this job
- output - add it in the same level of input then inside it a variable from your choice inside it description key and value key to add value to it using custom expression inside it steps. then id of the step then . ourputs then . name of variable you named in the following step in echo command in your targeted step
  -inside the same step we will use echo to set variable and assign to it he value of inputs. then name of your variable inside inputs - finally in your main file zo aceess output make a step first give and id to the step which uses the action then run echo with expression steps.id you have named in the step which uses action then .ouputs then. name of your variable inside it

# javascript

- make another folder iinside action inide it we will make two files action.yml and main.js
- you will navigate in your terminal to your js directory then npm init npm install
- then you will install @actions/core @actions/github @actions/exec
- then import them in main.js
  -note: node_modules folder in js action folder must not be ignored because custom js action must have all the codes to run successfully
- note: you should change .gitignore file dist folder to be only root /dist because action file need dist in its node_modules folder to run cuccessfully
