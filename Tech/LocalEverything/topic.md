Problem:
Instead of writing language specific Smart Contract abstractions (Arc.js, Colony.js, etc) 

Solution:


Story:
In talks with Bo, he asked (paraphrasing):
"Are you going to heavily use Arc.js or instead use graph protocol (GraphQL) to read blockchain data? We have a server that stores a bunch of DAOstack's data already, you could plug your client into that."

This thought of not using a JS wrapper around contract ABIs, and instead using a library of GraphQL queries is a really beautiful thing.

This means we can run in any language, and gives us a path to NATIVE!!! Native is beautiful because we're no longer constrained by the browser, and can do very complex computation locally. For example think of having full access to the GPU for an interesting visual or executing a neural net...

This would give way to the next level of applications that need trusted data. Here are some potential use cases:
- Collaboration Apps at an all new scale. (Governance, Project Management, Communications, Documents)
- Videogames that utilize blockchain backed state data. (city planning, economics, event planning)
- Automated AI banking on your phone. We all are the bank. (investing, predicting, lending, security, etc)

Anything cool that can only happen natively is now possible using blockchain data.

Counter Arguments:
1. "Your phone isn't powerful enough to do the things you mentioned, this is why we've moved to the cloud."
I would argue the reason we've moved to the cloud is more so due to the amount of data, rather than our edge device compute capabilities. The edge is where the compute is. The real issue is communicating trusted state data to devices.

2. "Even if you did all compute locally, the sheer amount of database read/writes surely couldn't be achieved using blockchain and IPFS..."
The way I see the solution to this problem is as follows. Imagine you have 5 read/writes to a peice of data within a minute. The naive way would be to store the content (on ipfs) and hash (on chain) 5 times. The better way would be to take advantage of "feeds", currently only implemented in Swarm.

A single feed's content can be updated as many times as you want, and the latest version is always served at the same address. You can also traverse the history and see older versions. With feeds, the chain is only used 1 time initially, so your 5 updates are "free". For more information on the caching mechanism to ensure data retention, view this document [here](../ScalableContentPersistence/story.md).

3. "You would be heavily dependent on a full node for the data, then the network becomes the bottleneck..."
* Running a full node locally is preffered, but most likely only possible for laptops/desktops. When phones have 1TB NVMe hard drives, then phones are an option.
* Caching lots of local data will still be necessary, but can be minimzed to:
  * The contracts you care about.
  * High level queryable data only (bloom filters). The raw block/transacion data can be pulled from elsewhere.
