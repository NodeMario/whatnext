# whatnext
> Warning WIP



###Usage
Define all question and answer in an array (nodes) in below format
#####question
```
{
	question1:{
		text: 'Are you human or super Hero', //the actual question
		selectedOption: '', //this will be updated on user input
		option: [answer1,answer2], //default options can be updated runtime.should be inside node array
	}
}
```

#####Answer
```
{ 
	answer1: {
		text: 'human'
	}
},
```


#####Ruleset
Define a rule set as an object. Order of expect ruleset answer follows the order of question.
Seperate the question with space. Add conditions to answers

```
'question1 question2': {                         //If question1 question two has answers
		'answer1 and answer4':{                      //answer1 AND anwer4 respectively
			question3: ['answer1','answer2','answer3']  //then next question should be question3 with options answer1,2,3
		},
		'answer1 and answer5':{
			question3: ['answer1','answer2','answer3']
		}
	},
```

#####API
######Intialize
```
	var whatnext = new WhatNext('test',nodes,ruleset,nodes[0]);
```

######get current question
```
	var currentQuestion = whatnext.getCurrentQuestion();
```

######setSelectedOption
```
	whatnext.setSelectedOption(currentQuestion,currentQuestion[currentQuestion.id].options[0]);
```

####Shortterm goals
Support predefined list

####Longterm goals
Multiple select questionS