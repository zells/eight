This is the second demonstration of the zells prototype number eight. It shows the same use case as the last demonstration, but with a different model.

The use case is to display a simple text message - basically a "Hello World". So it only contains the very basic elements and mechanics.

The goal of zells is to become a full-fledged  environment for authoring and exeucting software. But it still has a long way to go.

All there is so far, is the basic element, called "Zell". Let's create one.

	zell := Zell new

All a Zell can do is receive byte streams, called "Signals".

So let's send a Signal to our Zell. In this case a string.

	zell receive: #foo

Note that this action is asynchronous and there is no return value.

In order to display the received Signal, we can point something called a "Scope" at the Zell that prints received Signals to the Transcript.

	scope := TranscriptScope pointingAt: zell
	
Now everything we send to the Zell is printed on the Transcript.

And that's already the whole model. There are Zells which can asynchronously receive Signals. And there are Scopes which can be used to interact with Zells.

So let's move away from Smalltalk and get graphical.

	scope openInWorld. scope target openInWorld.
	
As you can see, the TranscriptScope not only prints received Signals on the Transcript, but also in it's own window. So we don't need the Transcript anymore.

We can take this a step further and use a Scope that displays received Signals as Zells.

	ListenerScope new openInHand
	
Once we point it at the Zell, every Signal it receives is displayed as a Zell itself. 

These are TextZells which we can send again to the Zell using an InboxScope.

	InboxScope new openInHand
	
Once we pointed it at the Zell, we can send it TextZells by dropping them in the Scope and a copy of it appears in the ListenerScope.

We can also change the text value using a TextScope.

	TextScope new openInHand

This way we can send and display "Hello".

That's it. That's how you send Signals to Zells and display them. Again, this is only a very basic use case. Stay tuned for more.
