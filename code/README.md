Problem:
Evaluation study using Natural LAnguage Processing to classify presence of suicide ideation
Does not rely on known risk factors to predict suicidal behavior
The prevalence of non-suicidal behaviors is significantly higher than completed suicide and may provide opportunity for understanding and growth where there otherwise has been 
The severity of suicidal ideation has been proposed by Beck et al. as an indicator of suicidal risk.
Beck, A. T., Kovacs, M., & Weissman, A. (1979). Assessment of suicidal intention: The Scale for Suicide Ideation. Journal of Consulting and Clinical Psychology, 47(2), 343–352. https://doi.org/10.1037/0022-006X.47.2.343
EHR Electronic Health Records (EHR)
construction of a depression "lexicon"
Automation of text screening for depression, proactive screening for suicidality

Heightened:

-Patient follow ups
-
***my_stop_words_remove*** = 
'after',
 'afterwards',
 'again',
 'against',
 'alone',
 'another',
 'anyone',
 'anything',
 'anywhere',
 'below',
 'beyond',
 'bottom',
 'cannot',
 'cant',
 'cry',
 'done',
 'down',
 'empty',
 'enough',
 'everyone',
 'everything',
 'everywhere',
 'give',
 'keep',
 'less',
 'me',
 'move',
 'must',
 'myself',
 'never',
 'nobody',
 'none',
 'nothing',
 'now',
 'nowhere',
 'off',
 'often',
 'out',
 'over',
 'please',
 'rather',
 'same',
 'serious',
 'she',
 'should',
 'someone',
 'still',
 'take',
 'thin',
 'together',
 'under',
 'well',
 'will',
 'within',
 'without'
                      
 ***my_stop_words*** = 'about', 'above', 'across', 'after', 'afterwards', 'again', 'against', 'all', 'almost', 'alone', 'along', 'already', 'also', 'although', 'always', 'am', 'among', 'amount', 'an', 'and', 'another', 'any', 'anyone', 'anything', 'anyway', 'anywhere', 'are', 'around', 'as', 'at', 'back', 'be', 'became', 'because', 'become', 'becomes', 'becoming', 'been', 'before', 'behind', 'being', 'below', 'besides', 'between', 'beyond', 'both', 'bottom', 'but', 'by', 'call', 'can', 'cannot', 'cant', 'co', 'could', 'couldnt', 'cry', 'describe', 'detail', 'do', 'done', 'down', 'due', 'during', 'each', 'either', 'else', 'empty', 'enough', 'etc', 'even', 'ever', 'every', 'everyone', 'everything', 'everywhere', 'except', 'few', 'fill', 'find', 'fire', 'first', 'five', 'for', 'former', 'found', 'four', 'from', 'front', 'full', 'further', 'get', 'give', 'go', 'had', 'has', 'have', 'he', 'her', 'here', 'herself', 'him', 'himself', 'his', 'how', 'however', 'if', 'in', 'interest', 'into', 'is', 'it', 'its', 'itself', 'keep', 'last', 'least', 'less', 'made', 'many', 'may', 'me', 'meanwhile', 'might', 'mine', 'more', 'most', 'mostly', 'move', 'much', 'must', 'my', 'myself', 'name', 'neither', 'never', 'next', 'no', 'nobody', 'none', 'nor', 'not', 'nothing', 'now', 'nowhere', 'of', 'off', 'often', 'on', 'once', 'one', 'only', 'onto', 'or', 'other', 'others', 'otherwise', 'our', 'ourselves', 'out', 'over', 'own', 'part', 'per', 'perhaps', 'please', 'put', 'rather', 're', 'same', 'see', 'seem', 'seemed', 'seems', 'serious', 'several', 'she', 'should', 'show', 'side', 'since', 'six', 'so', 'some', 'somehow', 'someone', 'something', 'sometime', 'sometimes', 'somewhere', 'still', 'such', 'system', 'take', 'ten', 'than', 'that', 'the', 'their', 'them', 'themselves', 'then', 'there', 'therefore', 'these', 'they', 'thin', 'third', 'this', 'those', 'though', 'three', 'through', 'throughout', 'thru', 'thus', 'to', 'together', 'too', 'top', 'towards', 'two', 'under', 'until', 'up', 'upon', 'us', 'very', 'via', 'was', 'we', 'well', 'were', 'what', 'whatever', 'when', 'whenever', 'where', 'whether', 'which', 'while', 'who', 'whoever', 'whole', 'whom', 'why', 'will', 'with', 'within', 'without', 'would', 'yet', 'you', 'your', 'yourself'