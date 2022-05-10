# Azure immersion workshop notes
## Tips
- It is recommended to use private/incognito window in the browser
- Make sure your tab is able to access to your clipboard, click "allow" when this message is prompted

<img style="margin-left: 50px" src="./assets/Screen%20Shot%202022-05-10%20at%2011.26.50.png" alt="drawing" width="500"/>

- The search bar is your friend. It is faster to navigate to resources in Azure Portal by using search bar other than the side menu

<img style="margin-left: 50px" src="./assets/Screen%20Shot%202022-05-10%20at%2013.01.14.png" alt="drawing" width="500"/>

- You can maximize your cloud shell window to by clicking the icon here:

<img style="margin-left: 50px" src="./assets/Screen%20Shot%202022-05-10%20at%2013.02.38.png" alt="drawing" />

- Use `Ctrl + Shift + v` to paste in the lab environment. If unsure what's registered in the virtrual machine chipboard, you can open a notepad in the VM and paste the content to the notepad to verify it.

- You can split your instruction to a separate window by clicking `Split Window` link at the bottom right corner of the panel

<img style="margin-left: 50px" src="./assets/Screen%20Shot%202022-05-10%20at%2013.30.16.png" alt="drawing" width="500"/>

## Notes:
- Exercise 2
  - Task 3 Create GitHub Personal Access Token
    - Step 3: Ignore this:

    <img style="margin-left: 50px" src="./assets/Screen%20Shot%202022-05-10%20at%2013.09.06.png" alt="drawing" width="500"/>
    
  - Task 5
    - Step 2:
      -  Use `Application Id` for `<client id>`
      -  Use `Secret Key` for `<client secret>`
     -  Step 8: to save and quit vi editor
        -  press `ctrl + [` to switch to vi normal mode
        -  type `:wq` and hit Enter key to save and quit vi
     -  Step 10: `PAT` is your github personal access token which you created in Task 3
     -  Step 11: ssh to build vm: `ssh  adminfabmedical@fabmedical613071.centralus.cloudapp.azure.com`. You can find yours on "Environment Detail" -> "Azure Credentails tab"

  - Task 7: 
    - Step 1 and 2: You can ignore all the warning from docker build commands (if there is any)


- Exercise 3
  - Task 1
    - Step 5, Make sure uncheck `Require SSL`, your IP could be different with the IP in the screenshot
    - Step 15, You may get error but you can continue the lab exercise

    <img style="margin-left: 50px" src="./assets/Screen%20Shot%202022-05-10%20at%2013.39.33.png" alt="drawing" width="700"/>
- Exercise 4
  - Task 1
    - Step 1, replace `{id}` with the id from previous step's output
    - Step 2, replace `SUFFIX` with your own uniq suffix

  - Task 2, you may see the error below, but you should be able to continue the lab exercise
    <img style="margin-left: 50px" src="./assets/Screen%20Shot%202022-05-10%20at%2013.47.32.png" alt="drawing" width="700"/>

    - Step 8: update the container image, replace `[LOGINSERVER]` with your Azure container register name (at line 25)
    - Step 20: If you see `No command 'code' found, did you mean`... error, this mean you executed the script on your build agent VM, you should exit the VM SSH session and execute it in your cloud terminal. And make sure you update the container image at line 25
  
    - Step 22, if you error `You must be logged in to the server (the server has asked for the client to provide credentials)`, please perform step 1 and 2 in Task 1, Exercies 2 to login AZ and get your Azure Kubenetes credentials
      - az login
      - az account show
      - az account list
      - az account set --subscription {id}
      - az aks get-credentials -a --name fabmedical-SUFFIX --resource-group fabmedical-SUFFIX
  - Task 3
    - Step 3: make sure to update container image at line 25


- Exercise 5
  - Task 5, You will need to execute the script on the build agent vm as mongo cli has been installed there
    - Step 7: vi editor:
      - press `i` to insert mode in which you can edit the file
      - `ctrl + [` to escape from the insert mode and swith to normal mode in which you can use hjkl to navigate arround
        - `h`: left
        - `l`: right
        - `j`: down
        - `k`: up
      This script is for load test to the cosmos db, you can skip this one if you want

  - Task 3, make sure you exit from the build agent first
    -  Step 4, `code app.js` to open the file in editor
    -  Step 5-11, you can use `ctrl + /` to uncomment the content in the editor

- Exercise 6
  - Task 4
    -  Step 5: you can use `ctrl + d` select and edit multiple instance/cursors 
       - You can find the region in the kubenetes url:

       <img style="margin-left: 50px" src="./assets/Screen%20Shot%202022-05-10%20at%2014.58.43.png" alt="drawing" />