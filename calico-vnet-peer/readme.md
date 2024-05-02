## Calico Policies for Azure VNet Peer

Sample policies for when you have an AKS Cluster with multiple VNET Peers to the AKS VNet.

You may not want all traffic from the cluster to be able to reach all vnets, or vice versa, so you can restrict this with the following.

1. Deny traffic to all Peered VNet Ranges at the cluster level.
    - The cluster can talk outbound and internal, but not to the peers
2. Allow workloads in the cluster matching a specific tag (tenant in this example) to communicate to its own peered VNet
    - This stacks on top of the global deny policy to allow just that access
3. Repeat as needed for additional customers in the cluster.