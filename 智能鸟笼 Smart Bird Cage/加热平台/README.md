这个项目的来源是因为有一款看起来不错的产品, K&H 加热站杆，有不少好评，个人感觉也确实有用。但因为该产品温度不稳定的原因，评论两级分化，差评一般分为（不够热，摸上去没感觉；过热，鹦鹉低温烫伤）。作为用户，我也不知道他实时温度是多少。<br>

The idea of this project comes from an exsiting product, K&H thermal perch, which is a pretty good idea IMO. However, its reviews have been either extremely good or extremely poor, mostly due to its inconsistent temperature. In the low star reviews, consumers are complaining either product is not warm enough, or product is too hot that it burned a concure's feet. As a user, I don't know what the temperatue is at any given time. So, good idea, but I want sth a little bit better.

<img src="https://user-images.githubusercontent.com/1382734/216394509-73d11a27-817f-42f5-8a2e-8797cb25eaf5.png" width="1200" height="450">


--------------------------------

期间也注意到过这个:<br>
<img src="https://user-images.githubusercontent.com/1382734/216998655-c9d83915-6c71-48a7-b8c1-56735950deed.png" width="350" height="450"> <br>
这个有2个选择，硅胶套或者不锈钢套。卖家也表明不锈钢保温效果不如硅胶，但鹦鹉会咬硅胶，所以是消耗品。<br>

<img src="https://user-images.githubusercontent.com/1382734/216999318-a674b5d0-ee39-4c8e-a9f2-b08e823a353e.png" width="850" height="450"> <br>
这个是我做完了我的平台后才发现的。<br>

---------------------------------------


我的初衷是基于做一个温度更稳定，并能知道温度，调整温度的产品。<br>
So the purpose of this project is to make sth that is thermally more stable, can display templeratrue and can be adjusted.<br>

这个项目开始时，我自以为很简单，随便拼一下就行。所以也没有很多的计划。但做的过程中，以及做完后，发现还是忽略了很多东西。<br>

从做体重计的时候，我错误的得出了“鸟更喜欢站杆”这个结论，以至于我一开始纠结于做一个加热站杆。<br>

A. 我一开始想做的是水暖站杆（想法来源于家里地暖），水的特性确实能让温度很稳定。<br>
<img src="https://user-images.githubusercontent.com/1382734/217002036-5b0dd2e6-5b75-4d1b-b261-a3caefaf3fbb.png" width="1200" height="600"> <br>

如图，站杆上一个水流入口，一个水流出口。水流有一个外置/内置水泵带动，水在水箱内（大概保鲜盒的大小）被加热棒加热。
经过2轮人为测试，我就发现几个问题：<br>
1. 两根水管带出来，很粗，不便于安装<br>
2. 热损耗很大，20C室温的情况下，30W的加热棒也不能让站杆到40C。<br>
3. 尽管我能控制水箱温度（~45C),但是站杆实际温度多少，我也不知道。<br>

于是，我改了一轮，将水箱，加热棒，温度计，直接集成到站杆里。<br>
<img src="https://user-images.githubusercontent.com/1382734/217003808-a069c635-3005-4b4c-8c07-f2ff547b5dfe.png" width="1200" height="600"> <br>
站杆将由SLA打印，螺纹套以及密封胶确保密封性。经过人为测试，以及轻度鸟测试，效果还不错。<br>
但是发现了一个问题：<br>
   -- 3D打印出来的站杆很滑，鸟抓不稳。<br>
于是我尝试了一些方案：<br>
1. 粗砂纸打磨 <br>
2. 模拟树皮的粗糙纹路打印在站杆上 <br>
3. 套一层东西（网球吸汗带/硅胶/皮带,etc) <br>
测试了几种之后，发现套一层东西效果最好，但这样他也变成了消耗品。并且套与站杆之间有缝隙，可能导致导热不良。<br>
在想了一段时间后，决定放弃 3D打印站杆这个方案。<br>

B. 虽然放弃了3D打印水暖站杆，但是可以直接尝试改良K&H的 PTC加热站杆方案。理论上我只需要加一个温度计，PID闭环控制，就没问题了。<br>
采购了一根直径8mm，20cm长的加热棒，导热胶/凝胶，温度计，宇电516PID控制器，以及直径28-30mmm的花椒木（对于凯来说，其实20-25mm就可以了）。 <br>
在制作的过程中发现（用8mm梅花钻 钻一个20cm深的洞），尽管我使用了工具固定，我的洞依然会有或多或少的错中心。加上树枝本身就不是直的，导致加热棒在某些地方，会靠近树枝的外径。在假设之后我能改进工艺的前提下，我先做了一轮测试。<br>
我发现了几个问题：<br> 
1. 尽管加热棒是20W满载运行，依然需要挺久才能从25C 到 40C <br>
2. 在树枝的不同点，温差明显很大。我评估了一下，认为就算改进工艺也不一定能解决问题。 <br>

这时候我认识到这个问题没我想的那么简单，我就回到SW画了点简单的模型，算了一些导热系数，做了一些简单的仿真。 <br>
因为木头是纤维组成，并且我的使用环境下，热传导方向是垂直于纤维方向，直接导致热传导系数特别低，所以加热距离每差1mm，温度能差好几度。 <br>
在做了几轮仿真，对比仿真与现在的数据。最后决定放弃花椒木站杆这个方案。 <br>

这时候我的选项就只有平台了。<br>
基于前面的经历，我这次仔细画了图，确认了材料的厚度，仿真，中间每几步也做了测试。最终恒温平台做出来了。<br>

<img src="https://user-images.githubusercontent.com/1382734/217471071-b9672fb8-0658-4307-a17a-899f1349b5e7.png" width="800" height="600"> <br>


<img src="https://user-images.githubusercontent.com/1382734/217888187-a3d0e99a-4426-4465-834d-2915c4b31577.jpg" width="800" height="500"> <br>


在用了几个月后，我比较满意，总体有几个发现：<br>
1. 现在是冬天，鸟每天都会在上面呆一会时间，特别是睡午觉以及刚洗完澡，他非常喜欢这个加热站杆。<br>
2. 基本无维护。在做木制鸟笼的时候发现，木头上了清漆之后，鸟对木头的啃咬欲望几乎为0。但这个不能构成结论，数据太少。<br>
   用PE/亚克力/其它板材其实也是不错的选择。<br>
3. 唯一的一个不满：鸟不在的时候，温度很稳定。鸟如果在上面活动，温度有时候会过高，但因为我这个有温度监控，他会自动停止加热。<br>
   我稍微研究了一下，初步判断是可能因为PTC加热片的原因。<br>
在鸟笼空调项目里的PTC模块，它好像会自检。比如如果它额定功率是200W，启动瞬间它会在100W左右，然后加热到200W。<br>
而加热平台这个PTC没模块，它有冲击功率，比如如果它的额定功率是20W，但每次启动瞬间他会飙到50-75W。<br>
我也可以在花点时间，调试PID。感觉自己建模调出PID有点难，因为我对这个PTC加热板的参数了解的非常少; 并且耗时。<br>

虽然还有一些问题，但在这一阶段，我已经比较满意了，有过热保护（里面也有几层冗余的软件逻辑），我也不是很担心。<br>





