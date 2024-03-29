## Test the loop-free topology

Let us verify that with the spanning tree algorithm in place to ensure a loop-free topology, a broadcast storm cannot occur. We should see that with the spanning tree protocol creating a logical loop-free topology, we can send a broadcast packet without creating a broadcast storm.

For this section, you will need one SSH session on each bridge, and one SSH session on the "romeo" host. 


On each of the four bridges, run

```
sudo tcpdump -env -i br0
```

and then, in the terminal on "romeo", run

```
ping -b -c 1 10.10.0.255
```

to generate a single broadcast packet.

**Lab report**: Compare this result to the previous experiment with a broadcast frame. How many times does the ICMP packet appear on each network segment? Does it reach every network segment? Does a broadcast storm occur?
