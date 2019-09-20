# falab
Automatically exported from code.google.com/p/falab
free algorithm lab, support digital processing, audio/video algorithm and so on

Totally free algorithm source code using C language, the idea is using independent basis module to form a big project. the basis module including basis digital processing algorithm(windows,lpf,hpf,resample..), audio analysis/synthesis module(fft,mdct analysis/synthesis...), audio encoding/decoding(AAC,mp3...)

falab是用Ｃ语言写的算法库，目标是为音视频编解码、人工智能、网络传输等提供基础算法模块，并让代码尽可能跨平台使用和二次迭代开发，支持嵌入式开发和ＤＳＰ实现，此库里的代码也提供由模块集成的编解码库，近期目标是音频开发，支持常见的算法模块(fft,mdct,resample,fir，低通滤波，高通滤波，多相滤波）和ＡＡＣ及mp3编解码。

写这个库的初衷是发现现有的很多开源算法特别是音视频编解码算法中的每个模块都很难被复用，每个不同的编解码版本都是由不同的人写的，里面的基础算法模块完全不同，有的效率高有的效率低，有的注重了算法本身的效率而忽视了代码本身结构和调用函数的效率；有的注重了整个代码框架，而忽视了将算法融入框架后不可分割复用。　本人移植了很多编解码算法，对于现有的ffmpeg中的算法既爱又恨，爱是因为它太强大太丰富了，能有的你都可以找到，恨是因为它底层的编解码算法想要单独隔离出来要费很大的功夫，因为它对框架和很多共用文件的耦合性太强，是紧耦合系统，要剔文件是真是牵一发而动全身，有的好剔有的则很难。

所以，基于此才想写一个模块化的算法库，希望在不久的将来这个库能发展壮大。　在算法库中，module是最基本的概念，任何一个module是单独开发并有测试用例的，且本身尽量不与任何系统耦合，只提供接口，且尽量不用全局变量防多线程调用，开发细节还有很多，在此不赘述，有意愿参与开发的人可以和我联系 luolongzhi@gmail.com

目前的库中可以支持以下功能： fir滤波器，支持低通、高通、带通、带阻，文件中自带了常见的窗函数和卷积函数 fft模块，效率尚可，支持定点算法 mdct模块，里面支持三种算法（原始公式，fft快速算法，常用的N/4点fft快速算法），也支持定点，不过定点的代码用N/4点的快带算法误差较低，　有兴趣的可以开发N/8点的fft 快速算法 resample模法，支持插值、抽取、任意比重采样 音频处理分析综合例子模块 ...

本人擅长的是音频开发和人工智能，对于视频不是很了解，所以如果有视频开发方面厉害的朋友可以参与进来，但考虑到代码质量，所以还是有以下要求： １. 有长期的视频算法、人工智能或网络传输开发经验，你可以是专长于matlab仿真或Ｃ代码实现 ２. 有长期的意愿进行开发与维护，并遵循现有的代码风格中和规范（风格和规范肯定是要不断改进，希望更厉害的人提意见），谢绝来来就走的人 ３. 此算法库完全是免费的，开发也遵循ＧＮＵ，完全是自愿在业余时间开发，无薪水 ４. 希望参与的人最好先发点你写的代码，说说你的经历 ５. 希望能互相交流提高代码的模块化程度、稳定性、可移植性、可复用、可迭代开发性
