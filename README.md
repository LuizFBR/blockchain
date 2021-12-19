# Blockchain

A decentralized network that allows its users to make transactions to each other without the involvement of third party.

User perspective:

> As an user, I would like to make safe transactions to anyone without the involvement of a third party, empowering myself and other peers like me to make 
> transactions, e.g like transactions, anytime without any reliance on others or bureaucracy.

## Software Engineering Planning(Work in progress)

A solution to this problem as discussed in [this paper](https://bitcoin.org/bitcoin.pdf) is a peer to peer network, where every node in the network carries a linked list of honest transactions done so far. The last transaction in this list carries the latest honest transaction performed on the network so far and each node can add a new transaction to the end of the list.

I'll organize this with epics and their multiple stories.

## Epics

- As a user I would like to be empowered such that my actons can be carried instantly and without any reliance of a third party, in a manner that is still safe, secure and reliable.
- As a user I would like that any transactions that are made with my name are legit, performed only by my account, which must be secure at all times.

> As a user I would like to be empowered such that my actions can be carried instantly and without any reliance of a third party, in a manner that is still safe, secure and reliable.

Stories:
- As a user, I would like to be a part of none or many Peer to Peer network(s), where I can perform my actions and transmit them to the rest of the network which I have performed an action on.
- I must also listen to changes done by others in any network I'm in.
   - The changes I listen to will only be applied to my node if they're deemed safe and secure.
   - I'll have a list of changes identifiable per users, which i must periodicaly check in order to reject or accept them.
- I would also like that there's no central node in the network, therefore I must have a maximum of k < n - 1 neighbouring nodes, where n is the number of nodes in the network.
- I would like to have the freedom to opt in and out of any network at anytime. I'll have a unique opt in or opt out key which must be shared with no one, under any circumstances.

> As a user I would like that any transactions that are made with my name are legit, performed only by my account, which must be secure at all times.

Stories:
- As an honest user I would like to make safe and secure transactions within any decentralized network. 
  - Creating a new transaction will require computational work to find a sequence of 256 bits that start with k 0s.
  - If I don't have enough currency to perform the transaction, then that transaction won't be accepted.
- As an honest user, I'd like to have a list of all the honest transactions done so far in the network and I'll always be listening to changes to this list in order to accept or reject them.
  - This list of honest transactions will take the form of a linked list of transactions, where the end of the list is the last honest transaction.
  - While listening to other nodes in the network, if there are any divergences in my list of transactions to the list of transactions I'm listenning to, then I will reject those changes. I'll always select the longest list of transactions being broadcasted and I'll only accept its changes if it has over k transactions more than mine list of transactions. Therefore, the chain of transactions with most work put in it always gets selected as being the honest one.

## References and Acknowledgements

Big thanks to 3B1B for its great guide to bitcoin: https://www.youtube.com/watch?v=bBC-nXj3Ng4&ab_channel=3Blue1Brown
