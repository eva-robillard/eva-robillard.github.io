---
title: Simple Example
layout: default
nav_order: 3
---


# Presentation of the simple example



# Process

### Step 1 : Download the simulation software Renew

Please refer to the [Renew Installation window](../renew.html).

### Step 2 : Download the simple example files

[Please click here to access the files on Github](https://github.com/eva-robillard/NetsWithinNets2023.git).

### Step 3 : Open the example on Renew

The procedure for the launching on the example in Renew is:

1. Open the Powershell in the directory with the example files, containing the Java script Eval.java.
2. Execute "javac Eval.java" in the Powershell
3. Open Renew from the Powershell ( type in the path of the directory containing the Renew software adding \renew ) 
4. In Renew, open "system_net.rnw"

### Step 4 : Simulate

Simulate Step by Step (Ctrl+I) or completely (Ctrl+R)


# Information on the files

**Color code** :
* Blue: System Net
* Green: Elements used to launch a simulation
* Red: Elements used to end a simulation
* Magenta: Processing of the information, display of the best solution




**Simulation information** : 
* At all times, you can observe the state of the robots nets by right-clicking the number contained by the Master Net place and double-clicking on one robot. 
* You can simulate by choosing the fired place. After having fired "init", you can double click on a transition si and choose what transition to fire. 
* This simulation is done for an LTL formula which implies the visit of three regions of interest ("a", "b", "c"), but requiring the visit of region "c" before visintg "a". The team of 3 robots evolves in an environment with 3 regions of interest from which two of them overlap.


**Addional remarks**:
* The system will be executed as many times as the initial marking of place "numSim".
* All the traces will be accumulated to the file named "log.txt".
* Besides storing in "log.txt" the solutions found, the "best" one will be in place named "bestSol". Being initially "", each time a new solution is obtained, it is compared with the current best, by means of the function "select_best" in the class "Eval". In its current version, "best" means "shorter" in terms of number of chars, but this is so just to check the feasability. The function could/should be much more sophisticated
* This example contains two different types of robots: two as the initial example, and a second one which is not allowed to visit the intersection area
* It has also been added a way of giving names to robots for an easier understanding of the solutions

 
For an easier visualization in the Renew simulator, let us define notations without subscripts. Thus, let $\mathcal{Y} = \{a,b,c, free\}$ be the set of atomic propositions replacing the set $\mathcal{B}_\mathcal{Y}$ associated with set $\mathcal{Y}$, such that $a \equiv b_1, b \equiv b_2, c \equiv b_3$, and $b_4 \equiv free$. In addition, the symbols $\neg$ or $\wedge$ are replaced in Renew with the syntax ``$!$``, respectively ``$,$``. The $True$ value returned by the associated B\"uchi automaton of the given co-safe LTL formula, is expressed in the tool with  ``1``. The elements of the partitioned workspace are associated with the regions of interest in such way: $p_1$ for region $y_1$, $p_2$ for the overlapped area $y_2 \cap y_3$, $p_3$ for area $y_3 \setminus y_2$, $p_4$ for free space $y_4$, while $p_5$ for area $y_2 \setminus y_3$. In the following, one example is provided in addition to the mathematical formalism described throughout the paper. 

%For an easier visualization in the Renew simulator, let us define notations without subscripts. Thus, let $\mathcal{Y} = \{c,b,a, free\}$ be the set of atomic propositions replacing the set $\mathcal{B}_\mathcal{Y}$ associated with set $\mathcal{Y}$, such that $c \equiv b_1, b \equiv b_2, a \equiv b_3$, and $b_4 \equiv free$. In addition, the symbols $\neg$ or $\wedge$ are replaced in Renew with the syntax ``$!$``, respectively ``$,$``. The Specification net models a B\"uchi automaton assigned to the given LTL formula (described in the next sub-section), thus the $True$ value in the automaton is expressed in Renew through ``1``. The elements of the partitioned workspace are associated with the regions of interest in such way: $p_1$ for region $y_1$, $p_2$ for the overlapped area $y_2 \cap y_3$, $p_3$ for area $y_3 \setminus y_2$, $p_4$ for free space $y_4$, while $p_5$ for area $y_2 \setminus y_3$. In the following, one example is provided in addition to the mathematical formalism described throughout the paper. 

%\textbf{Update of $\b{\mu_C}.$} As mentioned in the previous section, the update of $\mu_C$ derives from the places labeling function of RobotOPN $h_\wedge$. The Renew tool manipulates the labels of transitions, specified by $\lambda^O_\wedge$. Although there is no access directly towards places labels, these latter labels can be retrieved easily, knowing that $\lambda^O_{\wedge}(t^O_i) = h_{\wedge}(t^{^O\bullet}_i), \forall t_i^O \in T^O$. 

\begin{comment}
   {\red Considering a RobotOPN model, with the set of transition $T^O$ and places $P^O$, we have the transition labeling function $\lambda(t_i^O)$ with values in the set of atomic proposition $\mathcal{Y}$ or $\neg \mathcal{Y}$. We define the condition multi-set associated with $t_i^O$ as $\mu_{cond}^{i}$ over the finite set $\mathcal{Y}$ : $\forall$ $t_i^O \in \mathcal{T}^O$, $\forall \mu_j \in \mu_{cond}^{i}$, $\mu_j \in \mathcal{Y}$. The following rules are applied to recover the labels of the places which capacity is modified with the firing of a known transition, and then update $\mu_C$ (see Annex \ref{annex:a}):


\begin{itemize}
    \item $\forall t_i \in \mathcal{T}^O$, $\forall$ $\lambda_j \in \lambda(t_i)$ :
    \begin{itemize}
        \item $\lambda_j \in \neg \mathcal{Y}~\Rightarrow~\neg \lambda_j \in h(^{\bullet}t_i) ~\land~\neg \lambda_j \notin h(t_i^{\bullet})$
        \item $\lambda_j \in \mathcal{Y}~\land~\lambda_j \in \mu_{cond}^{i}~\Rightarrow~ \lambda_j \notin h(^{\bullet}t_i) ~\land~\lambda_j \in h(t_i^{\bullet})$
        \item $\lambda_j \in \mathcal{Y}~\land~\lambda_j \notin \mu_{cond}^{i}~\Rightarrow~ \lambda_j \in h(^{\bullet}t_i) ~\land~\lambda_j \in h(t_i^{\bullet})$
    \end{itemize}
    \item $\forall t_i \in \mathcal{T}^O$, $\forall$ $\mu_j \in \mu_{cond}^{i}$, $\mu_j \notin \lambda(t_i)~\Rightarrow~ (\mu_j \in h(^{\bullet}t_i)) ~\land~(\mu_j \notin h(t_i^{\bullet}))$
\end{itemize}} 
\end{comment}



\subsection{Easy to follow Case-study}

Let us provide a complete example tackling the problem formulation from Sec. \ref{sec:pbstat}. We exemplify a path planning strategy for a team of three robots evolving in a known workspace (Fig. \ref{fig:env}) for which a global specification is given, using the Linear Temporal Logic language. The mission $\varphi= \diamondsuit b_1 \wedge \diamondsuit b_2 \wedge \diamondsuit b_3 \wedge  \left(\neg b_1~\mathcal{U}~b_3\right)$ implies the visit of regions of interest $y_1, y_2, y_3$, but requires that region $y_3$ to be visited before $y_1$.

From the point of view of multi-agent spatial constraints, each partition element has a maximum capacity equal with two, e.g., $\mu_{cap}[p_1] = 2$ means that no more than two robots can be present at the same time in the area $p_1$, where $p_1$ is the partition element corresponding to $y_1$. The robots are different w.r.t. to their spacial capabilities, in the sense that robots $r_1$ and $r_2$ are allowed to move freely in the entire environment, while robot $r_3$ cannot reach the overlapping part of regions $y_2$ and $y_3$, denoted with partition element $p_2$ in Fig. \ref{fig:ropns}. 

For each agent of the team, one RobotOPN is built as follows: $r_1, r_2$ are modeled identically by $o^1, o^2$, while $r_3$ is modeled by $o^3$ (Fig. \ref{fig:NwNEx} (iii)), which are represented in Renew as in Fig. \ref{fig:ropns}. The SpecOPN (Fig. \ref{fig:SpecPN_path}) is represented by the B\"uchi Petri net assigned to the mentioned LTL formula, based on the algorithm from \cite{TAC_sh_submitted}.


Out of 100 simulations (the execution time per simulation was 18 milliseconds in mean, with a standard deviation of 12 milliseconds), we could compute the shortest path of the multi-agent system in terms of the truth values of atomic propositions, such as: $\langle r_1, r_2, r_3\rangle = \langle b_3, b_1, b_2\rangle$, meaning that $r_1,r_2$ respectively $r_3$ moves synchronously into regions $y_1, y_3$, respectively $y_2$. The motion of the robots is synchronized (based on the truth value of $gef$) by firing the most right transition in SpecOPN, having the Boolean label $b_1 \wedge b_2 \wedge b_3$ (blue path in Fig. \ref{fig:SpecPN_path}). As mentioned before, Renew returns non-deterministic solutions. Therefore, other paths in the SpecOPN (purple color) can be returned by another run of 100 simulations, having as robots shortest paths $\langle r_1, r_2, r_3\rangle = \langle b_2, b_3, b_2\rangle, \langle free, b_3 \wedge b_1, free\rangle$, meaning that firstly $r_1, r_3$ move to region $y_2$, while $r_2$ moves towards $y_3$; secondly $r_1, r_3$ returns to the free space $y_4$, while $r_2$ reaches the overlapped area of $y_2 \cap y_3$. 

