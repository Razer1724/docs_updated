---
icon: chevron-right
order: 1000
---
 
``Last update: Oct 21, 2024``

***
:::content-center
<img src="../kaggle-img/kaggle.png" alt="image" width="710" height="auto">        
:::

## ‎ 
## Introduction  
- Kaggle is a cloud platform for using AI apps, powered by virtual machines with powerful GPU's.     

- It's a great alternative for training RVC voice models through the cloud, since it has the best GPUs.    
***
###### ‎   
## How to Setup   
###### ‎   
#### 1. <u>Set up account.</u>
a. Start by making an account [here](https://www.kaggle.com/account/login?phase=startRegisterTab&returnUrl=%2F).

   <img src="../paperspace-img/3.png" alt="image" width="575" height="auto">

b. Verify your acount with a phone number so you can turn on "internet" option.      
 ‎   
######
#### 2. <u>Clone notebook and setup.</u>
a. Go to [Hina's mainline notebook](https://www.kaggle.com/code/hinabl/mainline) and click "Copy and Edit"

   <img src="../paperspace-img/5.png" alt="image" width="200" height="auto"> 
        ‎                 ‎     
b. Under session settings in the sidebar turn on "internet". Make sure persistance is on for both files and varibles.

   <img src="../paperspace-img/6.png" alt="image" width="450" height="auto">     
‎  
c. Turn on T4 X2 GPUs in accelerator.           

   <img src="../paperspace-img/7.png" alt="image" width="" height=""> 
d: (Optional) Turn on headless mode so you can run so you can run the GPU on all sessions and save your progress. Your runtime will continue draining when you're not running any cells. 

***
###### ‎   
#### 3. <u>Ngrok.</u>
a. Copy this, paste it in the Terminal and hit enter:      
‎       
b. Once it's done installing, open the `paper.ipynb` file.

   <img src="../paperspace-img/8.png" alt="image" width="650" height=""> ‎      
‎       
c. Execute the `INSTALL EVERYTHING` cell.

   <img src="../paperspace-img/9.png" alt="image" width="430" height=""> ‎   
‎               
d. Once that one is done, execute the ``START GUI`` one.    
Then you can start using Mangio.

   <img src="../paperspace-img/10.png" alt="image" width="430" height=""> ‎ 
‎               
‎       
!!! <u>Notes about training:</u>
**1.** To create the dataset folder, open the notebook, right click the ``Mangio-RVC-Fork`` folder, click `New folder`, name it `dataset`, and put your dataset there.    
‎       
**2.** If you get an error when you click ``Process data``, don't worry, it's a visual glitch. Keep working as usual.   
!!!
‎           
### Opening TensorBoard
To run TensorBoard while using RVC you'll have to do it on a separate terminal.         

a. Go to your notebook and open a new terminal by clicking the Terminal symbol ( :icon-terminal: ) on the right.

b. Then introduce this:

        cd/notebooks/Mangio-RVC-Fork
        make TensorBoard
        
***
###### ‎   
:::content-center
## Comparison With Colab
:::
###### ‎
>###### ‎
>:::content-center
><img src="../paperspace-img/11.png" alt="image" width="600" height=""> ‎   
>:::
>‎         
>‎       
>*"The main difference lies in the model training process, as the GPUs available on Paperspace are more powerful.         
‎       
You can achieve training speeds that are approximately 3 times faster compared to Colab, which translates to saving a significant amount of time.               
‎       
So, if you were to train a model with a dataset that takes around an hour and a half (1:30) on Paperspace, it would take approximately three and a half hours (3:30).       
‎       
On the other hand, on Colab, it might take around 7 hours (without considering the account switching)."*         
>***
>:::content-right
>``- Picture & quote by LollenApe``    
>:::     
>‎        
>‎    

***
###### ‎
:::content-center
#### `You have reached the end.`

[!badge variant="info" size="xl" corners="pill" icon="paper-airplane" iconAlign="right" text="Report Issues"](https://docs.ai-hub.wtf/rvc/#contributions)
:::
