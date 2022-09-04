# Basic-data-of-integrated-energy-system-protection-model
&ensp;&ensp;&ensp;&ensp;Based on the established electric gas thermal coupling integrated energy system as an example, the probability of node / line being attacked, the probability of node / line being successfully attacked and the cost parameters are shown below.
## The probability of node/line being attacked
&ensp;&ensp;&ensp;&ensp;This paper holds that node/line would be attacked in two ways: natural disasters and sabotage. The probability of attacks under natural disasters is rather low but every node/line would be attacked; while sabotage is of a relatively high probability and onto relatively important nodes/lines, i.e., high-weighted nodes/lines are prone to more artificial attacks. Therefore, the probability of nodes being attacked in this model is set in the following formula:   
$$\{P_{attack,i}} = 0.01 + \frac{{nodebetweennes{s_i} \times nodeindex}}{{10}}$$
Where 0.01 is the probability of nodes being attacked by natural disasters; $\frac{{nodebetweennes{s_i} \times nodeindex}}{{10}}\$ is the probability of artificial attacks on nodes. The higher the weighted node betweenness is, is more likely it is to be attacked.  
&ensp;&ensp;&ensp;&ensp;The probability of lines being attacked is shown as follows:
$$\{P_{attack,j}} = 0.1 + \frac{{linebetweennes{s_j} \times lineindex}}{{10}}\$$
Where 0.1 means the probability of lines being attacked by natural disasters; $\frac{{nodebetweennes{s_i} \times nodeindex}}{{10}}\$ is the probability of artificial attacks on nodes.The higher the weighted line betweenness is, is more likely it is to be attacked.
## The probability of nodes/lines being attacked successfully
&ensp;&ensp;&ensp;&ensp;This paper holds that it is pertinent between the probability of nodes/lines being attacked successfully and their weighted betweenness. The higher the weighted betweenness of nodes/lines is, the more important it is, the more sophisticated its protection is, and the less probability of nodes/lines being attacked successfully. Meanwhile, the probability of nodes being attacked is lower than that of lines.
Hence, the probability of nodes being attacked in this model is set in the following formula:  
$$\{P_{attacksuccess,i}} = 0.5 - \frac{{nodebetweennes{s_i} \times nodeindex}}{{10}}\$$
&ensp;&ensp;&ensp;&ensp;The probability of lines being attacked successfully is shown as follows:  
$$\{P_{attacksuccess,j}} = 0.6 - \frac{{linbetweennes{s_j} \times lineindex}}{{10}}\$$
## Parameters of adding-edge cost
&ensp;&ensp;&ensp;&ensp;Table 1 displays the parameter of adding-edge cost of the power network, gas network, and heat network set in this model. Adding edges in a power network means adding power transmission lines; in a gas network, it means adding natural gas transmission pipes; in a heat network, it refers to adding water supply and return lines. (One edge addition in the heat network is equal to adding a water supply pipe and water return pipe simultaneously.  
#### Table 1: Parameter of adding-edge cost
Subnet types  | Power network(10k yuan/line)|Natural gas network(10k yuan/line)|Heat network(10k yuan/line)
:-------------: |:-------------:|:-------------:|:-------------:
Adding side cost parameters  | 1500|2000|4000
## Parameters of physical protection cost
&ensp;&ensp;&ensp;&ensp;Table 2 shows the cost coefficient of physical protection on nodes and lines in this model.  
#### Table 2:cost coefficient of physical protection
Types of physical protection  | Node(10k yuan)|Line(10k yuan)
:-------------: |:-------------:|:-------------:
Parameters of physical protection cost  | 2000|1600
## Parameters of cost of backup stations/lines
&ensp;&ensp;&ensp;&ensp;  This paper proposes that the higher the weighted betweenness of a node is, the more critical the node is, and the higher the cost of building its backup station is; The higher the weighted betweenness of a line is, the more critical the node is, and the higher the cost of building its backup station is. Therefore, in this chapter, the cost of adding backup stations is set by the following formula:  
$$costcoefficientbus = {\rm{COSTCOEFFICIENTBUS}} \times (0.1 + \frac{{nodebetweennes{s_i}}}{{\sum\limits_{0 < i \le nodeindex} {nodebetweennes{s_i}} }})\$$
Where， $\{\rm{COSTCOEFFICIENTBUS}}\$ is the cost coefficient of adding backup stations; nodebetweenness；
$\\frac{{nodebetweennes{s_i}}}{{\sum\limits_{0 < i \le nodeindex} {nodebetweennes{s_i}} }}\$
 is the portion of nodes with weighted betweenness.  The cost of adding the backup line is shown in the following formula.  
$$costcoefficientline = {\rm{COSTCOEFFICIENTLINE}} \times (0.1 + \frac{{linebetweennes{s_j}}}{{\sum\limits_{0 < j \le lineindex} {linbetweennes{s_j}} }})\$$
Where， $\{\rm{COSTCOEFFICIENTLINE}}\$ is the cost coefficient of adding backup stations; 0.1 is the fixed cost factor for establishing a standby line；
$\\frac{{linebetweennes{s_j}}}{{\sum\limits_{0 < j \le lineindex} {linbetweennes{s_j}} }}\$
 is the portion of nodes with weighted betweenness.   
&ensp;&ensp;&ensp;&ensp;The cost coefficient of adding backup stations/lines is displayed in Table 3.
#### Table 3:Cost coefficient of adding backup stations/lines
Protection types  | Backup station addition (10k yuan)|Backup line addition (10k yuan)
:-------------: |:-------------:|:-------------:
Cost parameters  |24000|18000
## Other parameters
&ensp;&ensp;&ensp;&ensp;Table 4 shows other parameters mentioned in the algorithms of this model, in particular the number of constraints, such as adding edges and variable processing.
#### Table 4:Values of other parameters
 Parameter | $\alpha $|$\beta $|$\gamma $
:-------------: |:-------------:|:-------------:|:-------------:
Value  |0.15%|0.15%|0.15%
