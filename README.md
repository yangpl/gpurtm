gpurtm
===========
Name of the program: 2D prestack GPU-based RTM using effective boundary saving

Name  of the manuscript: RTM using effective boundary saving: A staggered grid GPU implementation

Author(s) details:  

	Pengliang Yang(1), Jinghuai Gao(2), Baoli Wang(3)

	Address: 	Institute of Wave and Information, 
			School of Electronic and Information Engineering, 
			Xi'an Jiaotong University, 
			Xi'an,  P.R. China
	
	Email(s):	(1) ypl.2100@gmail.com
			(2) jhgao@mail.xjtu.edu.cn
			(3) pooly1981@163.com

Notice: There is Matlab code to compute the staggered grid finite difference coefficients with varying even-order (NJ=2N).
Assume you are finding the 10-th order finite difference coefficients. In principle, you should run the following commands in Matlab command window!

	format long
	NJ=10;
	c=staggered_fdcoeff(NJ)


Instructions of the program:
	1. To test the GPU-based RTM codes, you need CUDA well-installed;
	2. You also need development version of Madagascar installed;
	3. To reproduce the Marmousi example, rename SConstruct1.txt as SConstruct and 
		run 'scons view' in that directory;
	4. To reproduce the Sigsbee example, rename SConstruct2.txt as SConstruct and 
		run 'scons view' in that directory;

The codes has already installed in the Madagascar development version, the cuda codes lie in $RSFSRC/user/pyang and the example scripts lie in $RSFSRC/book/pyang/gpurtm. Make sure the Internet is connected when run SConstructs because the marmousi and sigsbee models need to be downloaded.
	
Caution: Due to limited GPU resource on my laptop (NVS5400M GDDR3 2048M), I have to store a large amount of boundaries using pinned memory, which may degrade the speed performance a lot! It means that I have to run hours to obtain the images. If you have enough GPU resource, you may not need to do so! The speedup will improve a lot!  

Enjoy this code!
