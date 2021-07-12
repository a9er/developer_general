# Basics of Networking  

Whether you connect a Mac laptop to your office network, stand up an AWS instance, or turn on an IoT device, it will need to talk through the internet. Networking, while completely invisible, is critical in that it allows communication between two disparate networked objects. 

These links should provide you with basic knowledge on how interconnected networks work.

## The Basics

[Internetworking](http://docwiki.cisco.com/wiki/Internetworking_Basics) is one of the oldest and most concise explanations of how networks work from the bottom up. It's quite big, and covers a huge swathe - but it's worth a read at the beginning of your journey.    
A quick video overview of [How Internet Works](https://www.youtube.com/watch?v=3QhU9jd03a0), for people who prefers visual material.  

[The OSI model](https://www.lifewire.com/layers-of-the-osi-model-illustrated-818017) is a networking framework to implement protocols in layers, where control is passed from one layer to the next. As you put things online, you will have to contend with issues that originate from the varying layers of networks - so remembering this is always handy.

[Classless Interdomain Routing](https://www.digitalocean.com/community/tutorials/understanding-ip-addresses-subnets-and-cidr-notation-for-networking) is the way we generally notate IP address and subnet declarations. This is useful for finding out A.) What your IP address is, and B.) How big the network you're included in is.

## Checkpoint: Exercise!

Try to find out two things with [ipcalc](http://jodies.de/ipcalc) and [ifconfig](https://en.wikipedia.org/wiki/Ifconfig) - what your IP address is, and how big your network is.

## More! 

[DNS](https://howdns.works/) gives you the ability to use domain names to get to websites, instead of IP addresses (say, 211.45.202.130). Find out how it works.

[TLS](https://www.youtube.com/watch?v=4nGrOpo0Cuc) (Transport Layer Security) allows for security when talking over the general internet. Considering that the internet is a bundle of things that talk to each other with varying levels of trustworthiness, assuring that your message isn't tampered or viewable by other people is highly important.    
An interactive guide [The Illustrated TLS Connection](https://tls.ulfheim.net/) to help you fully understand TLS.

[Routing Tables](https://www.lifewire.com/tcp-ip-router-routing-tables-817584) declare how things travel between local and disparate networks relative to your local network.

## Checkpoint: More exercises!

Try to find out the IP address of the *name server* which is used by `google.com` using the utility [dig](https://ftp.isc.org/isc/bind9/cur/9.9/doc/arm/man.dig.html). Then, try to ask that server directly if it knows the IP address of the server responsible for `github.com`.


