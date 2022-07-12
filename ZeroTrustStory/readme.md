# A Zero Trust Fable

## Act I

- We meet Zane Tacket, who is getting up to go to work and isn't really feeling it.
- His company has recently come under fire due to a security flaw.
- He and his fellow software developers are half-working, half-refreshing the news to find out what is going on.
- Ultimately, this leads to his company failing: they lost the trust of their customers, and so there is a lay off.
- Zane is one of the people let go.  He feels the injustice of it - it wasn't his fault, it was security's fault for not doing their job!  Or so he thinks.
- We pick up six months later.  Zane has a new job, and has recently been promoted to a principle software architect, leading the charge for a product that he feels is his baby.
- There is some shake ups at the new place, though.
- First, there is a new principle security architect, someone that Zane hasn't met yet but has gotten a bad reputation in just three weeks.
- Second, and somewhat related, there is a security audit set to occur.
- The audit is being very by the books, and lead by two consultants - Will (short for Willy) and Bill (short for William), two indistinguishable suit-shaped auditors who are running things by a check list.
- As part of this, Zane attends many meetings for his application related to the security review.
- He gets to meet the new principle security architect, Alan Franks, who isn't very impressive; he seems half asleep and not interested in his own departments audit.
- The audit is boring as well; a lot of security says that Zane's team doesn't need to worry about stuff.  It makes Zan uncomfortable; so much of the security of his project is hidden from him, and he's being told to just trust them.
- Zane takes the check list, and gets to thinking about how trusting security got him in trouble before.  Alan seems like a goof.  Zane is afraid of the same thing happening with this app as what happened at his last place of employment.
- So he gets to looking at the list, and after a night of thinking, decides he is going to make it so that his application meets the requirements itself, regardless of what other teams do.

## Act II

### Use Least Privileges

- Zane reads the list and finds something pretty easy.  It says that **Applications should only communicate to each other through front end security appliances.**  So he decides to create a configuration on his application to enforce that.  
- His application has a Web, Business, and Data tier, and he creates configurations so that none of these tiers will take traffic anywhere but from the security appliance.
- He makes the change, and submits a pull request, and feels good.
- A week later, after his change and others are rolled up, another team's application breaks; they say it has to be due to an issue with his application.
- They find out that their application was communicating directly to the data tier of Zane's application.
- They roll back the change.
- There gets to be a whole war room situation to discuss.
- The other app architect goes off on Zane for making the change, not testing and communicating, and a whole bunch of other stuff.
- "What do you have to say about this?" goes the VP of Product to Alan.
- "Zane did a great job," is the reply.  Which makes people angry.
- Alan gets control of the room by standing up and beginning to pace.  He lays out the facts.
- "There is no documentation about this connection directly to the data tier."
- "It breaks the established security practices."
- "It's clear that the Zane's team wasn't aware that this was a requirement."
- "In addition, in both of the auditing checklists, it was marked that there was no violation for this requirement, for how applications communicate."
- "No *human being* knew that this connection was happening, or at least didn't bring it up.  We spend a lot of time setting up the firewall layer appropriately, and then it was just bypassed.  So good job to Zane for finding it."
- Alan reveals to the group that Zane was practicing one of the principles of Zero Trust Architecture: to use least privileged access, always.
- Alan stresses that no one is the bad guy here; "Our real adversary is ...  The Adversary..." he says in a spooky/creepy way.
- Alan talks with Zane after the meeting, to get an understanding of what happened.

### Verify Explicitly

- There is an app that needs user to access, but VPN access kills performance.
- A discussion about MFA
- Possible notes about changing the guidelines.
