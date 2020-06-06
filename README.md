# June 4 Lab Session 
1) SL Command<br />
sudo apt install sl<br />
sl<br />

2) Reverse a String using rev command<br />
rev

3)To monitor system health<br />

vmstat 1000 > vmstat1.data<br />
filename= "/root/Desktop/Lab/vmstat.data"<br />
tail -f $filename |<br />
while read $line do<br />
if [ (cat vmstat1.data | grep "swap")>0 ]<br />
then<br />
echo "Some rogue process has consumed massive amounts of memory"> swap.txt<br />
fi<br />
if [ (cat vmstat.data | grep "r")>1 ]<br />
then<br />
echo "Some process are waiting to execute"> runqueue.txt<br />
fi<br />
if [ (cat vmstat.data | grep "cpu")>1000 ]<br />
then<br />
echo "CPU usage is more"> cpu.txt<br />
fi<br />


grep “swap”- the swap should always be zero if it’s not then some process has consumed massive memory. That will be monitored in this line<br />

grep “r”- the running queue is constantly above process 1 it indicates the system is slow and some process is waiting to be executed. That will be monitored here.<br />

Grep “cpu”- it indicates the CPU usage of the system. If the CPU usage is more it will be monitored and will
alert in this line.

