# "Three plus Four" Use Case

This is the first use case that will actually use a user interface, and not only a visualization of the communication model.

You start with a blank portal that lets you send and receive messages.
You are given the task: add 3 and 4.

The first thing you need to do is find out that there are numbers and what their addresses are.
You then need to find out what messages numbers understand and which one is for adding two numbers.
And as a last step, you ask 3 to reply with the sum of itself and 4.

The interface is mostly a message editor. You should never have to build a message from scratch but always edit messages you receive.
You can send messages and receive replies for each message, which you can edit and send again.
A message "who is here?" to start with is given. The starting point is always to find a Node that can do the thing you want to do.

The use case is basically a conversation:
	
	Who is here?
	-> "numbers" is here
	
	What does "number" understand?
	-> e.g. "What do you contain?"
	
	numbers: What do you contain?
	-> Here are 100 inhabitants of mine:
		0, 1, 2, 3, 4, ...
	
	numbers/3: What do you understand?
	-> e.g. "What is the sum of you and numbers/7"
	
	numbers/3: What is the sum of you and numbers/4?
	-> numbers/7
	

In Messages:

	< (from: me, please: showYourself)
	
	> (to: me, please: (askMe: (from: me, to: numbers, please: sendYourMessages)))
	
	< (from: me, to: numbers, please: sendYourMessages)
	
	> (to: me, please: (askMe: (from: me, to: numbers, please: sendYourParts)))
	
	< (from: me, to: numbers, please: sendYourParts)
	
	> (to: me, please: (knowMyParts: (1, 2, 3, 4, 5, 6, 7, 8, 9, 10)))

	< (from: me, to: numbers.3, please: sendYourMessages)
	
	> (to: me, please: (askMe: (from: me, to: numbers.3, please: (add: numbers.7))))

	< (from: me, to: numbers.3, please: (add: numbers.4))
	
	> (to: me, please: (knowTheSum: 7))
