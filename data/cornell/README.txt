Cornell Movie-Dialogs Corpus

Distributed together with:

"Chameleons in imagined conversations: A new approach to understanding coordination of linguistic style in dialogs"
Cristian Danescu-Niculescu-Mizil and Lillian Lee
Proceedings of the Workshop on Cognitive Modeling and Computational Linguistics, ACL 2011.

(this paper is included in this zip file)

NOTE: If you have results to report on these corpora, please send email to cristian@cs.cornell.edu or llee@cs.cornell.edu so we can add you to our list of people using this data.  Thanks!


Contents of this README:

	A) Brief description
	B) Files description
	C) Details on the collection procedure
	D) Contact


A) Brief description:

This corpus contains a metadata-rich collection of fictional conversations extracted from raw movie scripts:

- 220,579 conversational exchanges between 10,292 pairs of movie characters
- involves 9,035 characters from 617 movies
- in total 304,713 utterances
- movie metadata included:
	- genres
	- release year
	- IMDB rating
	- number of IMDB votes
	- IMDB rating
- character metadata included:
	- gender (for 3,774 characters)
	- position on movie credits (3,321 characters)


B) Files description:

In all files the field separator is " +++$+++ "

- movie_titles_metadata.txt
	- contains information about each movie title
	- fields: 
		- movieID, 
		- movie title,
		- movie year, 
	   	- IMDB rating,
		- no. IMDB votes,
 		- genres in the format ['genre1','genre2',�,'genreN']

- movie_characters_metadata.txt
	- contains information about each movie character
	- fields:
		- characterID
		- character name
		- movieID
		- movie title
		- gender ("?" for unlabeled cases)
		- position in credits ("?" for unlabeled cases) 

- movie_lines.txt
	- contains the actual text of each utterance
	- fields:
		- lineID
		- characterID (who uttered this phrase)
		- movieID
		- character name
		- text of the utterance

- movie_conversations.txt
	- the structure of the conversations
	- fields
		- characterID of the first character involved in the conversation
		- characterID of the second character involved in the conversation
		- movieID of the movie in which the conversation occurred
		- list of the utterances that make the conversation, in chronological 
			order: ['lineID1','lineID2',�,'lineIDN']
			has to be matched with movie_lines.txt to reconstruct the actual content

- raw_script_urls.txt
	- the urls from which the raw sources were retrieved

C) Details on the collection procedure:

We started from raw publicly available movie scripts (sources acknowledged in 
raw_script_urls.txt).  In order to collect the metadata necessary for this study 
and to distinguish between two script versions of the same movie, we automatically
 matched each script with an entry in movie database provided by IMDB (The Internet
 Movie Database; data interfaces available at http://www.imdb.com/interfaces). Some
 amount of manual correction was also involved. When  more than one movie with the same
 title was found in IMBD, the match was made with the most popular title 
(the one that received most IMDB votes)  

After discarding all movies that could not be matched or that had less than 5 IMDB 
votes, we were left with 617 unique titles with metadata including genre, release 
year, IMDB rating and no. of IMDB votes and cast distribution.  We then identified 
the pairs of characters that interact and separated their conversations automatically 
using simple data processing heuristics. After discarding all pairs that exchanged 
less than 5 conversational exchanges there were 10,292 left, exchanging 220,579 
conversational exchanges (304,713 utterances).  After automatically matching the names 
of the 9,035 involved characters to the list of cast distribution, we used the 
gender of each interpreting actor to infer the fictional gender of a subset of 
3,321 movie characters (we raised the number of gendered 3,774 characters through
 manual annotation). Similarly, we collected the end credit position of a subset 
of 3,321 characters as a proxy for their status.


D) Contact:

Please email any questions to: cristian@cs.cornell.edu (Cristian Danescu-Niculescu-Mizil)



康奈尔电影对话语料库

分布式：

“想象对话中的变色龙：理解对话中语言风格协调的新方法”
Cristian Danescu-Niculescu-Mizil和Lillian Lee
ACL 2011认知建模和计算语言学研讨会论文集。

（本文包含在此zip文件中）

注意：如果您有结果要报告这些语料库，请发送电子邮件至cristian@cs.cornell.edu或llee@cs.cornell.edu，以便我们将您添加到使用此数据的人员列表中。谢谢！


本自述文件的内容：

A）简要说明
B）文件描述
C）收集程序的细节
D）联系


A）简要说明：

此语料库包含从原始电影脚本中提取的元数据丰富的虚构对话集合：

- 10,292对电影角色之间的220,579次会话交换
- 涉及617部电影中的9,035个字符
- 总共304,713个话语
- 电影元数据包括：
- 流派
- 发行年份
- IMDB评级
- IMDB投票数量
- IMDB评级
- 包括字符元数据：
- 性别（3,774个字符）
- 电影学分的位置（3,321个字符）


B）文件描述：

在所有文件中，字段分隔符为“+++ $ +++”

- movie_titles_metadata.txt
- 包含有关每个电影标题的信息
- 字段：
- movieID，
- 电影标题，
- 电影年，
- IMDB评级，
- 不。 IMDB投票，
  - 格式为''genre1'，'genre2'， ，'genreN']的类型

- movie_characters_metadata.txt
- 包含有关每个电影角色的信息
- 字段：
- characterID
- 角色名字
- movieID
- 电影标题
- 性别（未标记案件的“？”）
- 学分中的位置（“？”表示未标记的案例）

- movie_lines.txt
- 包含每个话语的实际文本
- 字段：
- lineID
- characterID（谁说出这句话）
- movieID
- 角色名字
- 话语的文本

- movie_conversations.txt
- 对话的结构
- 田野
- 对话中涉及的第一个字符的characterID
- 对话中涉及的第二个字符的characterID
- 发生对话的电影的movieID
- 按时间顺序排列进行对话的话语列表
顺序：['lineID1'，'lineID2'， ，'lineIDN']
必须与movie_lines.txt匹配才能重建实际内容

- raw_script_urls.txt
- 检索原始来源的网址

C）收集程序的细节：

我们从原始的公开电影剧本开始（来源承认
raw_script_urls.txt）。为了收集本研究所需的元数据
并且为了区分同一部电影的两个脚本版本，我们会自动进行
 将每个脚本与IMDB（互联网）提供的电影数据库中的条目相匹配
 电影数据库;数据接口可从http://www.imdb.com/interfaces获得。一些
 还涉及人工纠正的数量。当不止一部电影一样的时候
 在IMBD中找到了冠军，这场比赛是用最受欢迎的冠军
（获得大多数IMDB投票的人）

丢弃所有无法匹配或少于5个IMDB的电影后
投票，我们留下了617个独特的标题，包括流派，发行等元数据
一年，IMDB评级和没有。 IMDB投票和演员分配。然后我们确定了
自动交互和分离对话的字符对
使用简单的数据处理启发式。丢弃所有交换的对后
不到5个会话交换，剩下10,292个，交换220,579个
会话交流（304,713个话语）。自动匹配名称后
将9,035个涉及的字符放入演员阵容列表中，我们使用了
每个口译员的性别，以推断出一个子集的虚构性别
3,321个电影角色（我们提高了3,774个字符的性别数量
 手动注释）。同样，我们收集了子集的最终信用状况
3,321个字符作为其状态的代理。

