# Do Transformers Need Deep Long-Range Memory?
## By Jack Rae, Ali Razavi

* Quesitons:
    * Do transformers need long-range memory representations at every layer?
        * Transformer-XL can use ~3.4GB memory.
    * Can we save space and computation by having fewer long-range memories?

* Intervention experiment:
    * Memory types:
        * Long range memory - 1000s of slots
        * Short range memory - 100s of slots.
    * Ablation models tried (same number of parameters):
        * First layers: Reverse of "Last layers"
        * Interleaved: Interleave long and short range memories.
        * Last layers: Short range memory in bottom layers and long range memory in top layers.
    * Result (LM):
        * Long range memory is required for good performance!
        * Having long range memory in just first few layers is the worst configuration.
        * Interleaving long range memories with short range memories is the best. Close second is having long range memories in last layers.
        * With just 4 long range memories (interleaved with short range memories), the performance is quite close to having all 24 long range memories.  
