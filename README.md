## Communication-efficient Allocation of Multiple Indivisible Resources in a Federated Multi-agent System
## Abstract
The paper proposes a federated multi-agent system wherein agents collaborate with a central server to
optimize system goals without sharing their private information.
It presents a communication-efficient solution to resource
allocation problems for a population of agents coupled through
multiple indivisible shared resources in a federated multi-
agent system. The agents demand resources in a probabilistic
way based on their local computation and preferences, and
the agents receive either one unit of a resource or do not
receive it. The agents are not required to share their cost
functions or derivatives of cost functions with other agents
or the central server. Optimal control of a population of
such agents, subject to capacity constraints, is widely found
in many application domains, such as smart energy systems,
intelligent transportation systems, and edge computing, to name
a few. We present convergence results using multi-time scale
stochastic approximation techniques and an example of electric
vehicle charging point allocation illustrating the efficacy of the
developed solution.

We define a {\em federated multi-agent system} as a multi-agent system wherein agents collaborate with a central server to optimize system goals without sharing their private information \cite{Hao-Hsuan2023}.
This paper considers a federated multi-agent system consisting of several agents and a central server. The agents collaborate with the central server to solve a multi-resource allocation problem and aim to achieve social welfare for the system. In several applications in smart energy systems, intelligent transportation systems, edge computing, etcetera, a population of agents such as distributed energy resources (DERs), electric vehicles (EVs), virtual machines (VMs), or IoT devices should be controlled to access limited shared resources. These agents are not required to share private information with other agents in the system. It is challenging to solve such allocation problems that minimize the cost to the system, satisfy constraints, and provide a quality of service guarantee to each agent in the federated multi-agent system. For example, managing the distributed energy resources and loads on smart grids to achieve social optimum cost \cite{Nava2021}, or controlling the electric vehicle charging \cite{Liu2017, Nimalsiri2020}, in these examples, resource utilization should be maximized, and also a certain quality of service should be guaranteed to each agent. These problems are formulated as optimal control problems to control the agents' population in the system \cite{Fioravanti2019, Syed2018_B, Syed_ISC2_2022}. 
	
This paper considers the problem of controlling a population of agents coupled through multiple indivisible shared resources in a federated multi-agent system; each agent demands the indivisible resources in a stochastic way based on their local computation, and the agents do not share their cost function or derivative of the cost function with other agents or the central server in the system. This work is a novel extension of \cite{Griggs2016} in which the optimal control of a population of agents is considered for a single indivisible resource. 
Controlling a population of agents, which demand resources in a {\em stochastic way}, is widely found in many application areas, as stated above. In these applications, the probabilistic intent of agents can be modeled to optimize system-level goals. 
%
%Such feedback systems are generally coupled as agents participate in multiple services. 
For example, when a population of electric vehicles demands different types of charging points, such as level $1$ (slow charger) or level $2$ (faster charger) charging points, to minimize voltage fluctuation or minimize the cost to the network, their objective functions depend on the consumption of both types of charging points. Generally speaking, in these scenarios, agents are coupled through the allocation of multiple indivisible resources. Note that {\em indivisible resources} are either allocated one unit or not allocated. 
The developed solution is also suitable for client selection in federated learning, wherein clients collaborate with a server to train a global model without sharing their on-device data \cite{Mcmahan2017}, \cite{Kairouz2021}. The server selects a subset of clients and sends them a global model; the clients train the model on their device data and send the learned parameters to the server. The server then aggregates the parameters and adjusts the weights to update the global model. This process is repeated until the training loss converges or time exceeds a set limit. The server selects the subset of clients at a time step to participate in the training process without considering clients' preferences \cite{Mcmahan2017}. Our solution can be used to incorporate the choices and preferences of clients to participate in the training process, and on average, the number of times clients participate will reach optimal value. Interested readers may refer to our recent work on differentially private client selection in federated settings at \cite{Syed2023_DP}.

Our main contribution to this paper is to develop a stochastic solution for a federated multi-agent system in which several agents are coupled with multiple indivisible shared resources. Each agent demands the shared resources in a probabilistic way based on its private cost function, derivative of the cost function, etc. This approach is a novel extension of the single indivisible resource allocation solution proposed in \cite{Griggs2016}. We show almost sure convergence of the average allocations based on the ideas from multi-time scale stochastic approximation techniques \cite{Borkar2008}. To check the efficacy of our algorithm, we present an application to control a population of electric vehicles that share a limited number of level $1$ and level $2$ charging points. It illustrates that the agents receive the optimal charging points in long-term averages and maximize the social welfare of the system.
The agents do not need to communicate among themselves to achieve social optimum cost; however, the central server keeps track of the aggregate utilization of resources and broadcasts price (feedback) signals at each time step. Using the value of the price signal, agents calculate their probabilistic intent to demand resources at the next time step. Assuming each price signal is of $\mu$ bits floating point, then for a system with $m$ shared resources, the communication overhead will be $\mu m$ bits per time step. Furthermore, the upper bound on the communication complexity is $\mathcal{O}(m)$-bits per time step, which is independent of the number of agents in the system.


## Citation
S. E. Alam and D. Shukla, "Communication-Efficient Allocation of Multiple Indivisible Resources in a Federated Multi-Agent System," 2023 62nd IEEE Conference on Decision and Control (CDC), Singapore, Singapore, 2023, pp. 5279-5285, doi: 10.1109/CDC49753.2023.10384067.
