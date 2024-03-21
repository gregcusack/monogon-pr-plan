# Roadmap: Integrating Monogon Test Framework into Agave Repo

## Key Points
- Each commit needs to be consummable for review
- Each commit needs to work and pass CI
- Add tests where/when necessary
- Start w/ bootstrap configuration and deployment, then validators, then RPC, then client
- Update README.md as we go

## Steps
- [ ] Connect to kubernetes endpoint and check if namespace exists
- [ ] Setup build config Local
    - [ ] Build from local commit
    - [ ] Build from tar (release version)
- [ ] Create Genesis
    - [ ] Generate faucet and bootstrap accounts
    - [ ] Build genesis
- [ ] Docker Build
    - [ ] Build Bootstrap Image
    - [ ] Push Image to registry
- [ ] Create & Deploy Secrets
    - [ ] Bootstrap
    - [ ] Validator (regular)
    - [ ] RPC nodes
    - [ ] Client
- [ ] Create & Deploy Selector
    - [ ] Bootstrap
    - [ ] Validator (regular)
    - [ ] RPC nodes
    - [ ] Client
- [ ] Create & Deploy Replica Set
    - [ ] Bootstrap
    - [ ] Validator (regular)
    - [ ] RPC nodes
    - [ ] Client
- [ ] Create & Deploy Services
    - [ ] Bootstrap
    - [ ] Validator (regular)
    - [ ] RPC nodes
    - [ ] Client
- [ ] Check Bootstrap is deployed and running
- [ ] Build and deploy Load Balancer (sits in front of bootstrap and RPC nodes)
- [ ] Add metrics
    - [ ] Bootstrap
    - [ ] Validator (regular)
    - [ ] RPC nodes
    - [ ] Client
- [ ] Create accounts
    - Validator (regular)
    - RPC
    - Client
- [ ] Add feature flags to configure:
    - [ ] Bootstrap
    - [ ] Validator (regular)
    - [ ] RPC nodes
    - [ ] Client

Above, we start with bootstrap, and then we do validators (regular), and then we do RPCs, then Clients
- By the end of the Bootstrap set of PRs, we can
    - Build and deploy a boostrap validator with various configurations
- By the end of the Validator set of PRs, we can
    - Build and deploy N number of validators that operate with the bootstrap
    - Use command line flags to configure validator
- By the end of the RPC set of PRs, we can
    - Build and deploy M RPC nodes behind a load balancer shared with the Bootstrap
    - Use command line flags to configure RPC
- By the end of the Client set of PRs, we can
    - Build and deploy C Client nodes that load the network
    - Use command line flags to set type of client, tx-count, etc

- [ ] Add in kubernetes deployment flags
    - [ ] CPU/Memory Requests
    - [ ] Node Affinity -> Regions
    - [ ] Node Affinity -> Node Type (Equinix/Lumen)

By here:
- We can deploy bootstrap, N validators, M RPC nodes, and C clients with various command line configurations
- We can control the how and where we deploy kubernetes pods

- [ ] Other Features
    - Heterogeneous Clusters (e.g. multiple client versions)
    - Deploy with user-defined stake distribution

By here:
- We can deploy bootstrap, N validators, M RPC nodes, and C clients with various command line configurations
- We can control the how and where we deploy kubernetes pods
- We can deploy multiple cluster versions and have them interact with each other
- We can define a stake distribution for our cluster

DONE
