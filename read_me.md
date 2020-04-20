# Networks-Simulator-ns3 (Assignment-4)
Network Simulator ns3

# Assignment Question
Compare the performance of TCP over wired and wireless networks. Consider a topology as described below. The network consists of two TCP sources Node0 and Node2, corresponding to two TCP destinations Node1 and Node3 respectively. Node2 and Node3 come in wired domain with two routers R1 and R2 (connected by a {10 Mbps, 50 ms} wired link) between them. Both the routers use drop-tail queues with queue size set according to bandwidth-delay product. Node0 comes in domain of Base Station 1 (BS1) and Node1 comes in domain of Base Station 2 (BS2). BS1 and BS2 are connected by a (10 Mbps, 100 ms) wired link. The hosts, i.e. Node0, Node1, Node2, Node3 are attached with (100 Mbps, 20ms) links to routers or base stations (as
shown in the figure below). The sources (Node0 and Node2)) use three TCP agents (i.e. TCP Westwood, TCP Veno and TCP Vegas) to generate three different TCP flows. Study and plot the fairness index (Jain's fairness index) and throughput change when the TCP packet size is varied; all the other parameter values are kept constant. You should use the following TCP packet size values (in Bytes): 40, 44, 48, 52, 60, 552, 576, 628, 1420 and 1500 for your experiments. The throughput (in Kbps) and fairness index must be calculated at steady-state. Make appropriate assumptions wherever necessary.

# Simulation
Place the files (wired.cc & wireless.cc) in the scratch directory of your ns3 directory and execute the files using following commands from directory containing the scratch directory :

./waf run scratch/wired
./waf run scratch/wireless

It will generate wired.xml, wiredfairness.plt, wiredthroughput.plt, wireless.xml, wirelessfairness.plt and wiredthroughput.plt files.

# Plotting
Execute below commands to generate plot image for throughput vs packet size and fairness vs packet size in wired and wireless networks.
gnuplot wiredthroughput.plt
gnuplot wiredfairness.plt
gnuplot wirelessthroughput.plt
gnuplot wirelessfairness.plt

# Using Flow monitor
To process xml files, we need to search within ns3 for a parsing file.

For example, go to /home/saurabh/Desktop/ns-allinone-3.30.1/ns-3.30.1/src/flow-monitor/examples and copy flowmon-parse-results.py file to the 	location where xml file was generated (inside ns-3.30.1, here)

run the followig commands from directory containing the scratch directory :

python flowmon-parse-results.py wired.xml
python flowmon-parse-results.py wireless.xml

using python script (Matplotlib) 
flow.py which was generated manually for parsing the flowmonitor xml file

run the following commands from directory containing the scratch directory :

python flow.py wired.xml
evince results

This will generate a results.pdf file containing various performance data of network protocols from the simulation. Similarly do for wireless.xml file.
