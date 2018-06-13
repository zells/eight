# User Case I: Basic Communication

So here is my first use case for prototype eight.

First, I'll describe how exactly the use case is executed and then what capabailities the system needs to have to support it.


## Steps

1. Setup: 3 expanded Scopes pointed to 3 Zells
	- a Communicator named "Comm"
	- a Text named "Text" and empty string as value
	- an Inspector pointing at an empty Proto Zell named "Empty"

2. Build the first Message
	1. Rename "Empty" to "First Message"
	2. Put "Text" into "Empty"
		1. Open Zell Menu of "Text"
		2. Choose "grab"
		3. Drop "Text" in "First Message"
	3. Rename "Text" to "receiver"
	4. Change value of "receiver" to "Bob"
	5. Clone "receiver" to "content"
		1. Open Zell Menu of "receiver"
		2. Choose "clone"
		4. Dropped cloned Zell in "First Message"
		5. Rename cloned "receiver" to "content"
		6. Change value of "content" to "Hello, World!"
	
3. Create receiver
	1. Clone "Comm" to "Bob"	

4. Send message	
	1. Put "First Message" into outbox of "Communicator"

	
## Capabilities

- show empty Inspector Scope
- show name of Zell under Inspector
- change name of Zell under Inspector
- update changed name of Zell under Inspector
- show Text Scope without value
- grab Zell under Scope
- put grabbed Zell into Zell under Inspector
- show children of Proto Zell under Inspector
- update added children of Proto Zell
- change value of Text Zell
- update changed value of Text Zell
- clone Zell
- send message with sender by dropping in outbox of Communicator Scope
- show sent message in outbox of Communicator Scope
- receive message with matching receiver by Communicator Zell
- show received sessages in inbox of Communicator Scope