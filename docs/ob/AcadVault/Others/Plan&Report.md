## 20220507
本周把工作转移到在群组推荐中应用性格的研究学习，有两篇利用Thomas-Kilmann冲突性格模型文章，分别是**Quijano-Sanchez, L., Recio-Garcia, J.A., and Diaz-Agudo, B.** (2010). Personality and Social Trust in Group Recommendations. In 2010 22nd IEEE International Conference on Tools with Artificial Intelligence (IEEE: Arras, France), pp. 121–126. 和 **Recio-Garcia, J.A., Jimenez-Diaz, G., Sanchez-Ruiz, A.A., and Diaz-Agudo, B.** (2009). Personality aware recommendations to groups. In Proceedings of the third ACM conference on Recommender systems - RecSys ’09 (ACM Press: New York, New York, USA), p. 325.
Thomas-Kilmann冲突性格模型：Kenneth Thomas与Ralph Kilmann根据Blake and Mouton开发的管理网格，制定了冲突风格清单。他们在自信和合作这两个个人特征的象限上安排了5种冲突解决办法。他们还开发了Thomas-Kilmann冲突模式工具，在处理冲突时可以用来识别个人的自然倾向。

![](https://fengshaoying.oss-cn-shanghai.aliyuncs.com/images/20220508214656.png)

-   **竞争型**
    喜欢这种风格的人倾向于采取坚定的立场，因为他们对自己的立场很有信心。他们通常处于具有一定权力的职位。当冲突需要紧急解决时、当解决方案不是一般常规方案时、或者当对方努力利用情况来来实现自身优势时，这种风格是有用的。一定要注意不要不适当地使用这种风格，因为有些人会觉得他们已经在争论中失利，而且会感到很气愤。
-   **合作型**
    合作风格是努力去满足每个参与者的需求。具有这种风格的人仍然会自信，但是与“竞争”风格不同的是，他们承认每个人的观点都是同等重要的。这种风格尝试将许多观点结合在一起，以达到最佳的解决方案，并且应该是首先采用的风格，例如，在要求管理中解决冲突的时候。
-   **妥协型**
    妥协往往意味着所有各方只感到部分满意。妥协意味着每个人都必须放弃一些东西，但当冲突对项目、项目群或项目组合目标的影响超过打破各方之间僵局的影响时，是有用的。这种方法很可能在生命周期的交付阶段使用。
-   **随和型**
    这种风格表明，有人准备好满足他人的需要，并牺牲自己的需求。这对于项目、项目群、项目组合经理来说不太可能是一个合适的风格，因为他们的首要任务是满足项目、项目群、项目组合的目标。只有当这是解决冲突的唯一办法、而不解决的影响比必要的让步更严重时，这种风格才应该被采纳。
-   **避免型**
    喜欢这种风格的人会试图避开冲突，或将其传递给他人。只有当项目、项目群、项目组合经理真正相信别人能更好地解决冲突时，这种风格才是可以接受的。例如，对于一名项目、项目群、项目组合经理来说，将解决与资深利益相关方的冲突的责任转交给发起人是完全合理的——但是，应该以一种建设性的方式，而不是忽视问题、希望依赖赞助商来解决问题。

Quijano-Sanchez,  Recio-Garcia等人在上面两文章中提出了利用Thomas-Kilmann冲突性格模型来衡量成员的自性信和合作性，并以此来为群体成员之间的关系统进行模型建模，然后再使用Minimizing penalization(惩罚最小化),Average satisfaction(平均满意度最优),Least misery(不满最小化)。他们通过用户实验收集了70名学生的真实数据，包括组队，讨论，决定在电影院里看什么样的电影等。通过研究发现，考虑Thomas-Kilmann冲突性格模型后，推荐的准确性更好了。当然也可以考虑Thomas-Kilmann冲突性格模型和五因素模型相结合来衡量用户性格。

## 20220501
根据上周汇报Hu和Pu的《Exploring Relations between Personality and User Rating Behaviors》文章，对此文章的引用情况进行调查了一下，在Google Scholar查到了引用有33篇，并对引用的文章大致梳理了下。其中如下两篇可以学习借鉴。

1）Wen Wu & Li Chen的《 Implicit Acquisition of User Personality for Augmenting Movie Recommendations》文章中使用的性格提取方法感觉挺好的。近年来，用户性格被大量关注，普遍认为性格是有价值的信息，从而构建更加个性化的推荐系统。然而，通过心理问卷明确获取用户性格特征的难度相对较高，这可能会阻碍基于个性的推荐在现实生活中的应用。在Wen Wu & Li Chen的上述文中，专注于从用户在电影领域内的隐式行为中衍生出用户的个性，从而使得无需用户努力就能生成推荐。具体来说，通过实验验证确定了一组行为特征，并开发了基于高斯过程的推理模型来统一这些特征，以确定用户的大五人格特征。然后，在一个基于协同过滤的推荐框架中对两个真实的电影数据集进行了测试，结果表明，基于隐式性格的推荐算法在评级预测和排名准确性方面都显著优于相关方法。实验结果为提高基于性格的推荐系统在网络环境中的适用性提供了有效的解决方案。大概做法是：通过实验验证，首先确定了一组与用户个性特征显著相关的特征。其中，有些是领域依赖的，如用户对电影类型和电影多样性的偏好、观看时长、观看动机等。有些是独立于领域的，比如用户的评级行为和年龄信息。然后，我们将所有这些特性集成到一个回归模型中，以推断用户的个性。具体测试了三种不同的模型，Gaussian Process, Pace Regression, 和 M5 Rules，发现Gaussian Process在推理精度方面表现最好。最后，开发了基于CF算法的3种不同性格，该算法从现实生活中的电影数据集中的用户行为中含蓄地推断出性格。通过实验，证明了用户性格与评分相结合的方法在评分预测和排名准确率上都是最准确的。

2）针对上次老师您提到的花半年或一年时间收集用户真实评价，并对这些用户进行问卷调查，通过查阅文献，类似这样的工作已经有人做了，在RP Karumur, TT Nguyen, JA Konstan的《Exploring the value of personality in predicting rating behaviors: a study of category preferences on movielens》的文章中采用的就是这个方法。在这项研究中，使用了38675部MovieLens的电影，这些电影被划分为17种类型中的一种或多种，包括动作、冒险、动画、儿童、喜剧、犯罪、纪录片、戏剧， 幻想、恐怖、音乐等等。MovieLens的用户主要通过给电影打分，通过给他们五星评分，以半星为单位递增。根据Gosling, S. D., Rentfrow, P.J., and Swann的《 A very brief measure of the Big-Five personality domains》对MovieLens用户进行问卷调查，以获取他们的个性信息，并收集1840名用户的回答。  根据这些回答，为每个用户计算了五种性格特征中的每一种的性格得分，范围从1 - 7。还获得了这些用户提供的985,918部电影评级的可识别的数据，这些数据构成了我们的数据集。并对数据进行对比分析。 

## 20220424
本周主要了解性格的采集方法和一些线下实验的数据集
1. 很多线下的数据集可以用于基于用户性格的推荐系统实验中，这些数据集中包含用户和物品的交互数据（如评分数据），基于FFM的用户的性格数据。
	在The LDOS-PerAff-1 数据集中包含了52个用户对不同图片打分，而且每个用户对每张图片给出了打分。数据集中包含了每个用户的FFM五因素性格模型。用户的性格参数是根据50题IPIP问卷得到的。（参考文献The LDOS-PerAff-1 corpus of facial-expression video clips with affective,personality and user-interaction metadata）
	在LDOS-CoMoDa(Context Movies Dataset)数据集中，用于研究基于上下文的推荐系统，整个数据集中包含发95个用户和961部电影信息，它包含每个用户的五因素性格参数，这是这个数据集的唯一特征，性格参数是由50题IPIP问卷得到的。这个数据集还有丰富的上下文数据，如时间，天气，地点，情感和社交状态等。（参考文献Database for contextual personalization ）
	在MyPersonality数据集，用户规模很大，包含了38330个用户的大五性格因素。该数据集由一个Facebook的应用程序获得，数据包括用户在Facebook上的点赞行为。（参考文献Private traits and attributes are predictable from digital records of human behavior）
2. 本来的想在Hu和Pu的《Exploring Relations between Personality and User Rating Behaviors》学习一下怎么从产品评价获得用户性格分类，但此文献并不是讲获得的途径，而是讲用户性格对评价行影响，看着实验做得挺详细，也就认真研读了一下，并进行汇报。


## 20220417
本周主要了解学习性格的采集方法
**显示采集方法**
根据性格模型设计调查问卷，显示方法虽然能够准确获得用户的性格特征，但通常具有侵入性，费时费力，因此这些方法一般只能用在实验室研究中。国际性格测试题库是比较常用的获取性格五因素的方法，在IPIP(http://ipip.ori.org/) ![](https://fengshaoying.oss-cn-shanghai.aliyuncs.com/images/20220417185441.png)
的网页上根据每种性格因素的测试数量生成50道或者100道题目的问卷。这些精心设计的问题可以保证测试的准确性，但同时比较费时。感觉可操作性不强，Hellriegel和Slocum在《organizational behavior cengage learning》文献中制定的关于五因素性格测试的调查问卷里针对每种性格因素有5个问题，共有25个问题来衡量人的性格特征，简化问卷题目数量。相比之下具有较强的可操作性。当然还有一个更短的十项人格量表（Ten Item Personality Inventory,TIPI）属于大五量模型，针对每项性格因素只有两个小问题，特别适合在短时间内完成性格采集，可以参考文献《A very brief measure of the Big-Five personality domains》,由于它的问题数量数目比较少，所以可能无法达到心理测量学的要求，但可以满足基本性格测量分类要求。性格测试的工具有很多，但是工具的选择仍然依赖于具体应用场景，并不存一下“完全通用”的评价准则。**但有个疑问，难道在用户使用推荐系统前都要先做个问卷吗？然后再得到用户性格分类？**

**隐式采集方法**
隐式采集方法大多还是依赖现有的一些数据集，通过抽取数据集中的用户行为特征，探索相应的五种性格因素的相关性。比如Quercia等人在《Our Twitter Profiles, Our Selves: Predicting Personality with Twitter》的根据myPersonality数据集中的335个用户数据，发现从用户微博里抽取的特征和相应的五种性格因素有很强的相关性。他们把从微博中抽取的特征划分到以下类别：听众，受欢迎，高阅读量和有影响力，这些类别都和五因素模型中至少一种性格因素有紧密相关。Kosinski等人在《Private traits and attributes are predictable from digital records of human behavior》研究中使用myPersonality数据集中超过58000个用户在Facebook中点赞行为的记录来预测他们的五因素性格模型。他们根据用户对事件的点赞记录生成点赞矩阵，然后利用奇异值分解对特征值进行降维，再加上用户的性别、年龄等基本特征，使用逻辑回归预测用户五因素性格特征。Hu和Pu在《Exploring Relations between Personality and User Rating Behaviors》中研究了推荐系统中用户性格用户性格对他们的打分行为的影响，他们采集了86个用户对属于44种主要类别中的871种商品的有效打分。对于每个用户的打分行为可以从4个方面来分析：已打分商品数量，正面评分的比例，商品类别覆盖率和兴趣多样性。其中，商品类别覆盖率是该用户已打分商品所属的种类数目，兴趣多样性反映用户对各个类别的兴趣分布。他们使用皮尔逊相关系数计算了用户大五性格因素和打分行为变量之间的相关性，并验证了用户性格极大地影响用户对商品打分的行为。

## 20220410
1. 这周整理下关于性格方面的文献，一共收集了68篇研究性格相关文献
![](https://fengshaoying.oss-cn-shanghai.aliyuncs.com/images/20220411181329.png)

2. 性格的提取从收集的情况来看，性格的研究大都是性格五因素模型（FFM）。接下来去了解一下性格怎么与用户Preferences相关联起来。
3. 性格的提取
    显示和隐示性格提取，有一些离线的推荐系统实验数据集可使用，如：
	LDOS-CoMoDa数据集，参考文献[Košir, A., Odi ́ c, A., Kunaver, M., Tkalˇ ciˇ c, M., Tasiˇ c, J.F.: Database for contextual personalization. Elektrotehniški vestnik 78(5), 270–274 (2011)]
	LDOS-PerAff-1数据集，参考文献[Tkalˇ ciˇ c, M., Košir, A., Tasiˇ c, J.: The LDOS-PerAff-1 corpus of facial-expression video clips with affective, personality and user-interaction metadata.]
	myPersonality数据集，参考文献[Kosinski, M., Stillwell, D., Graepel, T.: Private traits and attributes are predictable from digital records of human behavior.]
	Chittaranjan数据集，参考文献[Chittaranjan, G., Blom, J., Gatica-Perez, D.: Mining large-scale smartphone data for personality studies.]
	接下来了解这些文献中数据集的使用和性格的提取。