# Nodes
"A node is a computer that runs the Bitcoin software. Your node is your own version of the Bitcoin blockchain and ruleset. Think of it as your own gateway to the Bitcoin ecosystem. It broadcasts transactions, verifies the bitcoin you receive are legitimate and maintains your privacy by allowing you to participate without reliance on anyone. When you connect your wallet to your node, you are not trusting anyone else to verify your transactions.
A node helps to protect you from bad actors and it also keeps the network decentralised. If you do not have your own, you are trusting in someone else’s node to tell you how much bitcoin you have and to broadcast/receive your transactions for you. Read a more in-depth look at the ‘why’ of Bitcoin nodes [here](https://armantheparman.com/why-should-you-run-your-own-bitcoin-node/).
**_Your node, your rules._**"

## Implementations
There are many implementation from `plug&play` to customizing the services that you want to install in your node (hardware). These are the main ones:
- [Umbrel](https://getumbrel.com/): A personal node for everyone
- [Raspiblitz](https://raspiblitz.org/): DIY Bitcoin & Lightning Node on a RaspberryPi
- [RoninDojo](https://ronindojo.io/): They help people to have a feature rich bitcoin experience, maintain privacy, and thrive as a sovereign individual. [[roninDojo |extra info]]
- [Raspibolt](https://raspibolt.org/): Build your own do-everything-yourself Bitcoin full node that will make you a sovereign peer in the Bitcoin and Lightning network
If you want more implementations, check in [bushido guide nodes](https://bushido.guide/explorer/bitcoin/nodes) or in their [github](https://bushido.guide/explorer/bitcoin/github/node)

## SSH
Sometimes, we forget the node IP in our local network to reach the node through ssh (`ssh username@node_ip_address`, that command is for linux and MacOS machines). One useful tool could be [angryIP](https://angryip.org/) which  scans all the devices connected to the local network. Once you scan the local network, you need to try with each IP the `ssh` command that we write above to access the node. _How you will know that you get the access to the node?_ Usually, when you reach the node, it will ask you the password.

#### private key
When we have set the authentication type in ssh over public-private key pair (check below sources), it is easier to access to the node. We do not need to type the password but we need to create the key pairs and add the public key in the remote machine, in our case, the node.
#### Note
If we have saved the private key (usually in `~/.ssh`) that grants access to the node, we can copy that private key in other machine to access easily. 
__ATTENTION:__ That private key has to be in a secure environment, if the key will be leak, everyone could access to the node. In that case, create a new key pairs and forbid the old public key the access to the node
```
// Copy the private key in the ssh folder
cp folder_of_our_private_key/name_of_the_key ~/.ssh/
```

## Sources
- [Bitcoiner Guide](https://bitcoiner.guide/node/)
- [Angry IP scanner documentation](https://angryip.org/documentation/)
- [How to use Angryp IP scanner - Beginners Guide](https://techwiser.com/use-angry-ip-scanner/)
- [What is SSH and How does it work](https://geekflare.com/understanding-ssh/)
- [Set up SSH keys](https://www.digitalocean.com/community/tutorials/how-to-set-up-ssh-keys-2)
