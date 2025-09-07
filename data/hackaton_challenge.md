## Follow the Money: Detecting P2P Fraud

### Overview (question)
Can you uncover hidden fraud patterns in a sea of peer-to-peer transactions? Using an anonymized dataset, your mission is to build a fraud-detection model that identifies suspicious behavior, unusual connections, and evolving fraud rings. How will you leverage AI to outsmart criminals and help Viseca protect the savings of your family and friends?

### Detailed problem
Peer-to-peer (P2P) payment apps have changed the way people handle money, making it incredibly simple to split a bill, pay a friend, or buy from a small business. That convenience hides risks: behind millions of legitimate transactions, sophisticated fraudsters exploit the system for financial gain.

P2P platforms form a social network of financial interactions. Every user is a node,every transaction an edge, mapping an intricate web of connections. Most are genuine relationships, some are engineered to deceive.

In this challenge, you will join the frontline with Viseca, one of the leading Swiss payment services provider, committed to making digital finance safer for everyone. Your task is to look beyond simple rules and metrics. Fraud detection is an adversarial game: a cat-and-mouse chase against an ever-evolving landscape of novel, increasingly sophisticated schemes.

To get you started, consider these common schemes:
- **Money Mule Networks:** to launder stolen money, criminals recruit or trick people into receiving illicit funds, quickly transferred other accounts. In a network view, this might appears as "gathering" pattern (many accounts send to one) followed by a "scattering" pattern (one account sends to many), often within hours.
- **Account Takeover:** after phishing or credential theft, a legitimate account suddenly behaves differently, for instance performing unusually large, late-night transfers to brand new contacts or changing personal details.

A model that overfits known fraud patterns will soon fail. It must be intelligent and adaptable, detecting new, unseen fraud typologies by recognising abnormal behaviour.

### Detailed objectives
Your mission is to build a robust, fraud detection system.

- **Model the System:** represent relationships and behaviours within the payment ecosystem. How will you model connections? Which features will you engineer from raw data (amounts, timestamps, historical card usage, ...) to reveal hidden patterns?

- **Identify Suspicious Activity:** assign a risk score to users or transactions to separate legitimate behaviour from anomalies that signal crimes.

- **Deliver a Future-Proof Solution:** The core challenge is generalization. Show how your approach approach can detect the ever-evolving tactics of fraudsters.

- **Do you want to go further? Explain**
- Can explain your model's choices? Why was a certain user or transaction flagged as high-risk?

### Why hack?
Every fraudulent transaction has a real victim: someone's rent, a small business's payroll, grandparent's savings. That victim can be someone near you: fraud methods have become increasingly sophisticated, and with the advent of advanced GenAI, anyone can fall prey.

Are you ready to wear your white hat to outsmart the criminals? This is your chance to use your skills for good, helping Viseca protecting millions of people.

### Support for hackers (data, api, people)
- **Data:** synthetic dataset mirroring a real P2P network, provided as CSV files. It includes P2P transactions, plus contextual information, such as user data and historical card transactions.
- **Mentorship:** Viseca's expert will provide guidance and support, answering your questions.

### Technical preferences
The problem is well suited for graph-based methodologies. However, you have complete theoretical and technical freedom. Your project will be judged on effectiveness, innovation and robustness, not on your tech stack.
