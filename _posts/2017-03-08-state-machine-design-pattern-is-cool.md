---
layout: post
title: State Machine Design Pattern
categories: [misc]
tags: [design patterns]
fullview: true
---

The state machine design pattern is beautifully described by Robert Nystrom with references to game logic in http://gameprogrammingpatterns.com/state.html and I would highly recommend reading through his site, there are many more patterns that are discussed in great detail.

As he mentions during the end of the article, "...they are most know for being used in AI, but they are also common implementations of user input handling, navigating menus...". In terms of the programming I have done for my projects so far, the main use I have had for the State Machine design pattern is UI navigation, it is so simple and easy to setup a flow of game logic with. All you have to do is inherit from your base State class and extend to the functionality that you want!

In terms of setting up the base state you can have something like:

	```
	class UIState
	{
		public:
			virtual ~UIState(){}
			virtual std::unique_ptr<UIState> HandleTransitions() = 0;
			virtual void OnEnter() = 0;
			virtual void OnExit() = 0;
			virtual void Render() = 0;
			virtual void Update(float& dt) = 0;
	};
    ```
	
Then for your inheriting states, you can just override the methods:

	```
	class TitleUIState : public UIState
	{
		public:
			TitleUIState(const UIState& current_state);
			~TitleUIState();
			std::unique_ptr<UIState> HandleTransitions() override;
			void OnEnter() override;
			void OnExit() override;
			void Render() override;
			void Update(float& dt) override;
	};
    ```
	
It's simple and powerful once you get to grips with it, and if you use it for the right situation. I have also used it for a turn based combat system (a project currently under development). It seems that this design pattern is very good for any sort of logic that has a set flow, if you know that one state should lead to another - this pattern could be a good shout!