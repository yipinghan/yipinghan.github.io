Background: Master degree in Audio Technology, 4-year in audio technology field, 1.5-year in the motor-dom; Be able to deal with personal at all levels effectively, to work under high pressure and different environment.
Skills: sound quality evaluation, signal processing, audio and video processing, audio algorithm

Personality: Calm and steady personality, has a sense of responsibility.
Professional Background: 1.5 years in manufacturing, 2 years in Internet and communication; Be familiar with sound quality evaluation, voice signal process, line array loudspeaker evaluation method.

Project management: Be able to pass project evaluation, Communication and process management methods to complete the integration of information resources, responsible for planning supplier needs, mining industry information, to find the characteristics and highlights of the product requirements of the supplier system.

Communication skills: Excellent team collaborators, participate in many technology industry projects, in the sound, Internet product technology, Automotive supplier system and other projects have accumulated communication skills, skilled to control the direction of communication, to achieve the purpose of cooperation, product planning, communication and coordination of strong comprehensive quality






Courses: Theoretical Acoustics, Modern Signal Processing
Experimental Psychology Method of Sound Quality Subjective Evaluation, Modern Acoustical Techniques of Measurement

2015/05-2015/11 Shanghai CanXing Cultural Media Audio Technology Supporter
Participated in the sound recording in a show “the voice of China”, resolved technical problems such as system connection for the audio signal. I applied theory to practices, and accumulated operation experience. 

2015/09-2016/01  Acoustics Lab         Trainer                    
Responsibilities: Training course was aimed at teaching the basics of acoustics and training the hearing for lab researchers to improve their professional skill. It lasted 4 months, 48 class hours in total, mainly covering acoustic phenomenon, hearing training, noise measurement, hardware use, etc. 
Results: 92% of the researchers showed significant improvement in their hearing skills after the course.

2015/09-2017/05 Acousic lab   measurement for line arrays
Description: measure the sound field in near-field and far-field, discussed the relation between results and performance. 
Responsibility:1.measure the directivity, freq-response, cover angle in near-field for line arrary loudspeaker's performance. 
2.propose the measurement methods for line array in near-field and evaluate the methods. 
According to the reasearch result we found the rules in acoustics radiation and try to estimate the radiation in far-field.


2017/07-2018/12  SGM  Delivery Engineer
Participated in messages sending service projects, meeting reservation project and user experience project which designed the product with users' requirements, coordinated resources to guarantee the functions. 
Responsibilities: 1. Got the main information according to business communication, set development plans and developed it. Provided high quality of delivery for users. 2. Also promoted the projects with videos on Wechat platform, and provided technical support for all services. 
Skills: Java, Python, Scikit-Learn technologies, etc. 
Value: These services all had high utilization.


Work performance: Got the main information according to business communication, set development plans and developed it. Provided high quality of delivery for users. Also promoted the projects with videos on Wechat platform, and provided technical support for all services. 
Skills: Java, Python, Scikit-Learn technologies, etc. 
Value: These services all had high utilization.





2018/12—NOW.  ISOFTSTONE  Audio Engineer
Be responsible for the audio detection algorithm development for audio effects. 
Responsibilities: 1. Focused on algorithm integration and audio effects evaluation. According to the requirements for audio signal, performed the development plans. 2. Based on psychoacoustics created new corresponding relation between the objective and subjective evaluations of phone use. 3. Gathered papers information in the audio field and held training regularly. Worked closely with the client and team members on issues. 

Skills: measurement skills, subjective evaluations, development skills(C , Python, Matlab). 
Value: The evaluation ability and robustness of audio detection algorithm got increased.





1.自我介绍
您好，我目前是音频工程师，本科就读于上海师范大学，主修通信工程，硕士就读于中传，主修声学。加上实习的话，有近4-5年的工作经验了，主要集中在音频领域

我目前是音频工程师，主要负责的工作内容是主客观评价体系的对应，以及测评算法的编写和集成，也有部分自动化工具实现的工作。目前求职仍想继续主客观评价的工作，想和前辈聊聊这个职位。

2.目前的主要工作
主要是负责客户方产品的音频效果测量和研发，也有自动化工具实现的工作


3.音频效果有哪些
最基础的是客观参数，除了频响，指向，响度，还要为产品的输出效果，比如杂音，卡顿，响度过大或者过小，异响（小波变换）等
主观参数也有很多，大部分还处在人主观听上，小部分可以实现算法检测，最近主要在立体声场上


9.如何实现自动化的，实现多功能评价
算法集成主要是在实现自动化的部分做的工作，要实现高效的测评工作就需要把多个算法合并到一起，能够实现给文件就能得到测评结果。
另外就是编写可移植的程序包，方便其他人使用


4.信号处理的算法集成有哪些/算法实现
频响，响度，可以直接硬件测量得到
指向可能需要费劲一些，需要自行测量得到，其他输出效果可以用算法检测

预处理 
一般会有格式的改变，长度的修改，预置信号的位置，剪裁，分段输出，修改采样率，长度

杂音 ，异响、 微小振幅检测
就是小波变换，杂音比如pop或者有规律的声音（TDD）
先用小波分解，再在分量重求 模极大值，最后在重建信号
CWT是连续小波变换
DWT是离散小波变换
SWT是平稳小波变换
在检测的过程中个，核心思想就是：二阶求导找极大值，尺度很重要，而且不同的信号可能会对应不同尺度
极大值法是小波变换找奇异值最常用的方法，而且也很简单易懂。得到信号多尺度下的分量后，主要在细节分量上找奇异值，因为扰动都会在细节分量上体现。
在计算的过程中，要注意数组求导不可超出数组范围，且求导的结果要对应正确的位置， 否则会出现数组移位，结果不准的情况。
局限性：
1.分量设置的层数因信号而异
2.该方法在突发的，有规律的异常点上的效果最好，其实这和平稳信号叠加白噪声进行检测的原理是一样的，如果在一段平稳噪声中有突发的奇异点，那么对奇异点很容易成为极大值，然而在歌曲这类信号中，或者本身信号就具有各种变化，那么对于奇异点的检测就不会特别成功，有可能就会检测到本身信号的身上，而忽略了我们所希望的噪声点上。比如下图的去噪检测，就会比比较容易得到好的结果，毕竟原始信号是很有规律性的，而高速噪声并没有过分的改变原始信号的趋势

SNR 峰值信噪比，分段信噪比
信噪比，就是= 信号能量S/噪声能量N    一般就是通过计算信号的功率谱来得到比值，当然前提是噪声不能过大，否则没有意义

THD  
总谐波失真，就是 = （高次谐波的均方根值/基波）x 100%
在已知基波的情况下，THD比较好计算，比如使用功率谱来计算能量，如果基波和谐波都需要计算的话，那么需要先知道如何计算基波和谐波。已知基波，先算功率谱，找到基波对应的PSD对应的位置，然后计算能量，默认除去基波之外的都是谐波，那么THD大致估算可以使用：（总能量-基波能量）/基波能量

响度
立体声 ITD双耳时间差，ILD双耳声强差
双耳互相关系数 IACC
NCF = 每一帧循环，计算∑左耳**右耳/squart(∑左右耳各自平方)
最大值得到IACC， ASW = 1-IACC 
低切高切频点，左右信号fft，
ILD = 20log10 (∑XL/∑XR)  根据已有的头模型参数，确定角度

降噪  谱减法
假设语音中的噪声只有加性噪声，只要将带噪语音谱减去噪声谱，就可以得到纯净语音，这么做的前提是噪声信号是平稳的或者缓慢变化的。提出这个假设就是基于短时谱（25ms），就是频谱在短时间内是平稳不变的。相减后差值如果为负值，设置一个语音的下限值beta* Pn(w），通过调整beta的值来调整这个宽带的噪声的强度
取前五帧的噪声估计，后面用信号减去，剪完之后平滑下，再返回到时域
端点检测  双门线法，短时能量值（一个较高，一个较低）和过零率（区分清浊）

可懂度 就用下面的建模得到的一个检测
MOS、PEAQ（有缺陷，只能8k，所以用的不多）
MOS-polqa算法，客观评价语音质量，和MOS评分等级建立认知模型，反应主观感知
参考信号的比例调整：参考信号现在处于一个理想的标准而衰减信号代表了回放标准。参考信号向衰减信号按比例调整以补偿标准不同所带来的影响。噪音补偿：为了解决引入了无声线性频率响应失真的测试系统中的滤波，参考信号在音高功率密度域已被部分过滤。为了进一步纠正线性失真比非线性失真影响较小这一事实，参考信号现在在音高响度域被部分过滤
原始POLQA分数由类似 MOS 的运用了 4种不同补偿的中间指标得出来的。原始 POLQA 分数通过运用一个优化 ITU-T P.863数据库组的三阶多项式映射到MOS-LQO 分
两种客观语音质量评估方法都基于感知模型，原理基本一致，主要差别在于认知模型

PESQ分值范围是-0.5～4.5，和主观MOS分值还有差距。因此P.862.1提供了一个PESQ分值向MOS分值映射的函数[7]。该映射得到的MOS-LQO分值范围是1.02～4.56
（1）感知模型
　　感知模型主要是模拟人耳的感觉器官，根据听觉的掩蔽效应将声音响度映射为巴克域响度指标[10]，然后用客观指标表述语音感知。POLQA感知模型输出的客观性指标主要有频率响应指示、噪音指示、混响指示以及三个描述语音内部差异的指标：时间-音调-响度，另外还有6个与音量/噪声/音色等有关的补偿性指标。POLQA感知模型的主要计算步骤如下：
　　1）首先设定窗口长度和语音的起止点，将音频通过FFT变换到频域，然后音高功率振幅被归一化到频率为1 kHz正弦波，声压等级为40 dB SPL的基准刻度；
　　2）语音信号从频域映射到巴克域音高功率密度的计算；
　　3）计算频率响应、噪音和室内混响的指标；
　　4）对参考信号和劣化信号进行电平、噪音等方面的补偿；
　　5）响度密集度计算，主要将音高的功率密度转换为听觉的响度密度；
　　6）内部感知差异的计算，并根据相关结果计算响度扰动密度，用于认知模型评分。
（2）认知模型
　　认知模型基于感知模型输出的扰动密度、客观性指标（频率响应指示、噪音指示、混响指示）以及6个补偿性指标计算出原始POLQA值，用一个三阶多项式再映射为MOS-LQO值。在窄带模式下，MOS-LQO分值最大为4.5，在超宽带模式下，MOS-LQO分值最大为4.75。

STOI 
1）删除静默帧；2）短时傅立叶变换（STFT）；3）三分之一倍频带分析：这是通过简单地对DFT-bin进行分组来完成的4）归一化和限幅：降级语音的归一化和限幅的时间包络表示为xj,m。5）可理解度度量：中间可理解度度量被定义为两个时间包络之间的相关系数。最后，将STOI计算为所有频段和帧上的中间清晰度测度的平均值

发音准确度，流利度，语速，音频起止时间怎么测评（公司任务，可以说一个）  
音频起止（attack）
对数上升时间(Log Attacak Time) LAT=log10(T1-T0)




6.如何提高算法评价能力？
首先提高可适用性，对多种类型的信号要适应，其次要减少操作次数，目的希望一次多检，最后要提高速度（这个经验还不是很丰富）



7.客观和主观是如何对应的

主观评价需要使用实验心理学方法进行科学的实验设计，接近心理尺度

主观评价大部分还是音乐声
主观有很多影响因素：声源，环境，换能器，听觉系统，听音方式，测量标准
音质客观评价
响度，混响时间，明晰度和清晰度（声能/混响声能），双耳听觉互相关iACC（越小越好，这样双耳信号有明显差别），空间感ASW 

语言主观评价。     
响度        
清晰度
丰满度
噪声，回声干扰

音乐主观评价。 音高响度音色 
响度
丰满感
亲切感
清晰度
整体感。融合不融合
平衡感
扩散感    柔和不柔和
空间感
噪声

评价方法有很多，排序法，对偶法，语意细分法，系列范畴法等等

多个例子
现有主观，后有客观，而且客观不能够100%替代主观，只能说提供参考，特别是对心理和情感的评价。如果想有什么需要测评的参数，一定要先做主观，准确设计主观参数，之后才能更容易将客观参数和主观对应
个人方法是，用主观实验去检测被试的主观感受，然后再和客观参数，单个或者多个进行建模，目前我只做过线性拟合的模型，R^2有0.89（芬兰PPT,每个参数都有加权，之后在合并）

掩蔽


铃声的那个也可以讲下（主要是听觉响应的人耳参数）

蓝牙客观延迟的计算


8.音乐主客观评价有哪些参数能表征
不方便多说，还在研发阶段
客观方面：尖锐度（普之心），力度（短时能量，集中程度，中位数）平衡性（左右耳频响差异）



10.培训的内容，哪些声学现象，什么培训，音质如何评价，噪声如何测量，硬件设备如何使用
声学现象：掩蔽效应，双耳效应（时间差，相位差，声级差，音色差等）
音质评价：听觉预限的测量，音高与频率，乐器掩蔽，音色的各种听辨，声音的畸变和失真听辨练习，瞬间特性，谐和性和平衡性，瞬间特性，音乐情感感知听辨等等，
黑暗，压抑，高贵，端庄，平静，着重，庄严，兴奋，优雅，愉快
噪声测量：噪声，频响，灵敏度，指向性等，阵列测量等
硬件设备：声级计，调音台，录音机，传声器，扬声器，功率放大器，声卡等





5.技术文献有哪些
主要还是在算法或者测量方法的积累上
除此之外是方法文档的赋能

11.SGM 工作内容



想问的问题
1.测评的对象是什么
2.怎么看待主观评价
3.工具平台的开发是实现什么
4.主要是处理语音还是音乐
5.机器学习的比重占多少

6.团队
