# SeqCmp
to find a reference(s) for CompMap 
编译：
在Unix系统下，拥有gcc编译器即可编译得到执行文件
依次输入：make 与  make clean 即可得到执行文件SeqCmp

使用过程中，占用最大内存略大于输入的文件大小。

命令使用方式：
输入 ./SeqCmp 可获取帮助
具体使用方式有：
 SeqCmp  db1.fasta  db2.fasta
db1.fasta 和 db2.fasta 是genome文件

 SeqCmp  -D  db_dir
加入参数-D (或-d)，则可输入包含genome（.fasta文件）的文件夹


运行结果：
屏幕输出： 

两行提示信息——finished read！<INT>
                number of genomes :　<INT>
其中，INT为genome数量

第三行：NO：<fileNO.> reference genome: <genome title>
其中，fileNO是参考基因组的文件序号，title是其文件头


第四行以后：<fileNO> <genome title> totle base <INT1> matched base <INT2>   <FLOAT>
其中，fileNO及title是除参考基因组以外的genome的序号及文件头，INT1是该文件总的碱基数目， INT2是被比较基因组与参考基因组重复的碱基数目， FLOAT是INT2/INT1

每份输入的genome都会作为一次参考基因组

 SeqCmp -I -D db_dir
 SeqCmp -I db1.fasta db2.fasta
加入参数 -I(或 -i)则将输出结果输入到report.txt文件中，若report文件已存在，则将保留原有信息，将新的report结果添加到文件末尾。
