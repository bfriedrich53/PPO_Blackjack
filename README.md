In this project, I use the Reinforcement Learning Algorithm of Proximal Policy Optimization(PPO) to determine the optimal policy in the game of blackjack. This project was inspired by the book "Reinforcement Learning: An Introduction" (Sutton and Barto). In the book, they use an alternative algorithm to create their agent, but I was inspired to use PPO for 2 reasons: 

1. I wanted to implement an algorithm by hand to get a thorough understanding of the world of reinforcement learning, and I hadn't seen anyone use PPO on blackjack, so it it seemed like a fun way to solve this problem.

2. PPO seems to be the "state of the art" RL algorithm, and it seemed useful and fun to learn.

Blackjack works by being dealt 2 cards and playing against the dealer. You can either choose to add cards or stay with your hand, and get as close to 21 as possible. If you exceed 21, however, you lose. You also lose if the dealer has a bigger number than you. Yopu win by beating the deaeler, or if the dealer goes over the value fo 21. It is also possible to tie the dealer if you end up with the same value. In this blackjack environment, we consider three inputs:

1. The sum of our hand, which takes on the integer values between 12 and 21 (we will always hit when our hand is an 11 or lower, as we cannot lose on that hit so we might as well increase our hand)

2. The card we can see in the dealers hand, which can be any integer from 2 to 11.

3. Whether or not we have an ace that can be used as either an 11 or a 1, giving us more flexibility.

The agent will consider these 3 factors and determine whether it is optimal for us to "hit" and draw another card, or "stick" with our current hand. The agent uses gymnasium, an open source library created by OpenAI to instantiate the environment and synthetically generate training data and rewards. The agent will receive a 1 if they win the hand and a -1 if they do not, with a 0 if they tie the dealer. In practice, payout for a natural blackjack (being dealt a card valued 10 or an ace) is 1.5X, but this will be ignored, as we are focused on the decisions you make to optimally play blackjack, and a natural blackjack represents no decisions to be made.
