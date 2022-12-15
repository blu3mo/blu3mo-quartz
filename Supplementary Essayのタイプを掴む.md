---
title: Supplementary Essayのタイプを掴む
---

* 大雑把に分けて、どういうpromptの[essay](Essay.md)があるのかを把握したい

* ちゃんと書き始たらタイプが分かってきたので書いてみる

* 以下のEssayがそれぞれ250w程度で書けていれば、後は合うように調整するだけで7割くらいのSuppはカバーできると思う
  
  ````
    - 例:
        - > We know you lead a busy life, full of activities, many of which are required of you. Tell us about something you do simply for the pleasure of it.  [[MIT出願]]
        - > Whether big or small, mundane or spectacular, tell us about something that brings you joy. [[Brown出願]]
    - <img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>の場合: [[Essay 世界の霧案]]
  
    - これは二パターンくらいあったほうが良さそう
    - <img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>の場合: [[Essay 未踏案]], [[Essay 歴史EE案]]
    - 例:
        - > The Stanford community is deeply curious and driven to learn in and out of the classroom. Reflect on an idea or experience that makes you genuinely excited about learning. [[Stanford出願]]
        - >  We are inspired by students who are flexible in their approach to learning, who are comfortable with experimentation, and who are willing to take intellectual risks that move them out of their comfort zone. Reflect on a time that you were intellectually challenged, inspired, or took an intellectual risk—inside or outside of the classroom. How has that experience shaped you, and what questions still linger? [[Swarthmore出願]]
  
    - <img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>場合: [[Essay Communityから受けた影響案]]
    - 例:
        - > Tell us about an aspect of your own perspective, viewpoint or lived experience that is important to you, and describe how it has shaped the way you would learn from and contribute to Columbia's diverse and collaborative community. [[Columbia出願]]
        - > Describe the world you come from; for example, your family, clubs, school, community, city, or town. How has that world shaped your dreams and aspirations? [[MIT出願]]
  
    - <img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>の場合: [[Essay CCC案]]
    - 例:
        - > Describe an example of your leadership experience in which you have positively influenced others, helped resolve disputes, or contributed to group efforts over time. [[UC出願]]
    - この話を、collaborationとかleadershipのpromptにも使いまわせると良さそう
        - > Tell us about how you have collaborated with and worked together within a small group of your peers on some task or endeavor in the past, or about how you imagine you will work with your Caltech peers in the future. [[Caltech出願]]
  ````

* 注意点
  
  * そのまま使い回すのはだいたいむずいので、ちゃんとPromptをしっかり読んで調整するべき
  * これらはCommon App 650w Essayとは別の内容
* もしUC/MITに出願する予定があるなら、それらの大学のEssayをまず書くと良さそう
  
  * UCもMITも使い回しがしやすいEssay Promptが多いので

---

以下は2021/08ごろ書いたやつ

* 分けるの難しいなとは思った
  
  * 例えば
    * 大学の特徴とかを絡めた上で課外活動とか思想とか聞くprompt（志望理由も間接的に聞いている）
    * 過去の課外活動等の具体的経験をもとに、思想とか興味の深掘り方とかを聞いてくるやつ
  * まあ一番近いジャンルに振り分けている
    * これを知るのがメインだろうなーと予想して分けている
* 使った大学
  
  * [Stanford](Stanford.md), *MIT*, *Columbia*, [Harvey Mudd](Harvey%20Mudd.md), [Swarthmore](Swarthmore.md), [Harvard](Harvard.md), *UBC*, [Brown](Brown.md)
* 課外活動や経験おしえろ系
  
  * シンプルに活動を聞くのと、経験と何かの繋がりを聞くやつがあるけど、まあどっちも本質的には一緒な気がする
    * シンプルに聞いてるやつでも、自分の何かと繋がりを持たせるのは必要だから
  * 「did simply for pleasure」とか「contributed to community」とかspecificに聞いてくるのもある
  * 
     > 
     > How did you spend your last two summers?
  
  * 
     > 
     > Briefly elaborate on one of your extracurricular activities, a job you hold, or responsibilities you have for your family.
  
  * 
     > 
     > The Stanford community is deeply curious and driven to learn in and out of the classroom. Reflect on an idea or experience that makes you genuinely excited about learning.
  
  * 
     > 
     > Please tell us what from your current and past experiences (either academic or personal) attracts you specifically to the areas of study that you noted in the application.
  
  * 
     > 
     > We know you lead a busy life, full of activities, many of which are required of you. Tell us about something you do simply for the pleasure of it.
  
  * 
     > 
     > At MIT, we bring people together to better the lives of others. MIT students work to improve their communities in different ways, from tackling the world’s biggest challenges to being a good friend. Describe one way in which you have contributed to your community, whether in your family, the classroom, your neighborhood, etc.
  
  * 
     > 
     > Tell us about the most significant challenge you’ve faced or something important that didn’t go according to plan. How did you manage the situation?
  
  * 
     > 
     > We are inspired by students who are flexible in their approach to learning, who are comfortable with experimentation, and who are willing to take intellectual risks that move them out of their comfort zone. Reflect on a time that you were intellectually challenged, inspired, or took an intellectual risk—inside or outside of the classroom. How has that experience shaped you, and what questions still linger?
  
  * 
     > 
     > Give us an example of how the pandemic has changed your involvement in the community or group most important to you. What have you learned from this experience?
  
  * 
     > 
     > Explain how you responded to a problem and/or an unfamiliar situation. What did you do, what was the outcome, and what did you learn from the experience?
  
  * 
     > 
     > Brown’s culture fosters a community in which students challenge the ideas of others and have their ideas challenged in return, promoting a deeper and clearer understanding of the complex issues confronting society. This active engagement in dialogue is as present outside the classroom as it is in academic spaces. Tell us about a time you were challenged by a perspective that differed from your own. How did you respond?

* 環境を教えろ系
  
  * 
     > 
     > Describe the world you come from; for example, your family, clubs, school, community, city, or town. How has that world shaped your dreams and aspirations?
  
  * 
     > 
     > Swarthmore students’ worldviews are often forged by their prior experiences and exposure to ideas and values. Our students are often mentored, supported, and developed by their immediate context—in their neighborhoods, communities of faith, families, and classrooms. Reflect on what elements of your home, school, or community have shaped you or positively impacted you. How have you grown or changed because of the influence of your community?

* 思想/考え方/興味を教えろ系
  
  * 面白いと思うこととか、価値を感じることとか、学び方とか、興味分野を聞いてくるやつ
  * これが個人的には一番書きやすい&書いてて楽しそうな気がする<img src='https://scrapbox.io/api/pages/blu3mo-public/blu3mo/icon' alt='blu3mo.icon' height="19.5"/>

    * いつもScrapboxでやってることなのかもw
  * 直接系
    * 
       > 
       > Tell us about something that is meaningful to you and why.
    
    * 
       > 
       > Pick what field of study at MIT appeals to you the most right now, and tell us more about why this field of study appeals to you.
    
    * 
       > 
       > What is important to you? And why?
    
    * 
       > 
       > Brown’s Open Curriculum allows students to explore broadly while also diving deeply into their academic pursuits. Tell us about any academic interests that excite you, and how you might use the Open Curriculum to pursue them while also embracing topics with which you are unfamiliar.
    
    * 
       > 
       > A hallmark of the Columbia experience is being able to learn and live in a community with a wide range of perspectives. How do you or would you learn from and contribute to diverse, collaborative communities?
  
  * 間接系
    * 
       > 
       > What is the most significant challenge that society faces today?
    
    * 
       > 
       > What historical moment or event do you wish you could have witnessed?
    
    * 
       > 
       > List the titles of the required readings from academic courses that you enjoyed most during secondary/high school.
    
    * 
       > 
       > List the titles of the books, essays, poetry, short stories or plays you read outside of academic courses that you enjoyed most during secondary/high school.
    
    * 
       > 
       > We’re interested in learning about some of the ways that you explore your interests. List some resources and outlets that you enjoy, including but not limited to websites, publications, journals, podcasts, social media accounts, lectures, museums, movies, music, or other content with which you regularly engage.
    
    * 
       > 
       > Brown students care deeply about their work and the world around them. Students find contentment, satisfaction, and meaning in daily interactions and major discoveries. Whether big or small, mundane or spectacular, tell us about something that brings you joy.

* 志望理由教えろ系
  
  * 
     > 
     > Name one thing you are looking forward to experiencing at Stanford.
  
  * 
     > 
     > Why are you interested in attending Columbia University? We encourage you to consider the aspect(s) that you find unique and compelling about Columbia.
  
  * 
     > 
     > What influenced you to apply to Harvey Mudd College? What about the HMC curriculum and community appeals to you?
  
  * 
     > 
     > Many students choose HMC because they don’t want to give up their interests in the Humanities, Social Sciences and the Arts – or HSA as we call it at HMC. Briefly (in 100 words or less) describe what you’d like to learn about in your dream HSA class.
  
  * 
     > 
     > Why are you interested in applying to and attending Swarthmore?

* 変化球系
  
  * 
     > 
     > Virtually all of Stanford's undergraduates live on campus. Write a note to your future roommate that reveals something about you or that will help your roommate—and us—get to know you better.
  
  * 
     > 
     > Tell us about who you are. How would your family, friends, and/or members of your community describe you? If possible, please include something about yourself that you are most proud of and why.
