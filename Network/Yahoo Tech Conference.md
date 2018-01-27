# Yahoo Japan Tech Conference
- Extreme Programming : 16時30分から

### 1st Session : Kotlin  
how to distribute Kotlin within Yahoo  
  - kickoff seminar
  - KotlinConf
  - create Kotlin community!  
  ->  in-house community

  How's Kotlin doing in Yahoo?
  - newly written code in Kotlin: takes about 30% of total LoC

  How are things different after implementing Kotln?
  - easy to read
  - overwhelmingly positive feedback
  - fun to write
  
  what were the risks for implementing Kotlin?
  - cost of learning new language : not so much
  - After all, not so different from Java
  - much better to adopt new language as bottom-up / not top-down 

----------------------------------------------------------

### 2nd Session: Application utilizing Web asset 
(web資産を活かしたアプリソフト)

yahoo! Japan の特徴
- WEBのみのサービスが多い
- mobile とwebの繊維が多い

-　webでは簡単にできたサービス連携がmobileでは難しかった。

- どんな改作取り組み？

1. one-tap login
Yahoo! Japan IDでいろんなサービスの利用が可能
- OAuth 2.0を利用。
- アプリを利用する際の問題: アプリごとのログインが必要
- 認証データをKeychainへ保存→アプリ間の認証情報共有が簡単になった。

2. Deferred Deep Linking
- WebからアクセスされたrouteはDeep linkingを利用して、アプリで開くか、Webページで開くか判断。
- redirect serverで、エントリーpointをmapping.
3. WKWebView
- increased level of security - no longer able to use Cookie.
- doing something-----


-------------------------------------------------------------

### 3rd Session: How PaaS is applied in Yahoo Japan
Yahoo Japanを支える開発基盤PaaS

- YahooがつかっているPaas, CICDについて
- なぜPaaSか

1. CloudFoundry
OSS PaaS
- 複数のIaaSやVirtual environementを利用できる。
- 拡張性が高い

2. Concourse
OSS CI/CD Platform
- pipeline-based. b
- Using Web-UI
- yaml + Docker. easy to reproduce/ expand
- go well with CloudFoundry

- なぜPaaSか？  
scalability , elasticity.  
focusing on core business (logic)
runtime -> unify -> buildpack 

- Future of developing PaaS...

2016 - beta service
2017 - stable release
2018 - more on!

so..what about infrastructure??

PaaS -> AWS iwthout paying Amazon price for using their infra??

- Complexity and autonomy
- more about cultural challenges

Why cloud native? what's cloud native?

- early and continous delivery!

impacting of delivering automation -> not only higher efficiency but also difference in how to do business.


So...why is it so difficult?

- "no plan survives the first contact with the enemy."

~ simple problem - the answer(recipe) is given.

~ complicated problem  - there are bunch of answers, but if you follow all the recipe, then all things are well.

~ complex problem - like raising a child. There's no recipe, but if you learn some rules and follow them, 

Complex problems are non-linear. Complex system happens when you put together tech and human.

It's like caterpillar turning into butterfly. 
You have to change the whole structure...can't just add wings to caterpillar and have it called a butterfly.


In successful organization, there's semi-autonomous teams
different from traditional hierarchy.

This model can't survive the rapid transformation.

- Everyone on the team, understands the "why". Shared understanding.

- The decision should not be 'perfect', but good enough.
- The good-enough decision fast is much better than perfect decision eventually. 

- Cross-functional and balanced- 
- a team full of developers is not a team.

A team functions when there's a lot of communication going on within team. 

A high performance team needs to be in the same room.

Individual mindset shift: go experimental.

- Expect failure! (80%)
- everything you do within organization is experiment
- can even be right even if your hypothesis was wrong.
- __Retrospectives are where the learning happens__  
you only learn when you are at the end of the project, not during. All the experiment is wasted, unless you stop and reflect on the learning process.

! Feature Flags : experiment on
! Blue/Green deploys : limiting the scope of the experiment.

Can apply this mind when you organize your team.


Due to amazingly fast speed of technology transformation, you won't ever know how to do your job. 

__REFLECT!__

- Listen & communicate is a skill just like writing code.

You have to accept that good enough is 'good enough'. Nothing is going to be perfect. There is no time to go back and fix things!

The most important thing is that, the work needs to be done! 

Systems are complex. -> there's no recipe!

- If you feel safe to be wrong in your work environment, then it's a good environment! 


At the beginning of your career, there's high correlation of what you are good at and how well you are doing.
As the career progresses, there's almost no correlation.

It's all practice. 

https://www.mobs-lab.org 