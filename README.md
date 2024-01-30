# Topology file for Nebius AI GPU clusters

For Nebius AI virtual machines in [GPU clusters](https://nebius.ai/docs/compute/concepts/gpu-clusters), the PCI device topology differs from the default bare-metal one.

This file describes how Nebius AI hardware and InfiniBand network are designed from the VM perspective. After applying it, all workloads that are using NCCL in multi-host environment will be more stable and have better performance results.

To run stable NCCL tests and improve workloads performance, apply Nebius AI topology on your VMs or inside containers you run on the VMs:

1. Download `nccl-topo-h100-v1.xml`. 

1. Set the path to the downloaded file via the `NCCL_TOPO_FILE` environment variable. For example:

   ```
   export NCCL_TOPO_FILE=/opt/nebius/nccl-topo-h100-v1.xml
   ```

For more information about testing GPU clusters in Nebius AI, see the [documentation](https://nebius.ai/docs/compute/operations/#gpu-test).
