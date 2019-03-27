There is an inescapable engineering tradeoff between security and usability. While it is easy to make a system that is not very secure or usable it is impossible to make a system that gets top marks in both categories. 

This is simply because the more security a system requires, the more authentication evidence is required. A 4-digit PIN is easy to remember and easy to input, but also easy to guess so it provides just a few bits of [Bayesian evidence](https://en.wikipedia.org/wiki/Evidence_under_Bayes_theorem) that the user is in fact who they claim to be.

Kinds of evidence that can increase the system's authentication confidence include:
* decent password
* control of email
* 2FA and [multi-factor authentication](https://en.wikipedia.org/wiki/Multi-factor_authentication)
* login from known IP address

Obviously each layer of added security reduces usability because it requires more effort from the user or restricts the flexibility of the use cases.
 
![tradeoff](https://i.imgur.com/olq3xz7.png)

There is no "right" answer here, just a cost associated with a given preference represented by the shade of grey (lighter has lower costs, darker has higher costs, but black is unattainable no matter the cost).