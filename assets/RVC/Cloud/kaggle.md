---
icon: chevron-right
order: 1000
---
 
``Last update: Oct 23, 2024``

***
:::content-center
<img src="../kaggle-img/kaggle.png" alt="image" width="710" height="auto">        
:::

## ‎ 
## Introduction  
- Kaggle is a cloud platform for using AI apps, powered by virtual machines with powerful GPU's.     

- It's a great alternative for training RVC voice models through the cloud, since it has the best GPUs.

!!!danger
You only get 30 free GPU hours per week.
!!!
    
***
###### ‎   
## How to Setup   
###### ‎   
#### 1. <u>Set up account.</u>
a. Start by making an account [here](https://www.kaggle.com/account/login?phase=startRegisterTab&returnUrl=%2F).

   <img src="../kaggle-img/kaggle-sign-in.png" alt="image" width="575" height="auto">

b. Verify your acount with a phone number so you can turn on the "internet" option.  

 <img src="../kaggle-img/kaggle-phone.png" alt="image" width="575" height="auto">    
 
***‎   
######
#### 2. <u>Clone notebook and setup.</u>
a. Go to [Hina's mainline notebook](https://www.kaggle.com/code/hinabl/mainline) and click "Copy and Edit"

   <img src="../kaggle-img/kaggle-copy.png" alt="image" width="200" height="auto"> 
        ‎                 ‎     
b. Under session settings in the sidebar turn on "internet". Make sure persistance is on for both files and varibles.

   <img src="../kaggle-img/kaggle-Internet.png" alt="image" width="450" height="auto">     
‎  
c. Turn on T4 X2 GPUs in accelerator.           

   <img src="../kaggle-img/kaggle-gpu.png" alt="image" width="" height=""> 
d: (Optional) Turn on headless mode so you can run so you can run the GPU on all sessions and save your progress. Go to the top right and click "Save version" then open the advanced dropdown.
!!!warning Warning
Your runtime will continue draining when you're not running any cells with this option on. 
!!!
<img src="../kaggle-img/kaggle-pers.png" alt="image" width="" height=""> 

***
###### ‎   
#### 3. <u>Ngrok.</u>
a. Scroll down to the fifth cell and you should see a section where you put your ngrok token. If you dont have a ngrok acount sign up [here](https://ngrok.com/).       
‎       
     2. Once you have an acount you can authenticate your ngrok tunnel agent here: https://dashboard.ngrok.com/get-started/your-authtoken   
‎       
b. put the Ngrok token in the quotation marks like so:

   <img src="../kaggle-img/kaggle-ngrok.png" alt="image" width="430" height=""> ‎   

‎!!!warning Warning               
There is a monthly limit rate with Ngrok so dont be supprised if training is suddenly interrupted.
!!!

***
###### ‎   
#### 3. <u>Starting the Cells.</u>
a. From top to bottom execute all the cells. With first being:

 <img src="../kaggle-img/kaggle-1.png" alt="image" width="430" height=""> 

b. The second cell will take ~5 minutes to load.

<img src="../kaggle-img/kaggle-2.png" alt="image" width="430" height=""> 
- when its finished it will look like this:
<img src="../kaggle-img/kaggle-fin.png" alt="image" width="430" height=""> 

c. Run the third cell.

<img src="../kaggle-img/kaggle-3.png" alt="image" width="430" height="">

d. Once you run the final cell it will give you three links.

<img src="../kaggle-img/kaggle-4.png" alt="image" width="430" height=""> 

RVC url is to open RVC's gui.
File url is to open Imjoy Elfinder gui.
Tensorboard is to open the Tensorboard.

***
###### ‎   ‎
:::content-center
#### `You have reached the end.`

[!badge variant="info" size="xl" corners="pill" icon="paper-airplane" iconAlign="right" text="Report Issues"](https://docs.ai-hub.wtf/rvc/#contributions)
:::
