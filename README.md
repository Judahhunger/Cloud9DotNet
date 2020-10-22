# Cloud9DotNet
Working with IDE on AWS Cloud9, The browser IDE code from anywhere.

Setting up Cloud9 for .Net Console App. Using Ubuntu server.


Setting Up Cloud9 for .Net Console App. 
once you create environment, defualt unbuntu evo free is fine.

*Steps/List to install .net core 3.1 sdk and runtime. YouTube exmp: if dotnet --version is not found.

*********AWS example:
 1.) sudo apt -y update

 2.)  wget https://dot.net/v1/dotnet-install.sh   -----(.Net Core SDK installer script download to env)
 3.)  sudo chmod u=rx dotnet-install.sh (make the installer script executable by current user.)
 4.) ./dotnet-install.sh -c Current (downloads and installs the .NET Core SDK.)
 5.)  vi ~/.bashrc   (*Open the .bashrc file for editing by using the vi command.)
 6.)  *Type G and move to the line that starts with export PATH useing the right arrow key to move to the end of that line. switch to insert mode by pressing the i key. (display should see -- INSERT --- appear.)
 7.) *press right arrow key and the press Enter twice, then type 'export PATH=$HOME/.dotnet:$PATH' by itself at the end of the file and save by pressing escape.  Then :wq to write and quit.
 8.) . ~/.bashrc (Load the .NET Core SDK by sourcing the .bashrc file.)
 9.) dotnet --help (to make sure .NET is LOADED)
 10.) rm dotnet-install.sh (to get rid of the SDK installer script if you don't want to keep it.)

***CREATE A .NET CORE CONSOLE APPLICATION PROJECT

make a directory, mkdir directory_name
Create a .Net Core console app project. Run the .Net core CLI with. 
 dotnet new console -lang C#

____________________________________________________________________________________________
*build the project and its dependencies into a set of binary files, including a runnable application file. Then you run the application.

1.) On the menu bar choose Run, Build System, New build System. replace the code with.
 { 
	"cmd" : ["dotnet", "build"],
	"info" : "Building..."
 }
2.) Save and type in '.NET Core.build'  ^Folder should be '/.c9/builders'   and then save.
3.) with Program.cs file displayed in the editor, choose Run, Build System, .NET Core. Then choose Run, Build.

4.) Create a runner for .net, open Run Run With, New Runner. and replace with 
{
  "cmd" : ["dotnet", "run", "$args"],
  "working_dir": "$file",
  "info" : "Running..."
}
5.) save and type in '.NET Core.run'  ^Folder should be '/.c9/runners' and save.
6.) with contents of the Program.cs file displayed in editor, choose Run, Run Config, New Run Config. - in the [New]-idle tab, choose Runner:auto, and choose .NET Core (on far right of Command menu). - in Command box, type hello 5 9
7.)choose run and check that out put is correct.

NEXT STEPS on STEP 5 at https://docs.aws.amazon.com/cloud9/latest/user-guide/sample-dotnetcore.html

 

