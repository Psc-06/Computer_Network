Most Important ones are CSMA/Cd and token ring passing 
## CSMA/CD 
used primarily in wired ethernet works
we will understand this with an example 
Imagine a group of people at a dinner table all wanting to talk
- Carrier Sense (Listen before talking) : Before anyone speaks , they first listen to see if anyone else is already talking if the "air" (the network medium) is busy the wait
- Multiple Access (Anyone can talk) : Once the air is clear, anyone can start talking There's no designated speaker multiple people have the access
- Collision Detection (What if Two start at once ) : What happens if two People listen, finds the air clear and then start talking at exactly the same time Their voice will overlap creating a collision
	- in CSMA/CD the speakers detect this collision they hear the other person's voice conflicting with their own
	- Jam Signal : when a collision is detected both parties immediately stop talking and emit a "jam signal" to ensure everyone else on the network knows a collision occurred
	- Backoff Algorithm : Both parties then wait for a random amount of time (called a backoff period) before trying to talk again by choosing a random time the chances of them colliding again are reduced
How it works in networks
- A device wants to send data
- It listen to the network cable to see if it's free
- If free, it starts transmitting data
- While transmitting, it continues to listen(collision detection)
- if it detects a collision it stops the transmission sends a jam signal and then waits a random amount of time before attempting to retransmit the data
## Token Passing
Used in older network technologies like Token Ring (IEEE 802.5), Token Bus (IEEE 802.4) And FDDI
We will understand this with an example
Imagine the same dinner party but this time there's a single "speaking stick" (the token) being passed around the table
- Exclusive access : only the person holding the speaking stick is allowed to talk. Everyone else must remain silent
- Passing the stick : When a person is finished talking the pass the speaking stick to the next person in a predefined order
- Transmission : if you have something to say you wait until you receive speaking stick. you  then fill the stick with your message, talk and then pass the empty stick to the next person
How it works in the network
- A special small data packet called "token" continuously circulates around the network 
- When a device wants to transmit data it waits for the token to arrive
- it grabs the token effectively removing it from circulation for a brief period
- The device then transmits its data frame onto the network
- After the data has been sent and typically acknowledged by the receiver the transmitting device release the token back onto the network for the next device to use 
- If a device receives the token but has no data to send, it simply passes the token to the next device