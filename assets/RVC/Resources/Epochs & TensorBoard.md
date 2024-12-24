---
icon: chevron-right
order: 6000
visibility: private
---

``Last update: Dec 12, 2024``   
***
###### ‎
:::content-center
## Epochs
:::     
- "Epoch" is a unit of measuring the training cycles of an AI model.     

- In other words, the amount of times the model went over its <u>[dataset](https://docs.ai-hub.wtf/rvc/resources/datasets/)</u> and learned from it.         
###### ‎ 
#### *:icon-chevron-right: How many epochs should I use for my dataset?*
- There isn't a way to know the right amount previous to training. It depends on the size, length & quality of the dataset.

- If you aim towards a quality model, it's not convenient to input a semi-arbitrary amount of epochs, as it makes it prone to underfitting/overtraining. (explained later)

- So it's best to use TensorBoard. WIth it you can determine **exactly** for how long you should train. (explained later) 
###### ‎ 
#### *:icon-chevron-right: Do more epochs equal a better model?*
- It doesn't, since using a disproportionate amount will overtrain the model, which will affect the quality of it.             
***
###### ‎ 
:::content-center
## Overtraining
:::
###### ‎       
- In the field of AI, is when an AI model learns its <u>[dataset](https://docs.ai-hub.wtf/rvc/resources/datasets/)</u> too well, to the point where it centers too much around it & starts replicating undesired data.

- The model performs very well with data of the dataset, but poorly with new data, as it has lost its ability to replicate anything that deviates from it.

- It happens when the model is trained for **too long**/is too complex. So to avoid this, RVC users use a tool called ***TensorBoard***.
***   
:::content-center
<img src="../tensorboard-img/1.png" alt="image" width="350" height="auto"> 

###### ‎
## TensorBoard
:::   
###### ‎
- TensorBoard is a tool that allows you to visualize & measure the training of an AI model, through graphs & metrics.

- It's specially useful for determining when to stop training a voice model, since with it you can detect when the <u><u>[overtraining</u>](https://docs.ai-hub.wtf/rvc/resources/epochs--tensorboard/#overtraining)</u> point begins.    

- Because of this, TB is the most convenient tool for RVC users for perfecting a voice model.     
***
###### ‎
### :icon-chevron-down: Installing & Opening

!!!success
For <u>[RVC Disconnected</u>](https://docs.ai-hub.wtf/rvc/cloud/rvc-disconnected/) users, ignore this, it opens up by itself when you start training.
!!!

###### ‎       
1. Download this file & move it inside RVC's folder. Ensure the file path doesn't contain spaces/special characters.
  
    [!file](./tensorboardfiles/TensorVENV.bat)    
###### ‎
2. Now execute it. It will open a console window & create some folders inside RVC.    
    - If you get the `Windows protected your PC` issue, click <u>**More info**</u> & **Run anyway**.         
‎   
3. Once it's done, your default browser should open with TensorBoard app.           
‎  
    - If it doesn't, copy the address of the console at the bottom, and paste it in your browser.       
    Said address will say "**https://localhost**" followed by some numbers.     
    ‎  
    <img src="../tensorboard-img/11.png" alt="image" width="500" height="auto">

***
###### ‎
### :icon-chevron-down: Usage Guide
    
+++ Simple Guide
###### ‎     
#### :icon-chevron-down: <u>SETTING UP</u>
***
- Open TB & begin training in RVC.     

    - If you get the ``No dashboards are active`` issue, select `SCALARS` in the top right corner dropdown.

        <img src="../tensorboard-img/17.png" alt="image" width="230" height="auto">‎    
‎       
- First ensure **auto-refresh** is on, so the graphs update constantly.    

    Click the gear (:icon-gear:) in the top left corner & turn on **``Reload data``**.      
    You can always manually refresh with the refresh symbol (🔄) in the top right.  
            
    <img src="../tensorboard-img/2.png" alt="image" width="280" height="auto">
       
    ‎       
- Go to the `SCALARS` tab.      
        ‎       
        <img src="../tensorboard-img/12.png" alt="image" width="280" height="auto">     
        ‎        

***
#### :icon-chevron-down: <u>GRAPH</u>
***
- #### In the left panel:  
    1. Activate `Ignore outliers in chart scaling`.  

    2. Set **Smoothing** to ``0.987``.     

    3. Select your model in the `Runs` section below. The models you tick will show in the graphs. (untick `/eval` if you want)        
    ‎       
    <img src="../tensorboard-img/18.png" alt="image" width="240" height="auto">‎      
‎       
- In the search bar, type "**g/total**". This will be the graph you'll monitor.        
    ‎   
        <img src="../tensorboard-img/19.png" alt="image" width="390" height="auto">‎        
‎    
‎  
- Each graph has three buttons in the corner:       
    - Left one is for going **fullscreen**.       
    - Middle one to **disable** Y axis, for a fuller view.       
    - And the right one is to **center** the view.      
        ‎       
        <img src="../tensorboard-img/15.png" alt="image" width="300" height="auto">‎    
‎       
- To **zoom** in & out the graphs, press the ALT key + mouse wheel. Remember to center the view after moving around, and after the graph updates.
***
 #### :icon-chevron-down: <u> MONITORING</u>
***
- Now let the training go for some time.  

- You'll detect **OT** (overtraining) when the graph hits the **lowest point**, then stay **flat**/**rising** indefinitely.  
    ‎       
     **<u>Example of OT:</u>**
        
    <img src="../tensorboard-img/10.png" alt="image" width="370" height="auto">‎     
    ‎    
- There will be various low points, one after the other, so don't get too anxious if it's OT or not. You can always use a previous checkpoint either way.

- If it reaches a low point, let it run for **longer** until it's **very clear** it's OT.

- When you detect OT go into the search bar and look for `mel`, 

    <img src="../tensorboard-img/mel.png" alt="image" width="500" height="auto">‎

- Then zoom out & lower the smoothening to 0. Then look for low points named local minima.

    <img src="../tensorboard-img/min.png" alt="image" width="600" height="auto">‎    

- Then over your mouse over the local minimas and take note of the step counts. Find all of the epochs connected to those step counts and then use them all to find the one that sounds best to you.

> If you want you can just use the lowest mel point.

+++ Advanced Guide ‎     
#### :icon-chevron-down: <u>Other Graphs</u>
***

#### `FM` Feature Matching: 
FM shows how well the generator is able to make synthetic data that has similar features to the dataset.

If the graph is decreasing that indicates that the generator is able to make audio that has similar features to the dataset.

> you can think of this as how well the model can match timbral, spetial, temporal characteristics. 
***

#### `KL` Kullback-Leibler: 
KL makes the generator create similar distribution of latest variables to real data. The KL loss ensures that the generator is not just memorizing real data but it's learning to capture the underlying patterns in the data. 

If the graph is decreasing that shows that the generator is making audio with similar distribution of latent variables to real data.

> You can think of this as how well it can replicate the speakers style. 
***

#### `Mel` Mel Spectrogram: 
 The mel spectrogram loss compares both the real and synthetic mel spectrograms. This loss encourages the generator to produce audio that sounds similar to the dataset.

 If the graph is decreasing that shows that the generator is producing audio with similar spectral distribution to the dataset.

 > you can think of this as clarity / fidelity.
***

#### `d/total` Discriminator Loss: 
d/total shows how well the discriminator is able to differentiate between real and generated audio. 

If the graph is decreasing that means the discriminator is becoming better at distinguishing between real and synthetic data which usually means that the generator is producing realistic audio. 
***

***
#### :icon-chevron-down: <u>Mel Images</u>
***
 While looking through the Tensor Board you may come across `slice/mel_gen` and `slice/mel_org`. 
#### slice/mel_gen: 
Is a mel spectrogram view of audio that the generator created in attempt to make it match `mel_org`.
<img src="../tensorboard-img/mel_gen.png" alt="image" width="700" height="700">‎ 

***

#### slice/mel_org:
Is a mel spectrogram view of audio from your dataset. 
<img src="../tensorboard-img/mel_og.png" alt="image" width="700" height="700">‎ 
***
#### Spotting Mode Collapses:
Another way of spotting is by using the Mel images as shown above. 

- A mode collapses is when RVC trys to learn silence. Here is an example of what the mel image looks like when RVC grabs a silent segment or a mute file. 

<img src="../tensorboard-img/mode.png" alt="image" width="700" height="700">‎ 

***


###### ‎
:::content-center
#### `You have reached the end.`

[!badge variant="info" size="xl" corners="pill" icon="paper-airplane" iconAlign="right" text="Report Issues"](https://docs.ai-hub.wtf/contributions/)
:::
