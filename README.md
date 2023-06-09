# Complex-Networks---Implementation-Of-Models

I developed functions to generate various network models, each with different parameters, which were
then used to generate networks of various sizes. These functions were implemented using Python
programming language, and the networkx package was utilized to handle the creation and manipulation
of the network models. The different network models generated include Barab´asi-Albert (BA), Erd˝os-
R´enyi (ER), Watts-Strogatz (WS), and Configuration Models.
To evaluate the generated networks, a range of parameters was used for each model. For small networks
with less than 1000 nodes, I plotted a visual representation of the network using the nx.draw(G)
function, and a histogram of the degree distribution. The degree distribution refers to the frequency
of nodes with a particular number of edges, or degrees. For larger networks with 1000 or more nodes,
I only plotted the histogram. For networks that follow a power-law distribution, the histogram was
plotted in a log-log scale. Why? Because this scale is used to visualize the tail of the distribution as
it is often difficult to see using a regular scale.
To estimate the exponent of the power-law distribution of degrees for networks with this property
(BA and CM Scale Free), I used two methods: linear regression of log(P(k)) as a function of log(k), and
Maximum Likelihood Estimation (MLE), and it is outlined in the file provided ”Details-Exponent”.
The goal of estimating the exponent is to determine the degree to which the network follows a powerlaw
distribution. In fact, Linear regression is a statistical technique used to identify the relationship
between two variables, and in my case, it is the degree of a node (k) and its frequency (P(k)).
Following the linear regression problem, it was also necessary to discard the (b, p[b]) pairs where
p[b] = 0 because it was impossible to take the logarithm of 0. For MLE, the output was often
unsatisfactory. Thus, based on the article ”Power-law distributions in empirical data,” I figured out
that it would be good to filter out all nodes with a degree less than 6 so as to improve the quality of
the estimation especially when kmin = 6.
Lastly, the networks generated were saved in pajek format, along with their respective images.
