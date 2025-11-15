# Gamification Strategies: A Characterization Using Formal Argumentation Theory

Esteban Guerrero<sup>1</sup>  $\cdot$  Panu Kalmi<sup>2</sup>

Received: 30 January 2022 / Accepted: 18 April 2022 / Published online: 17 May 2022  
© The Author(s) 2022

# Abstract

Gamified software applications are omnipresent in everyday life. The idea of using game design elements in non-game contexts to engage and motivate tasks has rapidly gained traction in the human-computer interaction and the psychology fields, but scarcely in the artificial intelligence (AI) research area. In this paper, we propose a software agent perspective of gamification elements to solve two specific problems: (1) a reactive perspective that gamification designers have for those gamified affordances, i.e. the visual cue (output) is only triggered by user interaction, and (2) a lack of formal treatment of gamified software, where strict characterization of software behavior as done in AI, guarantee that the information-based output follows the intended goal of the software. Our contributions presented in this paper are (1) two taxonomies of affordances based on the type of information that every element communicates, and the type of agency that is capable; (2) a framework to formalize the decision-making process for gamified software agents; and (3) a characterization of gamified stories using formal argumentation theory dialogues. We exemplify our contributions with two gamified platforms in the healthcare and financial literacy fields.

Keywords Gamification  $\cdot$  Argumentation theory  $\cdot$  Taxonomy  $\cdot$  Dialogues  $\cdot$  Stories  $\cdot$  Software agents

# Introduction

Gamification, understood as the use of game design elements in non-game contexts [1] is a research field integrating approaches from the human-computer interaction, psychology, and computer science fields. Usually, persuasive gamification constructs (e.g. social orientation [2], emotion-orientation [3], etc.) are used as a means for tailoring software, which although promising, presents a problem of high specialization without general theories or frameworks,

This article is part of the topical collection "Frontiers in Practical Applications of Agents, Multi-Agent Systems, and Social Good" guest edited by Fernando De la Prieta and Frank Dignum.

drifting toward an apparent immaturity of formal foundations and validated methods [4]. However, gamification has increased popularity for designing software that covers enjoyment, immersion, and goal-orientation being a conventional approach for behavior change [5, 6]. Key in these persuasive designs are well-used visual cues such as leader boards, rankings, levels, stories, etc. These gamification affordances have been the subject of different studies to understand user orientation and the relationship with those elements [7-9], to explore affordances to motivate and induce emotions [3, 4], and for assessing the suitability of those game objects for social-oriented tasks (e.g. cooperative or competitive) [2, 10]. Previous research has classified these gamified elements considering user motivation, engagement, and effects on user's behavior [11, 12], depending on the type of artifacts from a development perspective [13] and classifying affordances types depending on the application of different levels of design principles [14]. Despite this body of investigation, an evident research gap exists in the intersection between gamification and artificial intelligence (AI), specifically from one of its branches, the design of autonomous software agents. The two specific problems that we challenge in this paper are:

![](images/89dc1197d04e2a9fc7c94ce4b6025ca85957409f7ac4709e25a71fdf9dfbb076.jpg)  
Fig.1 Methodological process: Phase (1) content identification, Phase 2 strategies identification, and Phase (3) agent design

1. Previous research considers gamified software as static artifacts (see reviews [15, 16]), being common that affordances have only a reactive behavior, i.e. their output is only triggered by user interaction, and its behavior is handcrafted to a specific game task. The notions of proactive, semi-autonomous, or autonomous gamified elements have been disregarded in the gamification literature.  
2. Research on persuasive gamification lacks mathematical characterizations of gamified software, which is valuable to ensure the correct behavior of such affordances. Formalization of software behavior, as done in AI, guarantees that the information-based output follows the intended goal of the software. The use of formal approaches to describe gamification elements and mechanisms is almost nonexistent (see review [4]).

In this paper, we propose a software-agents perspective of gamification elements introducing two taxonomies of affordances based on the type of information that every element communicates and the type of agency that is capable. We also introduce a framework to formalize the decision-making process that such gamified software agents should have, presenting an algorithm that allows such agents to make decisions about what gamification affordance is most suitable for a user. Finally, we present a characterization of one type of gamification strategy called stories, where formal argumentation theory [17] (active research line of AI) is used to precisely describe the behavior of the software and user interaction. Concretely, three contributions are presented: (1)

a set of typologies of persuasive strategies and content, (2) a mapping between those typologies and formal persuasive dialogue games, and (3) a novel algorithm for strategy and content selection that can be used in persuasive technology. We exemplify our framework using two software platforms as persuasive gamified stories, one in the context of healthcare and the other for financial literacy. This paper is an extended and improved version of the paper presented in [18].<sup>1</sup>

This paper is organized as follows, we present our methodological approach in "Methodology" where we include a necessary background. "Results" introduces the main results, which are divided into three subsections presenting the three aforementioned contributions. Experiments implementing our framework are presented in "Experimentation", and an in-depth discussion about the results is presented in "Discussion and Future Work". We end our paper by highlighting our conclusions and future research paths in "Conclusions".

# Methodology

This paper followed a three-arm methodological approach (see Fig. 1). In the following, we present methods used in the three phases.

Table 1 Consulted databases with their number of potential papers  

<table><tr><td>Database</td><td>Potential</td></tr><tr><td>IEEE Xplore</td><td>64</td></tr><tr><td>SCOPUS</td><td>19 (set 1) + 15 (set 2)</td></tr><tr><td>EBSCOhost</td><td>1</td></tr><tr><td>ACM Digital Library</td><td>39</td></tr><tr><td>Total</td><td>138</td></tr></table>

# Persuasive Content and Strategies Identification (Phase 1 and 2)

Identification of general features of persuasive systems was performed using two data collection mechanisms: (1) a systematic literature review (SLR), aiming at identifying features (or content) used in persuasive systems within the health-care and financial literacy literature;[2] and (2) expert elicitation process in which a multidisciplinary group of researchers identified features of those systems focused on specific scientific areas. We describe the data collection procedure in the following.

# Literature Review on Features Identification

We followed Kitchenham's protocol in [19] to perform our systematic literature reviews (SLR), which was part of the methodological procedure used in this paper.

SLR Research questions. The questions that the SLR was aiming to solve were:

Q1 What type of gamification content is usually used in persuasive coaching systems?  
Q2 What gamification strategies are usually used in persuasive coaching systems?

Databases We collect results from seven databases: IEEE Xplore, Scopus, EBSCOhost, and ACM Digital Library. The time frame selected for this review was from January 2000 to December 2021. $^{3}$

Databases queries We use systematically two sets of keywords in our search strategy to evaluate publications by a different team, depending on the field background w.r.t. financial literacy or health.

Set 1 ("ALL METADATA":"COACHING SYSTEM") OR ("ALL METADATA":"PERSUASIVE SYSTEM") OR ("ALL METADATA":"BEHAVIOR CHANGE SYSTEM") AND ("ALL METADATA":GAMIFI*) AND ("ALL METADATA":HEALTH*) AND ("ALL METADATA":"BEHAVIOR CHANGE"),

Set 2 ("ALL METADATA":"COACHING SYSTEM") OR ("ALL METADATA":"PERSUASIVE SYSTEM") OR ("ALL METADATA":"BEHAVIOR CHANGE SYSTEM") AND ("ALL METADATA":GAMIFI*) AND ("ALL METADATA":"FINANC* LITERACY") AND ("ALL METADATA":"BEHAVIOR CHANGE")

# Inclusion and exclusion criteria

We removed duplicates  $(n = 4)$  and no-single articles such as collections  $(n = 4)$ , no-fully access  $(n = 2)$ , no-complete or mature publications  $(n = 2)$ , and reviews  $(n = 6)$ , which were used in the Discussion section to compare our results with the state of the art.

Four criteria (CR) were defined to assess every paper (see below), every criterion had a quantitative score of 1, 0, or -1, which correspond to answering the criteria with values: Yes, Partially or Not, respectively. A total score is calculated by adding the individual criteria values. Our total selection score was equal or greater than zero.

- CR1: It is connected with health-related or financial literacy-related persuasive systems.  
- CR2: Describes any AI-based approach used to detect, predict, anticipate, infer or deduce a (un)desired/(un) wanted specific behavior.  
- CR3: Describes the type of gamification content used for coaching.  
- CR4: Describes the type of gamification strategies used for coaching.

# Expert Elicitation

The expert elicitation process was oriented to capture the perspective of senior researchers about gamification in the specific aim of this project. Eight volunteers were recruited to participate in the study. They had no expertise in software development, user experience, or software design. However, they were part of the project, and the recruitment process was through direct contact. No rewards were offered. The following are general characteristics of the participants:

Number of participants: eight  
Age: avg: 47.5 sd: 7.59  
- Research areas expertise: physical activity and sedentary behaviour, ageing and disability, social work, social welfare, nutrition, psychology and governance, finance and economics, and health economics.

![](images/007f3d56c4bdee278b214ecb6fdd5164e0489ef7bad58f5e9063465082bc9455.jpg)  
Fig. 2 Themes and codes used for interpreting interviews entries

A five-items questionnaire directed a one-hour interview containing the following questions:

1. What should be the main goal for the digital coach?  
2. What are the main functionalities of the system?  
3. How the visual aspect of the main functionality would be?  
4. What direct benefits a user should receive from the digital coach use?  
5. What direct risks could the user have when using the digital coach?

Analysis Grounded theory [20] was used as an inductive, comparative process for gathering, synthesizing, and identifying features and strategies of persuasive/coaching systems. We used the RQDA: Qualitative Data Analysis package with RStudio v1.2.5 and R language to make the codes, code categories, and the analysis of cases of every interview. Then, a follow-up short questionnaire with identical questions was fulfilled by the same experts after six months, as a validation process to confirm/disapprove potential features and strategies. We used 19 codes grouped into nine categories as is presented in Fig. 2.

# Agent Design Background (Phase 3)

In this paper, we make the following design assumptions of our agents  $(Ag)$ : (1) an  $Ag$  has an independent knowledge

base  $\Sigma$ , potentially inconsistent, and contains formulas of a propositional language  $\mathcal{L}$ . (2) Formal argumentation is used in the  $Ag$ 's decision-making process, and in the communication process (argument-based dialogue) that has a persuasive nature, between a persuadee  $(Ag_{c})$  and a persuader  $(Ag_{p})$ . We use a propositional logic with connectives:  $\land, \leftarrow, \neg, \top$ ; the consequence operator:  $\leftarrow$  is non-monotonic.

# Formal Argumentation Reasoning

An argument is a tuple  $\mathsf{Arg} = \langle \mathsf{support}, \mathsf{conclusion} \rangle$ , fulfilling next conditions: (1)  $\mathsf{supp} \subseteq \Sigma$ ; (2)  $\mathsf{supp}$  is consistent; (3)  $\mathsf{supp} \vdash \mathsf{conc}$  and (4)  $\exists \mathsf{supp}' \subset \mathsf{supp}$  such that  $\mathsf{supp}' \vdash \mathsf{conc}$ .  $\mathsf{supp}$  and  $\mathsf{conc}$  are usually called the support and conclusion of an argument. All the arguments built from  $\Sigma$  are noted as  $\mathcal{A}$ .

# Argumentation-Based Dialogue

A dialogue  $(\mathcal{D})$  has two agents, both have an argument-based decision-making process and they communicate through a moves-based protocol. Agents have a shared knowledge base called commitment store (CS) that is updated at every agent's move. A move in  $\mathcal{D}$  contains: (1) a speech act  $(sa \in SA)$  that is a function defining the move intention; (2) a move content  $(ct)$ ; and (3) the targeted or opponent agent towards is directed the speech act and the content. Formally, a move is a tuple  $m = \langle sa, ct, Ag_i \rangle$ , which will be defined in the following sections. We use the following speech acts assert, accept, challenge, question, ignore and reject. Then, agents may have different attitudes towards propositional speech-acts from other agents: (1) assertion attitude: an agent is confident if it can assert any proposition  $p$  for which it can build an argument  $\langle S, p \rangle$ , or it is thoughtful if asserts any proposition  $p$  for which it can build an acceptable argument  $\langle S, p \rangle$ . (2) Acceptance attitudes: an agent is credulous if it accepts any proposition  $p$  that is backed by an argument, or it is skeptical if accepts any proposition  $p$  if there is an acceptable argument  $\langle S, p \rangle$ . (3) Challenging attitudes: an agent is curious if it challenges or questions any proposition  $p$  that has an argument, or it is inquisitive if it challenges or questions proposition  $p$  backed by an acceptable argument  $\langle S, p \rangle$ . ignore and reject speech acts do not change CS, ending the dialogue as an outcome.

# Results

This section summarizes two main results: (1) a classification of gamification strategies and content from a software agent perspective as typologies in "Typologies of Gamification Strategies and Content", and (2) a formalization of

Table 2 Evaluated papers using the proposed criteria with their respective ASReview ranking  

<table><tr><td rowspan="2">Authors</td><td rowspan="2">References</td><td colspan="4">Inclusion/exclusion criteria</td><td>Assess</td><td>ASReview</td></tr><tr><td>CR1</td><td>CR2</td><td>CR3</td><td>CR4</td><td>Sum</td><td>Ranking</td></tr><tr><td>Orji, Oyibo, et al., 2017</td><td>[21]</td><td>-1</td><td>-1</td><td>0</td><td>1</td><td>-1</td><td>20</td></tr><tr><td>Klein et al., 2013</td><td>[22]</td><td>1</td><td>1</td><td>1</td><td>1</td><td>4</td><td>15</td></tr><tr><td>Ndulue Orji, 2021</td><td>[23]</td><td>1</td><td>-1</td><td>1</td><td>1</td><td>2</td><td>13</td></tr><tr><td>Klaassen et al., 2018</td><td>[24]</td><td>1</td><td>1</td><td>1</td><td>1</td><td>4</td><td>4</td></tr><tr><td>Ofli et al., 2016</td><td>[25]</td><td>1</td><td>0</td><td>1</td><td>0</td><td>2</td><td>3</td></tr><tr><td>Kekkonen Oinas-Kukkonen, 2021</td><td>[26]</td><td>1</td><td>-1</td><td>1</td><td>1</td><td>2</td><td>21</td></tr><tr><td>Ndulue Orji, 2019</td><td>[27]</td><td>1</td><td>-1</td><td>0</td><td>1</td><td>1</td><td>2</td></tr><tr><td>Kappen Orji, 2017</td><td>[28]</td><td>1</td><td>-1</td><td>0</td><td>1</td><td>1</td><td>9</td></tr><tr><td>Ndulue Orji, 2021</td><td>[29]</td><td>1</td><td>-1</td><td>1</td><td>1</td><td>2</td><td>11</td></tr><tr><td>Orji, Mandryk, et al., 2017</td><td>[30]</td><td>-1</td><td>-1</td><td>0</td><td>1</td><td>-1</td><td>6</td></tr><tr><td>den Akker et al., 2017</td><td>[31]</td><td>1</td><td>-1</td><td>0</td><td>1</td><td>1</td><td>1</td></tr><tr><td>Ross et al., 2021</td><td>[32]</td><td>1</td><td>-1</td><td>0</td><td>1</td><td>1</td><td>7</td></tr><tr><td>Senette et al., 2018</td><td>[33]</td><td>1</td><td>-1</td><td>1</td><td>1</td><td>2</td><td>17</td></tr><tr><td>Omar et al., 2019</td><td>[34]</td><td>1</td><td>-1</td><td>1</td><td>1</td><td>2</td><td>5</td></tr><tr><td>Orji, Nacke, et al., 2017</td><td>[35]</td><td>1</td><td>-1</td><td>0</td><td>1</td><td>1</td><td>8</td></tr><tr><td>Dikken, et al., 2020</td><td>[36]</td><td>1</td><td>-1</td><td>0</td><td>1</td><td>1</td><td>8</td></tr><tr><td>Chaouali, et al., 2020</td><td>[37]</td><td>1</td><td>-1</td><td>1</td><td>1</td><td>2</td><td>12</td></tr><tr><td>Rasco, et al., 2021</td><td>[38]</td><td>1</td><td>-1</td><td>0</td><td>1</td><td>1</td><td>14</td></tr><tr><td>Raman, Prashant, 2021</td><td>[39]</td><td>1</td><td>-1</td><td>0</td><td>1</td><td>1</td><td>16</td></tr><tr><td>Rasco, et al., 2020</td><td>[40]</td><td>1</td><td>1</td><td>-1</td><td>1</td><td>2</td><td>18</td></tr><tr><td>Pal, et al., 2021</td><td>[41]</td><td>1</td><td>-1</td><td>0</td><td>0</td><td>0</td><td>19</td></tr><tr><td>Bauer, et al., 2020</td><td>[42]</td><td>1</td><td>-1</td><td>0</td><td>1</td><td>1</td><td>8</td></tr><tr><td>Inchamnan, et al., 2019</td><td>[43]</td><td>1</td><td>-1</td><td>0</td><td>1</td><td>1</td><td>22</td></tr><tr><td>Steinemann et al., 2015</td><td>[44]</td><td>1</td><td>-1</td><td>0</td><td>1</td><td>1</td><td>23</td></tr><tr><td>Arcand et al., 2017</td><td>[45]</td><td>1</td><td>-1</td><td>0</td><td>0</td><td>0</td><td>24</td></tr><tr><td>Rasco, et al., 2020</td><td>[46]</td><td>1</td><td>-1</td><td>0</td><td>1</td><td>1</td><td>8</td></tr><tr><td>Soni, et al., 2021</td><td>[47]</td><td>1</td><td>-1</td><td>0</td><td>0</td><td>0</td><td>25</td></tr><tr><td>Chun et al., 2021</td><td>[48]</td><td>1</td><td>-1</td><td>0</td><td>0</td><td>0</td><td>26</td></tr><tr><td>Baptista et al., 2017</td><td>[49]</td><td>1</td><td>-1</td><td>0</td><td>0</td><td>0</td><td>27</td></tr></table>

gamification mechanisms as argument-based dialogues in "Formal Framework for Content and Strategy Selection".

# Typologies of Gamification Strategies and Content

This section presents the joint results of our systematic literature review and the expert elicitation process that we performed to define typologies of gamification strategies that can be characterized as different variations of software agency.

# SLR Results

Based on the list of selected papers (Table 2), and a set of review/survey papers [4, 15, 16, 50-53], we obtained a list of gamification strategies and gamification content presented in Table 3. In summary, persuasive strategies and content are

combined in different forms to evaluate progress and levels of human activities [22, 24, 25, 27, 28, 31, 33-35], as well as the use of rewards, which was confirmed with the state of the art i.e. the reviews and surveys that we assessed. We also found that nudges, leader boards, and simulations are used in different other fields, as other reviews and surveys show.

# Results of the Expert Elicitation

The analysis of interviews with experts revealed three main trends: (1) few of them were describing gamification strategies based on specific known mobile applications, not novel types of interactions were suggested, (2) from those three interviewees suggesting gamification strategies, progress, avatars and nudges were mentioned as a potential for behavior change, and (3) interviewees did not mention specific gamification content in the user interface (Table 4).

Table 3 List of gamified persuasive strategies and content obtained from the SLR  

<table><tr><td rowspan="2"></td><td colspan="9">Strategies</td></tr><tr><td>Nudges</td><td>Avatars</td><td>Leader boards</td><td>Challenges</td><td>Simulations</td><td>Levels</td><td>Stories</td><td>Progress</td><td>Rewards</td></tr><tr><td colspan="10">Content</td></tr><tr><td>Activity-based</td><td></td><td></td><td></td><td>[28, 28]</td><td></td><td>[24, 25, 27, 31, 33]</td><td>[28]</td><td>[22, 24, 25, 27, 28, 33-35]</td><td>[24, 33, 35] ***</td></tr><tr><td>Location-based</td><td>***</td><td></td><td></td><td></td><td>[36, 38]</td><td></td><td></td><td>[33]</td><td></td></tr><tr><td>Time-based</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>[26, 33, 34]</td><td></td></tr><tr><td>Facts and knowledge</td><td>**</td><td>[31]</td><td></td><td></td><td></td><td>[23, 27, 31]</td><td>[23, 27]</td><td></td><td></td></tr><tr><td>Questions/Info gathering</td><td></td><td></td><td></td><td></td><td></td><td>[33]</td><td></td><td>[22, 33]</td><td></td></tr><tr><td>Goal-based</td><td>***</td><td></td><td>***</td><td>[47]</td><td>* [38]</td><td>[27, 43]</td><td>[23, 27]</td><td>[22, 24, 31, 36]</td><td>[43]</td></tr><tr><td>Value-based</td><td>[37]</td><td></td><td></td><td></td><td>[44]</td><td></td><td>[23, 27]</td><td>[26]</td><td>[26, 42]</td></tr><tr><td>Emotion/feelings-based</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>[26]</td></tr><tr><td>Cooperative goal</td><td>***</td><td></td><td></td><td>[47]</td><td>*</td><td></td><td></td><td></td><td>[39]</td></tr><tr><td>Cooperative value</td><td>***</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>[39]</td></tr><tr><td>Cooperative emotions</td><td>***</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Competitive goal</td><td>*** [48]</td><td></td><td>***</td><td></td><td></td><td>[27]</td><td></td><td></td><td>***</td></tr><tr><td>Competitive value</td><td>***</td><td></td><td>***</td><td></td><td></td><td></td><td></td><td></td><td>***</td></tr><tr><td>Competitive emotions</td><td>***</td><td></td><td>***</td><td></td><td></td><td></td><td></td><td></td><td>***</td></tr></table>

Bold asterisks  $(\ast)$  indicate the use of strategies and content in other fields and contexts. We identify those categories using surveys and systematic literature reviews[4, 15, 16, 50, 50-53]  $\ast$  less used.  
**: partial used.  
***: highly used

Table 4 Results of expert elicitation where  $\boxed{\mathbb{V}}$  symbolizes that an interviewee mentioned a specific strategy during the interview highly used  

<table><tr><td rowspan="2"></td><td colspan="9">Strategies</td></tr><tr><td>Nudges</td><td>Avatars</td><td>Leader boards</td><td>Challenges</td><td>Simulations</td><td>Levels</td><td>Stories</td><td>Progress</td><td>Rewards</td></tr><tr><td>Interviewee 1</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Interviewee 2</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Interviewee 3</td><td>☑</td><td>☑</td><td></td><td></td><td></td><td></td><td></td><td>☑</td><td></td></tr><tr><td>Interviewee 4</td><td>☑</td><td></td><td></td><td></td><td></td><td>☑</td><td></td><td>☑</td><td>☑</td></tr><tr><td>Interviewee 5</td><td></td><td>☑</td><td>☑</td><td></td><td></td><td></td><td></td><td>☑</td><td></td></tr><tr><td>Interviewee 6</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Interviewee 7</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Interviewee 8</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table>

# Content Typology

The elicitation process with multidisciplinary experts and our systematic literature review revealed three types of content that are preferred and expected by experts, and well-known used in the state of the art: (1) measuring and monitoring content; (2) information-based content, and (3) social-oriented content. In this taxonomy of content (Taxonomy 1), different general types were found for example motion type relates to complex activities or simple motion logs or data tracking, location relates to context or specific spatial information, facts regarding to information-based content presented in different modalities (text, audio, visual, haptic, etc.), and goal-targeted advises or value-targeted advises or emotion-targeted advises relate to information-based content integrating a goal or a value or an emotion to stimulate another individual (or agent in general). For lack of space, we do not provide the full list of papers linked to every branch of the taxonomy.

# Persuasive Strategies Typology

Our systematic review of persuasive strategies in gamification, revealed the existence of nine main types of strategies commonly used in persuasive and coaching systems, as is presented in Taxonomy 2. We mapped these gamification strategies with three key software agency characteristics: proactiveness, reactiveness, and social awareness [54]. From a software agent perspective, a reactive strategy generates an output after the execution of an action by another agent (e.g. an individual). A proactive strategy refers to action-based outputs that are not-preceded by other agents' actions, and social behavior is any output where collective relations information regarding cooperation and competition is shared.

# Content and Strategies Compatibility

Not all the content can be used in different gamification strategies [55], therefore we propose a set of dynamic constraints that the persuader agent should use during the strategy-protocol-content selection, presented in Table 5. This matrix between content and strategies of gamification uses three levels (w.r.t complete, partial compatible, and incompatible) to assess how compatible the content is for every strategy. We used the literature review and expert opinion to design the matrix (see "Methodology"). The compatibility matrix is not exhaustive but suggests important differences among strategies. Moreover, compatibilities/incompatibilities may change when multiple types of content are used for individual strategies. We leave for future work the examination of dynamic compatibility when multiple contents are used in a gamification strategy.

# Formal Framework for Content and Strategy Selection

In this section, we introduce a framework that a persuader agent can use to select content and strategies considering the persuadee's goals, values, and emotions. We also present a decision-making algorithm that has as input relevant information about the persuadee's status, and as an outcome, it generates a set of hypothetical situations where some content and strategies are used, influencing the persuadee's goals, values and emotions.

In this paper, the persuader agent is modeled as a tuple  $Ag_{c} = \langle S, Act, G, V, E, \preceq^{*} \rangle$ , where  $S, Act, G, V, E \subseteq \Sigma$ ,  $G, V, E$  are mental states representing beliefs, values and emotions, respectively, extending the Belief-Desire-Intention (BDI) model [56] by following recent work on the attitudinal theory of emotions [57] and the value orientations theory [58]. This extension allows us to model a human agent (the persuadee perspective) with capabilities closer to a real individual, endowing a software agent with possibilities to perceive and make decisions given the potential emotions and values of a person. The rationale for such a design is that the identification of beliefs, desires, and intentions (including emotions and values) is useful when the system must communicate with humans [59].

The decision-making process that we propose (see Algorithm 1) takes as input observations of the world in terms of rule-based facts, and the agents model, and it returns as output an ordered set of hypotheses about the current state of the persuadee agent, from which the persuader may take a preferred explanation. For example generating sets of goal hypotheses such as:

![](images/88dd017fbe1d0f67d351fe4ec77c7de3b66b78f28a29de592c02b3de5b417057.jpg)

A hypothesis such as  $h_{g1}$  intuitively says: "in order to improve physical activity as a goal, then it is necessary to show goal-oriented content when the persuadee's values are aiming to be healthy, and she/he is amazed". This algorithm is an extension of an argument-based practical reasoning mechanism [60], generating goal, emotion, and value-oriented hypotheses.

Our proposed strategies' classification w.r.t the type of agency is based on the underlying assumption that the protocol selection depends on an uncertainty level of the persuadee's  $G, V, E$ . In other words, gamification strategies (and their respective protocols) for proactive or social behavior cannot be used when there is limited information (high

Algorithm 1 Generation and selection of goal, value, emotion-oriented hypotheses  
INPUT:  $Ag^{\prime} = \langle S,Act,G,V,E,\preceq^{*}\rangle$  {Agent framework} Model updateS,Act,G,V,E,  $\preceq^{*}$  1:GHypoth,VHypoth,EHypoth,Support,RelatedRules  $\leftarrow$  2:  $\mathbf{G} =$  UpdateAttitude  $G^{\prime}$ $\preceq^{G},p(G)$  3:  $\mathrm{V} =$  UpdateAttitude  $V^{\prime}$ $\preceq^{V},p(V)$  4:  $\mathrm{E} =$  UpdateAttitude  $E^{\prime}$ $\preceq^{E},p(E)$  Hypotheses generationG,V,Econclusion  $\in G,V,E$  5:  $\mathbf{S} =$  ConnectedRulesconclusion 6: RelatedRules  $= 2^{S}$  set  $\in$  RelatedRules Support  $\neq \bot$  7: Support  $=$  min(Support)U ASPset 8: GHypoth  $=\cup$  GHypoth  $=\langle$  Support,conclusion> Hypotheses selectionGHypoth,SEM 9: Graph  $=$  buildGraphGHypoth,Conflicts 10:  $\mathrm{P} = \sum_{i\in \mathrm{Graph}}p(i)$  11: NonConflicting  $=$  SEMGraph {Argumentation semantics process}   
OUTPUT:  $\langle$  Graph,  $\preceq^{*},P\rangle$ $\{* \in \{G,V,E\} \}$

Algorithm 1 has three phases or procedures: a model update (lines 1-4), a hypotheses generation (lines 5-14), and a hypotheses selection (lines 15-17). The UpdateAttitude function updates the  $G$ ,  $V$ ,  $E$  attitudes with their respective preferences. In the hypotheses generation, ASP() (line 10) is an answer-set solver function that generates stable models (see [61]). In line 15, Conflicts is a logical relation set that emerges from different hypotheses. buildGraph(in line 15) is a function creating a graph with the entire set of hypotheses  $\mathcal{H}$  as nodes, and Conflicts as edges, and in line 17 SEM() is an argument-based pattern of selection where conflicting hypotheses are discarded [62]. Finally, the output of the algorithm is an ordered set of hypotheses that are selected to be used by the persuader agent during a dialogue exchange.

uncertainty) about goals, values, or emotions modeling the agent persuadee, which suggests that the persuader should adapt to the persuadee's needs, and the need for managing incomplete information during and for gamification, as it has been suggested by previous work on persuasive gamification [7, 63].

In this paper, uncertainty about the persuadee is modeled as a probabilistic distribution representing an ambiguity degree in the hypotheses premises for which  $G, V, E$  are believed to be true. More formally, such uncertainty is represented as a belief function on  $U \subseteq \Sigma$  where  $p: \Sigma \to [0,1]$ .

In the following, we introduce an informative example where a persuader agent has to generate different hypotheses about the persuadee status. This example is part of our two-branch experimentation presented in "Experimentation".

Example 1 (Generating value-oriented hypothetical actions) A persuader uses Algorithm 1 to establish the status of a persuadee, knowing that it has a preference to follow emotional cues, i.e.  $\exists e_i, e_j \in E$  such that  $e_i \preceq e_j$ , saying that  $e_j$  is preferred than  $e_i$ , for example, the persuadee prefers to be amazed than feel grief. Let  $P$  be a program capturing the persuadee behavior with the following rules:

$$
P = \left\{ \begin{array}{c} g 1 \leftarrow S _ {1} \wedge v _ {1} \wedge e _ {1} \wedge a c t _ {1} \\ g 2 \leftarrow S _ {2} \wedge v _ {2} \wedge e _ {2} \wedge a c t _ {2} \\ g 3 \leftarrow S _ {3} \wedge v _ {3} \wedge e _ {3} \wedge a c t _ {3} \\ a c t _ {1}, a c t _ {2}, a c t _ {3} \leftarrow \top \\ v _ {1}, v _ {2}, v _ {3} \leftarrow \top \\ e _ {1}, e _ {2}, e _ {3} \leftarrow \top \\ S _ {1}, S _ {2}, S _ {3} \leftarrow \top \end{array} \right\} \tag {1}
$$

where  $g_{1} =$  "improve physical activity",  $g_{2} =$  "stay in bed",  $g_{3} =$  "keep social network",  $\nu_{1} =$  "be healthy",  $\nu_{2} =$  "seek pleasure",  $\nu_{3} =$  "be social",  $e_{1} =$  "amazement",  $e_{2} =$  "grief",  $e_{3} =$  "vigilance",  $act_{1} =$  show (goal-oriented_content),  $act_{2} =$  show (value-oriented_content),  $act_{3} =$  show (emotion-oriented_content),  $S_{1}, S_{2}, S_{3}$  are observations, considering that  $g_{1} \equiv \neg g_{2}$ , and show is a propositional action to present content, e.g. "show goal-targeted advise" in Taxonomy 1.

Using Algorithm 1, two non-contradictory sets of hypotheses are generated in line 16:

interactions. In this paper, dialogues have the following characteristics: (1) agents' communications are based on tactical moves within a protocol; (2) the persuader agent has a well-defined decision-making mechanism and follows strict protocols, and (3) the persuadee agent (e.g. a person) may not follow some postulates of well-defined dialogues [65] and can "brake" protocols. In the following, we introduce our mapping starting with an analysis of protocols and moves, then we present how agents compute a dialogue outcome.

# Protocol and Moves

We present general move alternatives corresponding to different strategies and types of software agency (proactive and reactive). This mapping, as a key contribution of this paper, is presented in Table 6, which uses  $\cdot$  and  $\odot$  to represent the starting and ending points of a protocol; we also use  $p, q \in S$  as propositions (e.g.  $q = \text{show(value\_oriented\_content)}$ ), and every move is called by one or the other agent using an additional parameter to identify it ( $Ag_{c}$  or  $Ag_{p}$ ), for example assert(show(value\_oriented\_content),  $Ag_{c}$ ).

Protocols 1 to 4 in Table 6, are initiated by the persuader agent  $(Ag_{p})$  directed to the persuadee  $(Ag_{c})$ . Conversely,  $Protocol_{5}$  to  $Protocol_{7}$  can be seen as a "reactive" moves that a persuader can take considering that the persuadee initiates the dialogue. This mapping requires formal requirements/ constraints of the persuader's internal decision-making

$$
\left\{\left\{ \begin{array}{l} h _ {g 1} = \langle \{S _ {1} \wedge v _ {1} \wedge e _ {1} \wedge a c t _ {1} \}, g _ {1} \rangle , \\ h _ {g 2} = \langle \{S _ {2} \wedge v _ {2} \wedge e _ {2} \wedge a c t _ {2} \}, g _ {2} \rangle \end{array} \right\}, h _ {g 3} = \langle \{S _ {3} \wedge v _ {3} \wedge e _ {3} \wedge a c t _ {3} \}, g _ {3} \rangle \right\} \tag {2}
$$

Then, the persuader agent selects from the output lattices (2) one set considering  $\preceq^{e}$ , for example prioritizing emotion  $e_1 =$  "amazement" than  $e_2 =$  "grief", which can be seen as an explanation of the persuadee's current state.

# Gamification Strategies as Agent Dialogues

As we have presented, gamification strategies (Taxonomy 2) have in common the exchange of information between persuader and persuadee. Those interactions follow a protocol dictating a turn-taking procedure (e.g first a persuader interaction, then a persuadee response, etc.), the type of exchange under specific circumstances, etc. For example, a reward or praise from a persuader is preceded by a persuadee action; alternatively, challenges, nudges, and parts of simulations and stories are followed by a response from the persuadee. Those exchanges can be formally specified as dialogue protocols using formal argumentation. Argument-based dialogues are strategic games between two agents (persuader and persuadee) [64], which are formal specifications of

(Algorithm 1), such as the imposition that a persuader cannot ignore or reject an assert or quest move from the persuadee. We summarize these constraints as follows:

Proposition 1 (Constraints for gamification persuasive moves) Let out be the output set from Algorithm 1 or any argument-based decision-making process that considers the next move of a persuader agent in a dialogue. Then, the following formal requirements need to hold:

- R1: For  $\text{Protocol}_2$  and  $\text{Protocol}_3$ ,  $Ag_c$  cannot reject or ignore an asset move;

R2: For  $\text{Protocol}_5$  to  $\text{Protocol}_7$ , out  $\in \text{SEM}(AF)$  and out  $\neq \emptyset$ ; and

- R3: For every assert, challenge or quest move, compatible content w.r.t the strategy should be selected (see Table 5)

# Move Selection and Outcome

The persuader agent requires a fine-grained mechanism for protocol and move selection, then we use a utility function

$\mathcal{Q}:2^{\mathcal{D}}\to \mathbb{R}$ , which evaluates the attitude uncertainty  $P$  (line 21 in 1) in a dialogues  $\mathcal{D}$ . We compute such utility as an attitude achievement w.r.t. goals, values and emotions. For example, a persuadee has as reference goal $_1$  and goal $_2$ , then every hypothesis that a persuader obtains from Algorithm 1, provides evidence of goal $_1$  and/or goal $_2$  achievement if those goals belong to out, formally: if  $m = \langle sa,ct,Ag_c\rangle$  is a move generated by agent  $Ag_{p}$  targeting agent  $Ag_{c}$ , with  $ct\in H\subseteq \mathrm{out} = SEM(AF)$ , and  $G^{R},V^{R},E^{R}\subseteq \mathcal{R}$  be the reference attitudes of  $Ag_{c}$ , then a dialogue outcome quantifier is given by:  $\mathcal{Q} = \operatorname {Sim}(\arg \max_{G,V,E}(\mathrm{ct}),\mathcal{R})$ , considering a similarity function  $\operatorname {Sim}:2^{G,V,E}\times 2^{G,V,E}\rightarrow \mathbb{R}$ .

# Experimentation

In this section, we exemplify the proposed formalization of gamification strategies using two gamified software platforms, the first one, a behavior change mobile application used in the healthcare area, and the second one, a Web-based application used for financial literacy and financial decisions balancing.

# Materials

In experiment 1 the STAR-C coaching system, we designed and implemented a mobile application using cards (see Fig. 6), which follow a user interface design pattern for navigation where available buttons are actions that a user can take w.r.t. the information presented in the card [66]. We also implemented a server-side part, such as an implementation of the Algorithm 1, and the move selection mechanism using Java with the Tweety Project library. We used lonic framework to build the cards and the entire user interface of the STAR-C system.

In experiment 2, we upgrade an existing game called Talous Tandem, which was adapted to present gamified stories of a simulated student's life. The aim of the game is to support and balance finances, social relationships, happiness, and academic success of a user, assigning points for different situations. A running version of this game can be found in https://lipas.uwasa.fi/pelit/TalousTandem/. Talous Tandem stories have a cards-design where a hypothetical situation is presented with two available choices, then, the user has to flip the card to the left or right to select an option (see Fig. 5). The Talous Tandem for this experiment was implemented in Unity, with server-side components similarly to experiment 1.

# Procedure

In our experiments, two designers and a developer tested the STAR-C platform and Talous Tandem to assess the generation of cards. Given the aim of the experiments, which did not involve perceptions or persuasiveness of the cards information, target users of these software platforms were not involved, then only laboratory tests are presented.

First, we manually elaborated different programs such as  $P$  in 1 considering alternative user parameters, e.g. changing  $G$ ,  $V$ ,  $E$  such as  $g_{1} =$  "reduce alcohol consumption",  $g_{2} =$  "eat healthy",  $g_{3} =$  "improve physical activity",  $act_{1} =$  "show measuring",  $act_{2} =$  "show facts", etc (see Fig. 6), recalling that  $g$ 's are goals of the information cards (and the persuasive act), and  $act$ 's are the gamification content type (w.r.t Taxonomy 1 of content). Then, we observed the cards generated by Algorithm 1, and the cards' results were gathered. In the following, we describe details of the two experiments as well as their results.

# Gamified Cards as Dialogues, the STAR-C Platform

Our formal framework and decision-making process presented in "Formal Framework for Content and Strategy Selection" were instantiated in a practical approach for selecting and re-ordering mobile application cards, which contain information of a persuasive nature (see Fig. 6). In this context, the argument-based hypotheses contained all the information necessary to display in a card, such as the type of content. In order to make the move-based interaction, we coded the persuadee responses or moves accept, ignore, and quest as pre-defined buttons, which are enabled or disabled depending on the followed protocol. For this experiment, we manually manipulated a probability distribution causing different uncertainty levels of the persuadee model. We manipulate a program  $P$  considering the following information:  $g_{1} =$  "improve physical activity",  $g_{2} =$  "improve diet",  $g_{3} =$  "reduce alcohol consumption",  $\nu_{1} =$  "achievement",  $\nu_{2} =$  "tradition",  $\nu_{3} =$  "hedonism",  $e_{1} =$  "amazement",  $e_{2} =$  "grief",  $e_{3} =$  "vigilance",  $act_{1} =$  show(goal-oriented_content),  $act_{2} =$  show(emotion-oriented_content),  $act_{3} =$  show/location_quant_content),  $act_{4} =$  showCALENDAR_date_content),  $act_{5} =$  show(question_content).

# Results of Experiment 1

Based on the STAR-C scenario, several hypotheses were built using Algorithm 1. In Algorithm 1, we modify  $P = \{0.01, 0.5, 0.99\}$  in the set of created hypotheses, then we limited the set  $\mathcal{H}$  to a size of 10 hypotheses. We found that in general, the persuader agent (Agp in Fig. 7) "wins"

![](images/f7121d76e6b6bf811108c062db07f2b05f4a1a4f76487d6bf5fad9a41f1da702.jpg)  
Fig. 3 Typology of gamification content

the dialogue when it has more knowledge than the persuadee, i.e. that it will provide more cards connected with proactive strategies.

Conversely, as is expected, the more uncertainty in the persuadee, the more chances that the persuader selects reactive content. For example, when uncertainty was highest (0,99 in Fig. 7), where the persuader has no previous information about  $G$ ,  $V$ ,  $E$  then, only reactive cards were placed on the top of the application, i.e. changing the order from card 1 to card 2 in Fig. 6, where every card is associated with an action, e.g.  $act_2 = \text{show(emotion-oriented_content)}$ .

# Gamified Stories as Dialogues, Talous Tandem

We modified the TalousTandem game compelling the user to make a decision, i.e. avoid ignore, reject, and accept moves, only assert-ing whit left or right swipes. The rationale for this design decision was based on the idea of making the dialogue-based game short and simple. We aim in our future work to implement other moves types to enrich the game possibilities. Figure 8 presents de protocol used for the cards game used in experiment 1. In this setting, the game generates a tree-like structure that has a definite size, the dialogue tree was implemented as a game tree in Unity $^{10}$  using Play Maker $^{11}$  plugin.

# Outcome of the Talous Tandem

Different ending rules were implemented in the Talous Tandem based on the individual variable score (w.r.t. finance, social, etc.). Such rules were tailored by the designers to generate always positive feedback regardless of the reached score. Figure 9 presents screenshots of three different

dialogue outcomes. As part of our future work, we will update those handcrafted rules made for the game with automatic processes, as it is presented in the argumentation state of the art (see [67] as an example).

# Discussion and Future Work

In this section, we contrast in-depth our contributions with the state of the art, considering three points: (1) the taxonomies proposed; (2) the mechanisms for decision-making that we presented, and (3) the use of formal argumentation as a mechanism to formalize stories as a gamified strategy.

# Taxonomies of Gamified Elements

The type of gamification presented in this work entails the use of software-based visual cues to persuade a user. In the gamification literature, those gamification affordances have been the object of different studies, exploring user orientation and the relationship with game elements [7-9], investigating gamified cues to motivate and induce emotions/feelings [3, 4], and examining if some of these affordances are suitable for social-oriented tasks (e.g. cooperative or competitive) [2, 10]. As it has been highlighted in [11], gamification elements are not consistently defined nor used in consensus, therefore different approaches have classified them considering motivation and effects on user's behavior [12], depending on the type of artifacts from a development perspective [13], classifying affordances types depending on the application of different levels of design principles [14], and structuring game elements depending on the engagement experiences in users [11]. All these previous efforts have investigated gamified software as static individual artifacts, being common that affordances do not change during the gamified task (see [68] as a review of empirical studies).

![](images/79155cd3bfc7cdae018b60129078b131ca999bedd79482c619840c368e86b8cc.jpg)  
Fig.4 Typology of gamification strategies

Table 5 Content-strategies compatibility  

<table><tr><td rowspan="3" colspan="3"></td><td colspan="16">Content</td></tr><tr><td colspan="5">Measuring</td><td colspan="4">Information</td><td colspan="7">Social</td></tr><tr><td>Motion quantification</td><td>Motion quantification</td><td>Location quantification</td><td>Location quantification</td><td>Calendar/date</td><td>Facts</td><td>Questions</td><td>Goal-targ. advise</td><td>Value-targ. advise</td><td>Emotion-targ. advise</td><td>Cooper. goal</td><td>Cooper. value</td><td>Cooper. emotion</td><td>Compet. goal</td><td>Compet. value</td><td>Compet. emotion</td></tr><tr><td rowspan="10">Strategies</td><td rowspan="3">Social</td><td>Avatar</td><td>1</td><td>1</td><td>1</td><td>1</td><td>★</td><td>★</td><td>★</td><td>★</td><td>★</td><td>★</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td></tr><tr><td>Simulations</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>★</td><td>★</td><td>★</td><td>★</td><td>★</td><td>★</td><td>★</td><td>★</td><td>★</td><td>★</td><td>★</td></tr><tr><td>Stories</td><td>1</td><td>1</td><td>1</td><td>1</td><td>★</td><td>★</td><td>★</td><td>★</td><td>★</td><td>★</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td></tr><tr><td rowspan="2">Proactive</td><td>Challenges</td><td>☆</td><td>☆</td><td>☆</td><td>☆</td><td>☆</td><td>★</td><td>★</td><td>★</td><td>★</td><td>★</td><td>★</td><td>★</td><td>★</td><td>★</td><td>★</td><td>★</td></tr><tr><td>Nudges</td><td>☆</td><td>☆</td><td>☆</td><td>☆</td><td>☆</td><td>☆</td><td>☆</td><td>★</td><td>★</td><td>★</td><td>★</td><td>★</td><td>★</td><td>★</td><td>★</td><td>★</td></tr><tr><td rowspan="5">Reactive</td><td>Praise</td><td>★</td><td>★</td><td>★</td><td>★</td><td>★</td><td>★</td><td>☆</td><td>1</td><td>1</td><td>1</td><td>☆</td><td>☆</td><td>☆</td><td>☆</td><td>☆</td><td>☆</td></tr><tr><td>Leader boards</td><td>★</td><td>★</td><td>★</td><td>★</td><td>★</td><td>☆</td><td>☆</td><td>1</td><td>1</td><td>1</td><td>★</td><td>★</td><td>★</td><td>★</td><td>★</td><td>★</td></tr><tr><td>Levels</td><td>★</td><td>★</td><td>★</td><td>★</td><td>★</td><td>☆</td><td>☆</td><td>☆</td><td>☆</td><td>☆</td><td>☆</td><td>☆</td><td>☆</td><td>☆</td><td>☆</td><td>☆</td></tr><tr><td>Progress</td><td>★</td><td>★</td><td>★</td><td>★</td><td>★</td><td>☆</td><td>☆</td><td>☆</td><td>☆</td><td>☆</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td></tr><tr><td>Rewards</td><td>★</td><td>★</td><td>★</td><td>★</td><td>☆</td><td>☆</td><td>☆</td><td>☆</td><td>☆</td><td>☆</td><td>☆</td><td>☆</td><td>☆</td><td>☆</td><td>☆</td><td>☆</td></tr></table>

$\star$  : complete compatibility.  
partial compatibility.  
☆: incompatibility.

In contrast, in this paper we considered software-based gamification elements reactive, i.e. with the aforementioned static visual behavior, but also as the potentially proactive and social following the well-established perspective of agent-based software (see [54]), which are endowed with cognitive-like procedures that make every agent potentially autonomous for changing its goals, beliefs, and intentions.

We divided the gamification elements into content and strategies, which has a similarity with the MDA model presented in [13], seeing affordances as software artifacts

with different information-based nature. On the one side, the content taxonomy (Taxonomy 1 in Fig. 3) is based on the type of data presented with respect to measuring, high-level feedback information, and social-related information, this classification is important when the source, structure, and quality of the information need to be specified to be stored and manipulated. On the other hand, the strategies taxonomy (Taxonomy 2 in Fig. 4) reflects the type of agency that a gamified element is (or might be) able to perform, with respect to information that is generated and transmitted, for

Table 6 Typology of gamification strategies used in intelligent persuasive/coaching systems  

<table><tr><td rowspan="2">Proactive</td><td>Challenges</td><td>AgpAgc</td><td>Protocol1: assert(p, Agc); ignore(q, Agp)◎
Protocol2: assert(p, Agc); accept(q, Agp)◎
Protocol3: assert(p, Agc); challenge(q, Agp)◎
Protocol4: assert(p, Agc); reject(q, Agp)◎</td></tr><tr><td>Nudges</td><td></td><td>Protocol5: assert(p, Agp); assert(p, Agc)◎
Protocol6: assert(p, Agp); accept(q, Agc)◎
Protocol7: assert(p, Agp); challenge(q, Agc)◎</td></tr><tr><td rowspan="4">Reactive</td><td>Praise</td><td>AgpAgc</td><td></td></tr><tr><td>Leader boards</td><td></td><td></td></tr><tr><td>Levels</td><td></td><td></td></tr><tr><td>Progress Rewards</td><td></td><td></td></tr></table>

![](images/a2213c0e8d68d9a247792322da0ef0482dcf5fa7e927b07820d158670263d3a9.jpg)  
Fig. 5 Card of the Talous Tandem game with the four value-changing variables, finance, social, friendship/love, academic performance. Left image, swipe action to the left displaying a greetings message. Right image, the same card when user made a right swipe displaying a fact-oriented message

![](images/6b5681e25ddc7adc24ab347d8df9f3e4eb5bc8033cbc6ebacc4d81ecfbf8e932.jpg)

![](images/d7cf32922e7dbba02dabbd3588988a7982fe414b430b9ae65f7f7f50506f14c5.jpg)  
Fig. 6 Experiment 1, the STAR-C platform: mobile application where cards are used as content within persuader moves. Left and left-center (card 1 and card 2) are cards using information and measuring type  
content, respectively. Right and center-right figures show cards with information regarding eating and physical activity, using goal-oriented nudges and fact messages

![](images/e911cdac00e1920ff7404a3cc719c31681880f8c714d8b4a8cfcf60b5d1623e3.jpg)  
Fig. 7 Uncertainty  $P$  of the agent's model vs protocol winner

example, an affordance such as a level or a reward visual indicator is completely different from an avatar or a story, which are oriented to exchange information with a user.

In the gamification literature, the taxonomy of game elements in the educational domain continuously improved in [69-71] is related to the environment that the gamification is being implemented, and it has a close relationship with other classifications where the psychological effects of those affordances are considered, see for example [3, 4]. Indeed, the work of Toda et al. in [69] is focused on the particular area of education with potential use in other contexts. Similar to

Todag's work, in [72] a taxonomy of game elements, with game attributes and their effects on learning is presented. This work has remarkable similarities to Toda's but uses a different methodology, which is analogous to our approach, using a systematic review and using expert opinion. As part of our future work, we want to empirically evaluate our taxonomies in the financial and financial literacy area.

A catalog of gamification patterns presented in [76, 77] is a well-elaborated and empirical collection of gamified approaches, that was established for mobile applications aiming to increase student motivation in a learning context. Inspired by these catalogs, we hope to empirically test what branches of the proposed taxonomies fit better for improving persuasion and motivation. Moreover, we agree with the authors of [76] that the use of gamified applications is not enough to motivate and persuade, it is necessary to complement with other alternatives (e.g. traditional education), since gamification can generate in the student's indices of distraction in the medium and long term [76].

The two taxonomies presented here are the result of expert elicitation and a systematic literature review and lack empirical evaluation and testing, which is part of future work, considering that experiment 2 with the Talous Tandem software is our current ongoing project.

![](images/c9e4ca6fc2d7cd5104cabc0e7aba07329fe9421718344cfd2b2185daeeb6d00a.jpg)  
Fig. 8 Left, protocol followed by the modified version of the Talous Tandem game. A user can select one of the two alternative assert moves. Right image, screenshot of the induced tree from the dialogue protocol, implemented in Unity using the Play Maker plugin

![](images/d92925b1ba08d065bbd2a29305569d09ba807c78c8923dad9ac9d81af516700c.jpg)

![](images/f7c8e9df254c2544caac7b5e3ca4f6e13fac0109f3da7a0635791372e1d76067.jpg)  
Fig.9 Screenshots of ending cards of the Talous Tandem, these last moves are handcrafted from outcome rules that depend on the four variables: finance, social, friendship/love, academic performance

# Mechanisms for Automatic Selection/Decision-Making in Gamification

In this paper, we proposed a general algorithm that generates alternatives for selecting gamified content (w.r.t. content taxonomy) considering the user profile. The main characteristic of Algorithm 1 is its non-monotonicity, meaning that when input information changes the output also changes, which is different from most of the algorithms in programming languages or mathematical functions. A non-monotonic behavior guarantees a reasoning process closed to human decision-making. Similar to medical doctors that dictate a diagnosis, but under more evidence they may change the final word, the decision-making process in our proposed algorithm generates valid and sound alternatives of what the game should present, but under more information about the user, the algorithm may change its output. Our approach is novel in the gamification literature considering the characterization framework and the methodological direction. Previous work, for example, the model presented in [13], only mentioned the potential use of artificial intelligence with no specific formalization.

Algorithm 1 is an extension of a general reasoning process based on abstract argumentation introduced in [62], and a derivation for generating alternative scenarios for human activities presented in [73]. The two main phases of this generic decision-making process: hypotheses generation and hypotheses selection have different computational costs, being the selection of hypotheses computationally intractable, i.e. NP-hard or even harder under some argumentation semantics SEM (see [74] for complete complexity analysis of the associated reasoning problem). The computational complexity of the problem for selecting a set of the best" gamification strategies or content depending on parameters of the user profile, varies with the size of the user profile and the number of gamification affordances. However, as we presented in Table 5, not all content types and strategies are compatible (as suggested by other gamification authors, see [7, 69, 72]), then the time for generation of gamification alternatives induced by Algorithm 1 may decrease. Furthermore, in a context where a game is repeatedly played by a user, a learning mechanism can be added to our algorithm to not "run" in every move, but using a machine learning process to generate an output faster. This type of hybrid mechanism is part of our future work to be implemented in the new version of Talous Tandem.

# Gamification Strategies as Argument-Based Dialogues

Mathematical characterizations of specific software components are useful to ensure the correct behavior of those modules. Such formalization not only guarantees that the

information-based output follows the intended goal of the software, but also can be used to predict "extreme" use conditions, such as the use of a module under no information, incorrect or incomplete data structures, or large size (even infinite) of information as input. In gamification literature, the use of formal approaches to describe gamification elements and mechanisms is almost nonexistent, as far as we review the literature, which has been one of the strong criticisms and missing research tracks of the gamification literature [4]. Gamified strategies such as stories or avatar interactions require consistent exchanges of information given that the nature of "gamification" implies behavior change, for example, to keep a goal-oriented storyline, the use of an agreed language, vocabulary, or visual cues that persuadee and persuader understand, the acknowledgment of a start and an ending in the exchanges, etc. All those rules, that for humans are implicit in most regular conversations, for interactive software should be explicitly defined. In that sense, in the formal argumentation literature researchers have devoted themselves to specifying different types of goal-oriented dialogue games such as persuasive, deliberative, negotiation-oriented, and even eristic or "fighting" exchanges (see [64]). Then, the use of formal argumentation to describe some gamified strategies such as stories is a useful approach to guarantee the completion of persuasive dialogue goals (see [75] for a description of persuasion dialogues in behavior change contexts).

# Autonomy of Gamification Systems

In this paper, we present theoretical and laboratory-tested experimental approaches for what we called autonomous gamification, meaning that gamified software makes decisions based on its own goals, for example running Algorithm 1 without any user input. An autonomous agent is not dependent on the goals of others, it possesses goals that are generated from within rather than adopted [54]. In this context of autonomy, it may necessary to consider persuasive gamification systems that align automatically to the users' goals (see for example [61]), however, such computational processes are currently under debate given that may imply the need for guidelines or rules for designing artificial intelligence-based systems, such as the joint effort that the European Union and other leading countries to develop guidelines for trustworthy AI.[12] In this regard, four principles for autonomous gamification were presented in [78]: traceability of gamified outputs, internal consistency of a gamification attempt, coherent gamified interaction, and rational persuasive gamification. These principles although suitable for the

paper presented here, they are not covering other potential issues that may arise with the use of autonomous software, as has been pointed out by different authors in the artificial intelligence field (e.g. [81]). In our future work, we want to present a set of design principles for autonomous gamification usable for formal computer scientists as well as gamification practitioners.

# Limitations

We acknowledge at least three types of limitations in our contributions: (1) the constraints of our systematic literature review and the expert elicitation process. We are aware that biases during processes of selection and expert judgment could have led to the generation of other types of gamification content and strategies in the proposed taxonomies. (2) The lack of a strict formalization and proof realization of our proposed decision-making algorithm and the dialogue protocols. We understand that characterizations in the argumentation literature require an accurate procedure, however, we decided to leave such formalization for future work in a different venue, we considered that the goals of the paper were not oriented to a rigorous argumentation theory-related context. And 3) we did not make user-oriented empirical experimentation, instead we opted for designing high-level laboratory experiments given that the goal of the paper was introduced novel contributions of what we can call "formal gamification". Part of our future work, as we have expressed is devoted to solving some of those limitations and continuing our research line in gamification from the perspective of computer science, specifically from artificial intelligence.

# Conclusions

Persuasive gamification is a rising research track where empirical theories and models of behavior change (e.g. self-determination theory, flow theory, etc.) are used along game-oriented (or gamified) tools to promote change [80]. Gamification as a design process, employs game elements (affordances) into different types of systems and services with the goal of affording gameful experiences [79]. Usually, in persuasive gamification traits (e.g. social-orientation [2], emotion-orientation [3], etc.) are used as a means for tailoring software, which although promising, it presents a problem of highly specialization (lack of generalization of the approaches). Despite an apparent immaturity of theoretical foundations and validated methods [4], gamification has increased popularity for designing software that covers enjoyment, immersion and goal-orientation being a conventional approach for behavior change [5, 6]. In this context, is clear that gamification literature uses methods and approaches from social sciences, rather from computer

science area. This was our starting point for this research project, a general lack of formal computational models of gamified approaches.

Therefore, in this paper we started with two problems in the gamification research literature: (1) gamification affordances have been considered as static software elements, with no proactive, autonomous, or semi-autonomous behavior, and (2) the current efforts for classifying gamification affordances have been focused on the psychological outcomes that emerge from the user-game interaction, but not from a computer science design perspective where characteristics of the information involved in the gamified content are considered.

In this context, we provide three contributions in the interdisciplinary area that we called "formal gamification", which is the strict characterization of gamification approaches from an artificial intelligence perspective. Our contributions are (1) two taxonomies of gamified affordances, the first one oriented to identify different types of gamification content considering the class of information that communicate, and the second, a taxonomy of gamification mechanisms, that we called strategies, considering the type of agency (w.r.t. proactive and reactive) that the gamified software is oriented. (2) a decision-making algorithm that enables a gamified software with capabilities of personalization and adaptation, generating consistent outputs at the same time that has a non-monotonic behavior. Finally, (3) we present two laboratory empirical experiments showing how the taxonomies and the decision-making algorithm can be used in practical gamified tasks.

Acknowledgements This work and the project Digiconsumers was supported by the Academy of Finland Strategic Research Council, project number: 327241, and also the European Regional Development Fund (A75418).

Funding Open Access funding provided by University of Vaasa (UVA).

# Declarations

Conflict of interest On behalf of all authors, the corresponding author states that there is no conflict of interest.

Open Access This article is licensed under a Creative Commons Attribution 4.0 International License, which permits use, sharing, adaptation, distribution and reproduction in any medium or format, as long as you give appropriate credit to the original author(s) and the source, provide a link to the Creative Commons licence, and indicate if changes were made. The images or other third party material in this article are included in the article's Creative Commons licence, unless indicated otherwise in a credit line to the material. If material is not included in the article's Creative Commons licence and your intended use is not permitted by statutory regulation or exceeds the permitted use, you will need to obtain permission directly from the copyright holder. To view a copy of this licence, visit http://creativecommons.org/licenses/by/4.0/.

# References

1. Deterding S, Dixon D, Khaled R, Nacke L. From game design elements to gamefulness: Defining "gamification". In: Proceedings of the 15th international academic MindTrek conference: envisioning future media environments. MindTrek '11. Association for Computing Machinery, New York, NY, USA; 2011, p. 9-15.  
2. Morschheuser B, Riar M, Hamari J, Maedche A. How games induce cooperation? A study on the relationship between game features and we-intentions in an augmented reality game. Comput Hum Behav. 2017;77:169-83.  
3. Mullins JK, Sabherwal R. Gamification: a cognitive-emotional view. J Bus Res. 2020;106:304-14.  
4. Koivisto J, Hamari J. The rise of motivational information systems: a review of gamification research. Int J Inf Manag. 2019;45:191-210.  
5. Alahäïvalä T, Oinas-Kukkonen H. Understanding persuasion contexts in health gamification: a systematic analysis of gamified health behavior change support systems literature. Int J Med Inform. 2016;96:62-70.  
6. Cugelman B. Gamification: what it is and why it matters to digital health behavior change developers. JMIR Serious Games. 2013;1(1):3139.  
7. Tondello GF, Wehbe RR, Diamond L, Busch M, Marczewski A, Nacke LE. The gamification user types hexad scale. In: Proceedings of the 2016 annual symposium on computer-human interaction in play; 2016. p. 229-43.  
8. Santos ACG, Oliveira W, Hamari J, Rodrigues L, Toda AM, Palomino PT, Isotani S. The relationship between user types and gamification designs. User Model User-Adapt Inter. 2021;31(5):907-40.  
9. Hallifax S, Serna A, Marty J.-C, Lavoué G, Lavoué E. Factors to Consider for Tailored Gamification. In: CHI PLAY '19: Proceedings of the annual symposium on computer-human interaction in play. Association for Computing Machinery, New York, NY, USA; 2019. p. 559-72.  
10. Vegt N, Visch V, de Ridder H, Vermeeren A. Designing gamification to guide competitive and cooperative behavior in teamwork. In: Gamification in education and business. Springer, Cham; 2014. p. 513-33.  
11. Liu D, Santhanam R, Webster J.: Toward meaningful engagement: a framework for design and research of gamified information systems. MIS Q. 2017;41(4):1011-1034.  
12. Mekler ED, Bruhlmann F, Opwis K, Tuch AN. Disassembling gamification: the effects of points and meaning on user motivation and performance. In: CHI EA '13: CHI '13 extended abstracts on human factors in computing systems. Association for Computing Machinery, New York, NY, USA; 2013, p. 1137-42.  
13. Hunicke R, LeBlanc M, Zubek R. Mda: a formal approach to game design and game research. In: Proceedings of the AAAI workshop on challenges in game AI, vol. 4, San Jose, CA; 2004. p. 1722  
14. Deterding S, Dixon D, Khaled R, Nacke L. From game design elements to gamefulness: defining In: MindTrek '11: Proceedings of the 15th international academic mindtrek conference: envisioning future media environments. Association for Computing Machinery, New York, NY, USA; 2011. p. 9-15.  
15. Hamari J, Koivisto J, Pakkanen T. Do persuasive technologies persuade?-a review of empirical studies. In: International conference on persuasive technology. Springer; 2014. p. 118-36.  
16. Klock ACT, Gasparini I, Pimenta MS, Hamari J. Tailored gamification: a review of literature. Int J Hum Comput Stud. 2020;144:102495.  
17. van Eemeren FH, Eemeren FH, Garssen B, Krabbe ECW, Henkemans AFS, Verheij B, Wagemans JHM. Handbook of argumentation theory. Dordrecht: Springer; 2019.

18. Guerrero E, Lindgren H. Typologies of persuasive strategies and content: a formalization using argumentation. In: International Conference on practical applications of agents and multi-agent systems. Springer; 2021. p. 101-13.  
19. Kitchenham B. Procedures for performing systematic reviews, vol. 33. Keele: Keele University; 2004. p. 1-26.  
20. Charmaz K. Grounded theory: methodology and theory construction. In: International encyclopedia of the social and behavioral sciences., Oxford, England, UK: Pergamon; 2001 p. 6396-9.  
21. Orji R, Oyibo K, Tondello GF. A comparison of system-controlled and user-controlled personalization approaches. In: Adjunct publication of the 25th conference on user modeling, adaptation and personalization; 2017. p. 413-8.  
22. Klein M, Mogles N, van Wissen A. An intelligent coaching system for therapy adherence. IEEE Pervasive Comput. 2013;12(3):22-30.  
23. Ndulue C, Orji R. Covid dodge: an African-centric game for promoting Covid-19 safety measures. In: 3rd African human-computer interaction conference: inclusiveness and empowerment; 2021. p. 166-9.  
24. Klaassen R, Bul K, Op den Akker R, Van der Burg GJ, Kato PM, Di Bitonto P. Design and evaluation of a pervasive coaching and gamification platform for young diabetes patients. Sensors. 2018;18(2):402.  
25. Ofli F, Kurillo G, Obdrzalek S, Bajcsy R, Jimison HB, Pavel M. Design and evaluation of an interactive exercise coaching system for older adults: lessons learned. IEEE J Biomed Health Inform. 2015;20(1):201-12.  
26. Kekkonen M, Oinas-Kukkonen H. Doctoral students' battle of stress—designing BCSS to help them win the battle: searching for design improvements via workshops with end-users. In: CEUR workshop Proceedings, vol. 2885; 2021. p. 47-64.  
27. Ndulue C, Orji R. Driving persuasive games with personal eg devices: strengths and weaknesses. In: Adjunct publication of the 27th conference on user modeling, adaptation and personalization; 2019. p. 173-7.  
28. Kappen D.L, Orji R. Gamified and persuasive systems as behavior change agents for health and wellness. XRDS: Crossroads. ACM Mag Students 2017;24(1), 52-5.  
29. Ndulue C, Orji R. Gender and the effectiveness of a persuasive game for disease awareness targeted at the African audience. In: Adjunct Proceedings of the 29th ACM conference on user modeling, adaptation and personalization; 2021. p. 318-24.  
30. Orji R, Mandryk RL, Vassileva J. Improving the efficacy of games for change using personalization models. ACM Trans Comput Hum Interact (TOCHI). 2017;24(5):1-22.  
31. den Akker RO, Klaassen R, Bul K, Kato PM, van der Burg G-J, di Bitonto P. Let them play: Experiences in the wild with a gamification and coaching system for young diabetes patients. In: Proceedings of the 11th EAI international conference on pervasive computing technologies for healthcare; 2017. p. 409-18.  
32. Ross M, Broz F, Baillie L. Observing and clustering coaching behaviours to inform the design of a personalised robotic coach. In: Proceedings of the 23rd international conference on mobile human-computer interaction; 2021. p. 1-17.  
33. Senette C, Buzzi MC, Paratore MT, Trujillo A. Persuasive design of a mobile coaching app to encourage a healthy lifestyle during menopause. In: Proceedings of the 17th international conference on mobile and ubiquitous multimedia; 2018. p. 47-58.  
34. Omar MYB, Rambli DRA, Sulaiman S, Shiratuddin MF, Merienne F, Vanhalle D. Proposed conceptual design model of persuasive game for upper limb for stroke rehabilitation. In: 2019 IEEE conference on graphics and media (GAME). IEEE; 2019. p. 44-8.  
35. Orji R, Nacke LE, Di Marco C. Towards personality-driven persuasive health games and gamified systems. In: Proceedings of

the 2017 CHI conference on human factors in computing systems; 2017. p. 1015-27.  
36. Dikken O, Prakash K, Roseboom B, Rubio A, Østvik S, Bueno M, Salamon NZ, Bidarra R. A serious game for changing mindsets about loans for home retrofitting. In: International conference on games and learning alliance. Springer; 2020. p. 347-61.  
37. Chaouali W, Lunardo R, Yahia IB, Cyr D, Triki A. Design aesthetics as drivers of value in mobile banking: does customer happiness matter? Int J Bank Mark 2019;219-241.  
38. Rasco A, Chan J, Peko G, Sundaram D. Evolution of serious games to support lifelong learning and decision making: Design and implementation of a financial literacy game. In: Proceedings of the 54th Hawaii International Conference on System Sciences, 2021;p. 64.  
39. Raman P. Examining the importance of gamification, social interaction and perceived enjoyment among young female online buyers in India. Young Consumers. Emerald Publishing Limited; 2020. vol. 22. No. 3. pp. 387-412. https://doi.org/10.1108/YC-05-2020-1148.  
40. Rasco A, Chan J, Peko G, Sundaram D. Fincraft: immersive personalised persuasive serious games for financial literacy among young decision-makers. In: Proceedings of the 53rd Hawaii international conference on system sciences; 2020. p. 32-41.  
41. Pal A, Indapurkar K, Gupta KP. Gamification of financial applications and financial behavior of young investors. Young Consumers. Emerald Publishing Limited; 2021. vol. 22 No. 3. pp.503-519. https://doi.org/10.1108/YC-10-2020-1240.  
42. Bauer J.C, Linzmajer M, Nagengast L, Rudolph T, D'Cruz E. Gamifying the digital shopping experience: games without monetary participation incentives increase customer satisfaction and loyalty. J Serv Manag. 2020;563-595.  
43. Inchamnan W, Niranatlamphong W, Engbunmeesakul N. Gamification-driven process: financial literacy in Thailand. In: 2019 17th international conference on ICT and knowledge engineering (ICT&KE). IEEE; 2019. p. 1-6.  
44. Steinemann ST, Mekler ED, Opwis K. Increasing donating behavior through a game for change: the role of interactivity and appreciation. In: Proceedings of the 2015 annual symposium on computer-human interaction in play; 2015. p. 319-29.  
45. Arcand M, PromTep S, Brun I, Rajaobelina L. Mobile banking service quality and customer relationships. Int J Bank Mark. 2017;1068-1089.  
46. Rasco A, Chan J, Peko G, Sundaram D. Serious financial games for youth: An evolutionary action design science approach. In: Americas conference on information systems. The University of Auckland Business School Research Paper. 2020.  
47. Soni M, Jain K, Jajodia I. Mobile health (mhealth) application loyalty in young consumers. Young Consumers. Emerald Publishing Limited; 2021. vol. 22 No. 3. pp. 429-455. https://doi.org/10.1108/YC-10-2020-1236.  
48. Chun S, Johnson DS. The effects of mental budgeting and pain of payment on the financial decision making of socially excluded people. Int J Bank Mark. 2021;886-899.  
49. Baptista G, Oliveira T. Why so serious? gamification impact in the acceptance of mobile banking services. Internet Res. 2017.  
50. de Sousa Borges S, Durelli VH, Reis HM, Isotani S. A systematic mapping on gamification applied to education. In: Proceedings of the 29th annual ACM symposium on applied computing; 2014. p. 216-22.  
51. Orji R, Moffatt K. Persuasive technology for health and wellness: state-of-the-art and emerging trends. Health Inform J. 2016;24(1):66-91.  
52. Thach KS, Phan TPN. Persuasive design principles in mental health apps: A qualitative analysis of user reviews. In: 2019 IEEE-RIVF international conference on computing and communication technologies (RIVF). IEEE; 2019. p. 1-6.

53. Monteiro-Guerra F, Rivera-Romero O, Fernandez-Luque L, Caulfield B. Personalization in real-time physical activity coaching using mobile applications: a scoping review. IEEE J Biomed Health Inform. 2019;24(6):1738-51.  
54. Wooldridge M, Jennings NR. Agent theories, architectures, and languages: a survey. Berlin: SpringerLink; 1994. p. 1-39.  
55. Johnson D, Deterding S, Kuhn K-A, Staneva A, Stoyanov S, Hides L. Gamification for health and wellbeing: a systematic review of the literature. Internet Interv. 2016;6:89-106.  
56. Bratman M, Bratman ME. Intention, plans, and practical reason, vol. 100. Harvard University Press; Cambridge, MA, USA. 1991. p. 277. https://doi.org/10.2307/2185304.  
57. Deonna JA, Teroni F. Emotions as attitudes. Dialectica. 2015;69(3):293-311.  
58. Schwartz SH. Universals in the content and structure of values: theoretical advances and empirical tests in 20 countries. In: Advances in experimental social psychology, vol. 25., Cambridge, MA, USA: Academic Press; 1992, p. 1-65.  
59. Rao A., Georgeff MP, et al: Bdi agents: from theory to practice. In: ICMAS, vol. 95; 1995. p. 312-9.  
60. Guerrero E, Lindgren H. Practical reasoning about complex activities. In: International conference on practical applications of agents and multi-agent systems. Springer; 2017. p. 82-94.  
61. Guerrero E, Nieves JC, Lindgren H. Semantic-based construction of arguments: an answer set programming approach. Int J Approx Reason. 2015;64:54-74.  
62. Dung PM. On the acceptability of arguments and its fundamental role in nonmonotonic reasoning, logic programming and n-person games. Artif Intell. 1995;77(2):321-57.  
63. Orji R, Tondello GF, Nacke LE. Personalizing persuasive strategies in gameful systems to gamification user types. In: Proceedings of the 2018 CHI conference on human factors in computing systems; 2018. p. 1-14.  
64. Walton D, Krabbe ECW. Commitment in dialogue: basic concepts of interpersonal reasoning. SUNY series in logic and language. New York: State University of New York Press; 1995. p. 223.  
65. Amgoud L, de Saint-Cyr FD. An axiomatic approach for persuasion dialogs. In: 2013 IEEE 25th international conference on tools with artificial intelligence. IEEE; 2013. p. 618-25.  
66. Neil T. Mobile design pattern gallery: UI patterns for Smartphone apps. Newton: O'Reilly Media; 2014. p. 385.  
67. Yan C, Lindgren H, Nieves JC. A dialogue-based approach for dealing with uncertain and conflicting information in medical diagnosis. Auton Agent Multi-Agent Syst. 2018;32(6):861-85.  
68. Hamari J, Koivisto J, Sarsa H. Does gamification work? A literature review of empirical studies on gamification. In: 2014 47th Hawaii international conference on system sciences. IEEE; 2014. p. 3025-34.  
69. Toda AM, Klock AC, Oliveira W, Palomino PT, Rodrigues L, Shi L, Bittencourt I, Gasparini I, Isotani S, Cristea AI. Analysing gamification elements in educational environments using an existing gamification taxonomy. Smart Learn Environ. 2019;6(1):1-14.  
70. Toda AM, Palomino PT, Oliveira W, Rodrigues L, Klock AC, Gasparini I, Cristea AI, Isotani S. How to gamify learning systems? An experience report using the design sprint method and a taxonomy for gamification elements in education. J Educ Technol Soc. 2019;22(3):47-60.  
71. Toda AM, Oliveira W, Klock AC, Palomino PT, Pimenta M, Gasparini I, Shi L, Bittencourt I, Isotani S, Cristea AI. A taxonomy of game elements for gamification in educational contexts: proposal and evaluation. In: 2019 IEEE 19th international conference on advanced learning technologies (ICALT), vol. 2161. IEEE; 2019. pp. 84-8.  
72. Bedwell WL, Pavlas D, Heyne K, Lazzara EH, Salas E. Toward a taxonomy linking game attributes to learning: an empirical study. Simul Gaming. 2012;43(6):729-60.

73. Guerrero E, Nieves JC, Sandlund M, Lindgren H. Activity qualifiers using an argument-based construction. Knowl Inf Syst. 2018;54(3):633-58.  
74. Dvorak W, Dunne PE. Computational problems in formal argumentation and their complexity. Handbook of formal argumentation. 2018. vol. 4 No. 8. pp. 2557-2622. http://www.collegepublications.co.uk/downloads/ifcolog00017.pdf.  
75. Hunter A. Towards a framework for computational persuasion with applications in behaviour change. Argum Comput. 2018;9(1):15-40.  
76. Taborda M, Johnny P, Arango L, Jefferson C, Cesar A, Gutierrez V, Francisco L. A proposal of a catalog of gamification patterns: a way to improve the learning motivation. J Inf Technol Res (JITR). 2019;12:34-49.  
77. Arango-Lopez J, Ruiz S, Taborda J, Gutierrez V, Francisco L, Collazos CA. Gamification patterns: a catalog to enhance the learning motivation. J Inf Technol Res (JITR). 2017;1-7.

78. Guerrero E, Xi, N, Vartiainen T, Kalmi P. What if gamified software is fully proactive? Towards autonomy-related design principles. CEUR workshop Proceedings, In: Personalized persuasive technologies workshop (PPT2022) proceedings. To appear; 2022,  
79. Kai H, Juho H. A definition for gamification: anchoring gamification in the service marketing literature. *Electron Mark.* 2017;27(1):21-31.  
80. Böckle Novak J, Bick M. Exploring gamified persuasive system design for energy saving. J Enterp Inf Manag. 2020.  
81. Virginia D. Responsibility and artificial intelligence, vol. 4698. Oxford: Oxford University Press; 2020. p. 1337-1356

Publisher's Note Springer Nature remains neutral with regard to jurisdictional claims in published maps and institutional affiliations.
