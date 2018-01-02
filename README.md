<font size=5>A telegram bot based on a finite state machine
##<font size=6>Setup##
# <font size=5>Prerequisite #
<font size=4>Python 3.4.3
# <font size=5>Install Dependency#
 <pre> <code> 
<font size=4>py -m pip install transitions==0.5.0<br />
<font size=4>py -m pip install Flask==0.12.1<br />
<font size=4>py -m pip install pygraphviz==1.3.1<br />
<font size=4>py -m pip install python-telegram-bot==5.3.0<br />
</code></pre>
# <font size=5>Secret Data #
<font size=4>**API TOKEN** and **WEBHOOK URL** in app.py MUST be set to proper values. Otherwise, you might not be able to run your code.
# <font size=5>Run Locally #
<font size=4>You can either setup https server or using **ngrok** as a proxy.
<pre> <code><font size=4>ngrok http 5000
</code></pre>
<font size=4>After that, **ngrok **would generate a https URL.<br />
<font size=4>You should set **WEBHOOK URL** (in app.py) to your-https-URL/hook.<br />
# <font size=5>Run the sever #
<pre> <code><font size=4>py app.py
</code></pre>
##<font size=6>Finite State Machine##
![](https://i.screenshot.net/jrqxlsp)
##<font size=6>Usage##
<font size=4>The initial state is set to user.

Every time user state is triggered to advance to another state, it will go_back to user state after the bot replies corresponding message.

●user<br />

　○input:"ncku csie"<br />
　　　■reply:"history or professor"<br />
　○input:"test"<br />
　　　■reply:"love or personality or work"<br />
　○input:"chat"<br />
　　　■reply:"Hi!"<br />
　○input:"joke"<br />
　　　■reply:"normal or turbo"<br /><br />

●stateNCKUCSIEIntroduction<br />

　○input:"history"<br />
　　　■reply:NCKU CSIE’s history<br />
　○input:"professor"<br />
　　　■reply:List all professors<br /><br />

●state1~state42<br />

　○input:"1"~"42"<br />
　　　■reply:professor’s　introduction<br /><br />

●statePsychologicalTest<br />

　○input:"love"<br />
　　　■reply:a　psychological　test<br />
　　　　　　(choose an answer and it will go to next state which will show you result)<br />
　○input:"personality"<br />
　　　■reply:a　psychological　test<br />
　　　　　　(choose an answer and it will go to next state which will show you result)<br />
　○input:"work"<br />
　　　■reply:a　psychological　test<br />
　　　　　　(choose an answer and it will go to next state which will show you result)<br /><br />
●stateChat   <br />
　○input:"hi"<br />
　　　■reply:"How are you?"<br /><br />
●stateChat1<br />
　○input:"good"<br />
　　　■reply:"Are you single?"<br /><br />
●stateChat2<br />
　○input:"no"<br />
　　　■reply:"Congratulations!\nhttps://pbs.twimg.com/media/DB4AHDFU0AEu6G4.jpg"<br />
　○input:"yes"<br />
　　　■reply:"Ok~This is for you.\nhttps://youtu.be/WCpKhCyqmFE"<br /><br />
●stateJoke<br />
　○input:"normal"<br />
　　　■reply:show you a joke<br />
　○input:"turbo"<br />
　　　■reply:show you a joke<br /><br />
##<font size=6>Author##
<font size=4>LGY3030