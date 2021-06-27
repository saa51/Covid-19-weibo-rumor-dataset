# Covid-19-rumor-dataset 

This is a rumor detection dataset focusing on Covid-19-related rumors on [Weibo](https://weibo.com), a Chinese online social media.

All the rumors are collected for [Weibo community management center](https://service.account.weibo.com/). Users can report potentially untrue information to the platform, and it will check the authenticity of the information manually. Basically, we assume that the platform provides trusted ground truth. The same way of data collection can also be seen in Ma et al. (2016):

Jing Ma, Wei Gao, Prasenjit Mitra, Sejeong Kwon, Bernard J Jansen,  Kam-Fai Wong, and Meeyoung Cha. Detecting rumors from microblogs with  recurrent neural networks. In Proceedings of IJCAI 2016.

All the non-rumors are collected from Weibo's hotspots. Most of them are released from authentic sources and are seen by a large number of users. Therefore, it is less possible that those information is not true.

We collected all the available rumors on the platform from *2020.01.22* to *2021.04.22*. Non-rumors are collected at the same period.

Rumor detection can be classified as event-level detection and twitter/microblog-level detection. In our rumor data, there are some microblogs depicting only one event. Therefore, we went through all the rumors and grouped them by event. We assumed that the earliest microblog are the source of the rumor.

Here are some basic information about the dataset:

| Users # | Posts # | Events # | Rumors # | Non-Rumors # | Avg. # of posts / event |
| ------- | ------- | -------- | -------- | ------------ | ----------------------- |
| 34,035  | 42,697  | 285      | 138      | 147          | 150                     |

##### Usage:

**root.json**: A json file containing a list of root microblogs (i.e. the earliest microblog of an event).

**same_event.txt**: A json file containing a list of lists. Each element of the list includes all the ids (event-id) of the same event.

**rumor&non-rumor**: two dirs containing rumors and non-rumors, respectively. every sub-dirs are named after the id of the microblog.

In each dirs, there are possibly the following files:

**detail.json**: A json file containing the original posts.

**comments.json**: A json file containing a list of all the comments.

**reposts.json**: A json file containing a list of all the reposts.

**comm_edges.json**: A json file containing a list of all edges of the comments. A edge is a list of two elements, namely `[src_id, dest_id]`.

**repo_edges.json**: A json file containing a list of all edges of the reposts.

