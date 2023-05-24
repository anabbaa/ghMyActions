# ghMyActions

# composite

- you can make it in another reposoitory or in the existing project
- add folder name it actions in the same level of workflows folder under it another folder inside the last one a yml file and in composite action you only need this one file this file must name action
- note you do not need get code action because this action should be triggered after get code from reposoitory
- here we do not have events
- name it then in the same level add description then in the same level add runs inside runs add using add to it as a value composite then in the same value add steps then add shell key add to it a shell value
- use it as before in uses key reference to the path position of subfolder only the path should begin with thw root ./.guthub/...
- inputs - to use input add keyword inputs with the sam level of description then inside add a varable from your choice inside it add description required value for required if set to true means user must gives a value and to be sure your app still working there is default field so add to it value true inside double quote - then add if to the step you want to turn off caching by users add context inputs. name of the variable inside inputs == true here we apply it to caching so we will add it to install dependienc< step by adding if inputs. name of the variable != true - to use it in the main file under where you want to use it under uses key add with key inide it add your variable which you define under inputs in your action gives it a value if false so caching will be stopped for this job
- output - add it in the same level of input then inside it a variable from your choice inside it description key and value key to add value to it using custom expression inside it steps. then id of the step then . ourputs then . name of variable you named in the following step in echo command in your targeted step
  -inside the same step we will use echo to set variable and assign to it he value of inputs. then name of your variable inside inputs - finally in your main file zo aceess output make a step first give and id to the step which uses the action then run echo with expression steps.id you have named in the step which uses action then .ouputs then. name of your variable inside it

# javascript

- make another folder iinside action inide it we will make two files action.yml and main.js
- also here you will name it then describtion then runs: keyord inside run you will have using: kexword here we will have nodejs as value with same level we will have main; as a keyword and we will have as a value the main.js file in our directory
- you will navigate in your terminal to your js directory then npm init npm install
- then you will install @actions/core @actions/github @actions/exec
- you can add input or output here also with the same level  description add inputs: as a a keyword inside it choose a name for your variable inside it description then required whter it is true or false
- with the output add outputs: keyword with same level of inputs keyword after description keyword then inside it a variable from your choose inside it description keyword you do nothave value keyword here then let us go to our example go down to see its practising 
- to use it go to another job in your  workflow file inside it runs-on keyword and have operating system as a value then  with same level  keyword steps inide it name a stepl then keyword uses: and a path to your main.js file
- here you must add another step name it then  keyword uses: as a value action to get the code of your repository and it must be befor the code to import or uses: main.js file  
- then import them in main.js
  - note: node_modules folder in js action folder must not be ignored because custom js action must have all the codes to run successfully
- note: you should change .gitignore file dist folder to be only root /dist because action file need dist in its node_modules folder to run successfully
- github object:
  - method getOktoKit to send request to github RestAPI
  - contexts method which offers some value of githubaction contexts object
- in aws s3 example
  - after defining main.ls fule with three inputs
  - in main.js file in function run we will use function that we already imported core.get input and pass to it two agruments first one name of our variable as a streng the second one object property as require its value either true or false in our example bucket true because we define it true in our action.yml file the bucket-region variable we will make it require true because we need this value
  - second step how to upload files:
    - use object exe.exe which is to execute a command in a command line then i pass to this method a streng cli command which is already installed in ubuntu image  the command will be aws s3 sync then folder then url which is s3://then name of our bucket then - -region then name of the region
  - then write your code in action.yml file name your step in deploy job then keyword uses: as a value the path of main.js file then keyword env in the same leve inside it two variables for acess key and secret key which we will save in our secret object ion our repository then back to the same level of env and write the keyword with inside it our two variable of input here bucket name of our bucket in AWS and dist-filder it should be ./dist
  - now for the output after defining it in our action.yml file we navigate to main.js file under deploy code create a variable put inside it "htto://s3: then bucket name then.s3-webseit then  region name then .amazonaws.com" after that i will use object core with its method getoutput it will accept two arguments the first one the name of our variable in our ouputs in our action.yml file the second will be our variable the last one after that to use it i beed another step in our workflow file after deploy step name it then run a command echo like life url: then custom expression which will be steps,deploy.outputs.name of our variable in output in action.yml file and deply here it is id in our deploy step 
