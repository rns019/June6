# June 4 Lab Session 
1) SL Command
sudo apt install sl
sl

2) Reverse a String using rev command
rev

3)To monitor system health

vmstat 1000 > vmstat1.data
filename= "/root/Desktop/Lab/vmstat.data"
tail -f $filename |
while read $line do
if [ (cat vmstat1.data | grep "swap")>0 ]
then
echo "Some rogue process has consumed massive amounts of memory"> swap.txt
fi
if [ (cat vmstat.data | grep "r")>1 ]
then
echo "Some process are waiting to execute"> runqueue.txt
fi
if [ (cat vmstat.data | grep "cpu")>1000 ]

then
echo "CPU usage is more"> cpu.txt
fi


grep “swap”- the swap should always be zero if it’s not then some process has consumed massive memory. That will be monitored in this line

grep “r”- the running queue is constantly above process 1 it indicates the system is slow and some process is waiting to be executed. That will be monitored here.

Grep “cpu”- it indicates the CPU usage of the system. If the CPU usage is more it will be monitored and will
alert in this line.

