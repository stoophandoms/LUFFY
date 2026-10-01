# LUFFY Development Repository

> 🚧 **Development Branch** - This is the main development repository for LUFFY (Learning to Reason Under Off‑Policy Guidance)

## About LUFFY

LUFFY is a reinforcement learning framework that bridges the gap between zero-RL and imitation learning by incorporating off-policy reasoning traces into the training process. This repository contains the core implementation and development work.

## 🔧 Development Status

This repository is under active development. Many features are currently being implemented or need refactoring.

## 🚀 Quick Start

⚠️ **Note**: This development version has incomplete implementations. Many features are marked as TODO and need to be completed before production use.

```bash
# Clone the repository
git clone <repository-url>
cd LUFFY

# Install dependencies
pip install -r luffy/requirements.txt

# Note: Some functionality is incomplete - check TODO list below for details
```

## 📁 Repository Structure

```
LUFFY/
├── luffy/                 # Core framework
│   ├── deepscaler/        # Scaling utilities (⚠️ API integration needed)
│   ├── verl/              # RL training components (⚠️ Some features incomplete)
│   └── ...
├── data/                  # Training data and scripts
├── eval_scripts/          # Evaluation utilities
├── exp_scripts/           # Experiment scripts
└── README.md              # This file
```

## ⚠️ Development Notes

- This is a **development version** with incomplete implementations
- Many functions contain TODO markers indicating pending work
- API integrations (OpenAI, Gemini) are currently placeholder implementations
- FSDP and distributed training features need completion


### 🔴 High Priority TODOs

- **API Integration**: OpenAI and Gemini API implementations need completion
- **Reward System**: Parallel processing and validation for reward computation  
- **FSDP Training**: Model loading and distributed training setup
- **Data Processing**: Batch dimension operations and tensor reshaping

### 📝 Complete TODO List

- [ ] **luffy/deepscaler/utils.py:45** - Add logging for API calls and errors
- [ ] **luffy/deepscaler/utils.py:46** - Support batch processing for multiple prompts
- [ ] **luffy/deepscaler/utils.py:47** - Add timeout configuration for API calls
- [ ] **luffy/deepscaler/utils.py:107** - Implement Vertex AI initialization and authentication
- [ ] **luffy/deepscaler/utils.py:108** - Configure safety settings for content generation
- [ ] **luffy/deepscaler/utils.py:109** - Set up GenerativeModel with proper system instructions
- [ ] **luffy/deepscaler/utils.py:110** - Implement retry logic with exponential backoff
- [ ] **luffy/deepscaler/utils.py:111** - Add comprehensive error handling for API access issues
- [ ] **luffy/deepscaler/utils.py:112** - Handle rate limiting and quota management
- [ ] **luffy/deepscaler/utils.py:113** - Implement response validation and text extraction
- [ ] **luffy/deepscaler/utils.py:114** - Add support for different generation configurations
- [ ] **luffy/test.py:1590** - add smaller page sizes when https://github.com/Dao-AILab/flash-attention/pull/824 is merged
- [ ] **luffy/verl/examples/split_placement/split_monkey_patch.py:141** - make a canonical logger that supports various backend
- [ ] **luffy/verl/tests/e2e/check_results.py:21** - this function needs error handling
- [ ] **luffy/verl/tests/model/test_transformer.py:22** - (sgm): add more models for test
- [ ] **luffy/verl/tests/model/test_transformer.py:50** - (sgm): we can construct the position_ids_rmpad here
- [ ] **luffy/verl/tests/model/test_transformer.py:111** - (sgm): we can construct the position_ids_rmpad here
- [ ] **luffy/verl/tests/model/test_transformers_ulysses.py:34** - (sgm): add more models for test
- [ ] **luffy/verl/tests/model/test_transformers_ulysses.py:81** - (sgm): we can construct the position_ids_rmpad here
- [ ] **luffy/verl/tests/model/test_transformers_ulysses.py:159** - (sgm): we can construct the position_ids_rmpad here
- [ ] **luffy/verl/tests/ray/test_high_level_scheduling_api.py:25** - pass *args and **kwargs is bug prone and not very convincing
- [ ] **luffy/verl/tests/ray/test_worker_group_basics.py:43** - pass *args and **kwargs is bug prone and not very convincing
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:54** - (sgm): support FSDP hybrid shard for larger model
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:83** - it seems that manual offload is slowly than FSDP offload
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:123** - (zhangchi.usc1992): 1. support add checkpoint save/load for FSDP offload; 2. support resharding for non-tensor data; 3. support meta device init for CPU offload
- [ ] **luffy/verl/verl/mix_src/mix_worker_group_dp.py:42** - (zhangchi.usc1992): add support for custom worker group creation
- [ ] **luffy/verl/verl/models/transformers/monkey_patch.py:13** - Monkey patch for wrong dtype in original modeling Llama
- [ ] **luffy/verl/verl/models/weight_loader_registry.py:27** - load the model with correct weight loader
- [ ] **luffy/verl/verl/protocol.py:114** - Optimize memory usage during tensor reshaping
- [ ] **luffy/verl/verl/protocol.py:115** - Add support for different tensor types and shapes
- [ ] **luffy/verl/verl/protocol.py:136** - Optimize tensor view operations for performance
- [ ] **luffy/verl/verl/protocol.py:137** - Add error handling for invalid batch dimensions
- [ ] **luffy/verl/verl/protocol.py:169** - (zhangchi.usc1992) add consistency check
- [ ] **luffy/verl/verl/protocol.py:265** - we can actually lift this restriction if needed
- [ ] **luffy/verl/verl/protocol.py:351** - (zhangchi.usc1992) whether to copy
- [ ] **luffy/verl/verl/single_controller/base/decorator.py:10** - (zhangchi.usc1992) implement the decorator as a normal python function
- [ ] **luffy/verl/verl/single_controller/base/megatron/worker.py:28** - This function uses torch local
- [ ] **luffy/verl/verl/single_controller/base/megatron/worker.py:43** - Implement Megatron worker initialization
- [ ] **luffy/verl/verl/single_controller/base/megatron/worker.py:53** - Implement world size and rank info setup
- [ ] **luffy/verl/verl/single_controller/base/megatron/worker.py:67** - Implement model parallel groups initialization
- [ ] **luffy/verl/verl/single_controller/base/megatron/worker.py:72** - Implement optimizer and learning rate scheduler setup
- [ ] **luffy/verl/verl/single_controller/base/megatron/worker.py:79** - Implement the forward and backward pass
- [ ] **luffy/verl/verl/single_controller/base/megatron/worker.py:96** - Implement the optimizer step
- [ ] **luffy/verl/verl/single_controller/base/megatron/worker.py:103** - Implement the saving checkpoint
- [ ] **luffy/verl/verl/single_controller/base/megatron/worker.py:110** - Implement the loading checkpoint
- [ ] **luffy/verl/verl/single_controller/base/megatron/worker.py:118** - Implement the get/set parameters
- [ ] **luffy/verl/verl/single_controller/base/megatron/worker.py:122** - Implement the get/set gradients
- [ ] **luffy/verl/verl/single_controller/base/megatron/worker.py:131** - Implement the get/set optimizer states
- [ ] **luffy/verl/verl/single_controller/base/megatron/worker.py:135** - Implement the learning rate scheduler step
- [ ] **luffy/verl/verl/single_controller/base/megatron/worker.py:144** - Implement the learning rate scheduler setup
- [ ] **luffy/verl/verl/single_controller/base/register_center/ray.py:50** - (zhangchi.usc1992) setup the torch device
- [ ] **luffy/verl/verl/single_controller/base/register_center/ray.py:63** - (zhangchi.usc1992) setup the distributed training
- [ ] **luffy/verl/verl/single_controller/base/register_center/ray.py:72** - (zhangchi.usc1992) setup the model
- [ ] **luffy/verl/verl/single_controller/base/register_center/ray.py:79** - (zhangchi.usc1992) implement the data_proto_to_tensor_dict
- [ ] **luffy/verl/verl/single_controller/base/register_center/ray.py:86** - (zhangchi.usc1992) implement the tensor_dict_to_data_proto
- [ ] **luffy/verl/verl/single_controller/base/worker.py:27** - Implement worker initialization
- [ ] **luffy/verl/verl/single_controller/base/worker.py:33** - Implement the setup/forward-only/forward-backward/optimizer step
- [ ] **luffy/verl/verl/single_controller/base/worker.py:39** - Implement the get/set parameters and gradients
- [ ] **luffy/verl/verl/single_controller/base/worker.py:46** - Implement the learning rate scheduler step
- [ ] **luffy/verl/verl/single_controller/base/worker.py:52** - Implement the learning rate scheduler setup
- [ ] **luffy/verl/verl/single_controller/base/worker.py:59** - Implement the saving/loading checkpoint
- [ ] **luffy/verl/verl/single_controller/base/worker_group.py:42** - Implement the rank initialization for each worker
- [ ] **luffy/verl/verl/single_controller/base/worker_group.py:68** - Implement the world size setup
- [ ] **luffy/verl/verl/single_controller/base/worker_group.py:83** - Implement the model setup
- [ ] **luffy/verl/verl/single_controller/base/worker_group.py:98** - Implement the optimizer setup
- [ ] **luffy/verl/verl/single_controller/base/worker_group.py:113** - Implement the learning rate scheduler setup
- [ ] **luffy/verl/verl/single_controller/base/worker_group.py:127** - Implement the data parallel group setup
- [ ] **luffy/verl/verl/single_controller/base/worker_group.py:144** - Implement the tensor model parallel group setup
- [ ] **luffy/verl/verl/single_controller/base/worker_group.py:159** - Implement the pipeline model parallel group setup
- [ ] **luffy/verl/verl/single_controller/base/worker_group.py:173** - Implement the sequence parallel group setup
- [ ] **luffy/verl/verl/single_controller/base/worker_group.py:189** - Implement the epoch/step counter initialization
- [ ] **luffy/verl/verl/single_controller/base/worker_group.py:203** - Implement the forward/backward pass
- [ ] **luffy/verl/verl/single_controller/base/worker_group.py:213** - Implement the optimizer step
- [ ] **luffy/verl/verl/single_controller/base/worker_group.py:221** - Implement the learning rate scheduler step
- [ ] **luffy/verl/verl/single_controller/base/worker_group.py:229** - Implement the get/set parameters
- [ ] **luffy/verl/verl/single_controller/base/worker_group.py:235** - Implement the get/set gradients
- [ ] **luffy/verl/verl/single_controller/base/worker_group.py:243** - Implement the get/set optimizer states
- [ ] **luffy/verl/verl/single_controller/base/worker_group.py:254** - Implement the saving checkpoint
- [ ] **luffy/verl/verl/single_controller/base/worker_group.py:264** - Implement the loading checkpoint
- [ ] **luffy/verl/verl/single_controller/base/worker_group.py:277** - Implement the execution of functions on specific workers
- [ ] **luffy/verl/verl/single_controller/ray/base.py:31** - Implement the rank initialization for each worker
- [ ] **luffy/verl/verl/single_controller/ray/base.py:48** - Implement the world size setup
- [ ] **luffy/verl/verl/single_controller/ray/base.py:64** - Implement the model setup
- [ ] **luffy/verl/verl/single_controller/ray/base.py:79** - Implement the optimizer setup
- [ ] **luffy/verl/verl/single_controller/ray/base.py:94** - Implement the learning rate scheduler setup
- [ ] **luffy/verl/verl/single_controller/ray/base.py:109** - Implement the data parallel group setup
- [ ] **luffy/verl/verl/single_controller/ray/base.py:126** - Implement the tensor model parallel group setup
- [ ] **luffy/verl/verl/single_controller/ray/base.py:141** - Implement the pipeline model parallel group setup
- [ ] **luffy/verl/verl/single_controller/ray/base.py:156** - Implement the sequence parallel group setup
- [ ] **luffy/verl/verl/single_controller/ray/base.py:171** - Implement the epoch/step counter initialization
- [ ] **luffy/verl/verl/single_controller/ray/base.py:186** - Implement the forward/backward pass
- [ ] **luffy/verl/verl/single_controller/ray/base.py:196** - Implement the optimizer step
- [ ] **luffy/verl/verl/single_controller/ray/base.py:204** - Implement the learning rate scheduler step
- [ ] **luffy/verl/verl/single_controller/ray/base.py:212** - Implement the get/set parameters
- [ ] **luffy/verl/verl/single_controller/ray/base.py:218** - Implement the get/set gradients
- [ ] **luffy/verl/verl/single_controller/ray/base.py:226** - Implement the get/set optimizer states
- [ ] **luffy/verl/verl/single_controller/ray/base.py:237** - Implement the saving checkpoint
- [ ] **luffy/verl/verl/single_controller/ray/base.py:247** - Implement the loading checkpoint
- [ ] **luffy/verl/verl/single_controller/ray/base.py:260** - Implement the execution of functions on specific workers
- [ ] **luffy/verl/verl/single_controller/ray/megatron.py:23** - Implement the worker group initialization
- [ ] **luffy/verl/verl/single_controller/ray/megatron.py:31** - Implement the world size setup
- [ ] **luffy/verl/verl/single_controller/ray/megatron.py:39** - Implement the model setup
- [ ] **luffy/verl/verl/single_controller/ray/megatron.py:54** - Implement the optimizer setup
- [ ] **luffy/verl/verl/single_controller/ray/megatron.py:69** - Implement the learning rate scheduler setup
- [ ] **luffy/verl/verl/single_controller/ray/megatron.py:84** - Implement the data parallel group setup
- [ ] **luffy/verl/verl/single_controller/ray/megatron.py:101** - Implement the tensor model parallel group setup
- [ ] **luffy/verl/verl/single_controller/ray/megatron.py:116** - Implement the pipeline model parallel group setup
- [ ] **luffy/verl/verl/single_controller/ray/megatron.py:131** - Implement the sequence parallel group setup
- [ ] **luffy/verl/verl/single_controller/ray/megatron.py:146** - Implement the epoch/step counter initialization
- [ ] **luffy/verl/verl/single_controller/ray/megatron.py:161** - Implement the forward/backward pass
- [ ] **luffy/verl/verl/single_controller/ray/megatron.py:171** - Implement the optimizer step
- [ ] **luffy/verl/verl/single_controller/ray/megatron.py:179** - Implement the learning rate scheduler step
- [ ] **luffy/verl/verl/single_controller/ray/megatron.py:187** - Implement the get/set parameters
- [ ] **luffy/verl/verl/single_controller/ray/megatron.py:193** - Implement the get/set gradients
- [ ] **luffy/verl/verl/single_controller/ray/megatron.py:201** - Implement the get/set optimizer states
- [ ] **luffy/verl/verl/single_controller/ray/megatron.py:212** - Implement the saving checkpoint
- [ ] **luffy/verl/verl/single_controller/ray/megatron.py:222** - Implement the loading checkpoint
- [ ] **luffy/verl/verl/single_controller/ray/megatron.py:235** - Implement the execution of functions on specific workers
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:84** - Implement FSDP model loading from checkpoint
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:88** - Implement FSDP model sharding across GPUs
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:94** - Implement distributed training setup
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:100** - Implement proper data collation and tokenization
- [ ] **luffy/verl/verl/trainer/main_ppo.py:28** - (yejun) Add support for parallel and validation sampler
- [ ] **luffy/verl/verl/trainer/main_ppo.py:132** - Implement reward computation with parallel processing
- [ ] **luffy/verl/verl/trainer/main_ppo.py:133** - Add validation and error checking for rewards
- [ ] **luffy/verl/verl/trainer/main_ppo.py:139** - Implement PPO loss computation
- [ ] **luffy/verl/verl/trainer/main_ppo.py:147** - Implement KL penalty computation
- [ ] **luffy/verl/verl/trainer/main_ppo.py:153** - Implement advantage normalization
- [ ] **luffy/verl/verl/trainer/main_ppo.py:160** - Implement value function loss computation
- [ ] **luffy/verl/verl/trainer/main_ppo.py:168** - Implement policy loss computation
- [ ] **luffy/verl/verl/trainer/main_ppo.py:175** - Implement gradient clipping
- [ ] **luffy/verl/verl/trainer/main_ppo.py:182** - Implement optimizer step with learning rate scheduling
- [ ] **luffy/verl/verl/trainer/main_ppo.py:190** - Implement logging and metrics tracking
- [ ] **luffy/verl/verl/trainer/main_ppo.py:210** - Implement checkpoint saving and loading
- [ ] **luffy/verl/verl/trainer/main_ppo.py:216** - Implement distributed training synchronization
- [ ] **luffy/verl/verl/trainer/main_ppo.py:224** - Implement evaluation during training
- [ ] **luffy/verl/verl/trainer/main_ppo.py:232** - Implement proper error handling and retries
- [ ] **luffy/verl/verl/trainer/ppo/core_algos.py:20** - (yejun) add ray support
- [ ] **luffy/verl/verl/trainer/ppo/core_algos.py:44** - (yejun) add length
- [ ] **luffy/verl/verl/trainer/ppo/core_algos.py:45** - add ptx checkpoint to resume training
- [ ] **luffy/verl/verl/trainer/ppo/core_algos.py:50** - (yejun) add length
- [ ] **luffy/verl/verl/trainer/ppo/ray_trainer.py:33** - (yejun) add ray support
- [ ] **luffy/verl/verl/trainer/ppo/ray_trainer.py:79** - add ray support
- [ ] **luffy/verl/verl/trainer/ppo/ray_trainer.py:87** - (yejun) add length
- [ ] **luffy/verl/verl/trainer/ppo/ray_trainer.py:156** - add ray support
- [ ] **luffy/verl/verl/trainer/ppo/ray_trainer.py:157** - (yejun) add length
- [ ] **luffy/verl/verl/utils/checkpoint/checkpoint_manager.py:58** - (yejun) add async
- [ ] **luffy/verl/verl/utils/checkpoint/checkpoint_manager.py:69** - (yejun) add async
- [ ] **luffy/verl/verl/utils/checkpoint/checkpoint_manager.py:79** - (yejun) add async
- [ ] **luffy/verl/verl/utils/checkpoint/checkpoint_manager.py:89** - (yejun) add async
- [ ] **luffy/verl/verl/utils/dataset/rl_dataset.py:15** - (yejun) add support for token id and token str
- [ ] **luffy/verl/verl/utils/distributed.py:15** - (yejun) maybe add using collective to reduce overhead
- [ ] **luffy/verl/verl/utils/fs.py:121** - (yejun) think about non-prefix path. e.g. `~`
- [ ] **luffy/verl/verl/utils/fsdp_utils.py:8** - support cpu offload
- [ ] **luffy/verl/verl/utils/fsdp_utils.py:23** - support cpu offload
- [ ] **luffy/verl/verl/utils/fsdp_utils.py:36** - think about how to support liger kernel
- [ ] **luffy/verl/verl/utils/fsdp_utils.py:65** - think about how to support liger kernel
- [ ] **luffy/verl/verl/utils/logger/aggregate_logger.py:22** - aggregate in a period
- [ ] **luffy/verl/verl/utils/megatron/memory.py:10** - (yejun) add cache- clean function
- [ ] **luffy/verl/verl/utils/megatron/memory.py:17** - (yejun) use the checkpoint
- [ ] **luffy/verl/verl/utils/megatron/memory.py:29** - (yejun) test the code
- [ ] **luffy/verl/verl/utils/seqlen_balancing.py:31** - (yejun) add doc
- [ ] **luffy/verl/verl/utils/seqlen_balancing.py:47** - (yejun) support perfect balance
- [ ] **luffy/verl/verl/utils/torch_functional.py:15** - (yejun) fix me
- [ ] **luffy/verl/verl/utils/torch_functional.py:21** - (yejun) fix me
- [ ] **luffy/verl/verl/utils/torch_functional.py:26** - (yejun) fix me
- [ ] **luffy/verl/verl/utils/torch_functional.py:27** - (yejun) fix me
- [ ] **luffy/verl/verl/utils/torch_functional.py:28** - (yejun) fix me
- [ ] **luffy/verl/verl/utils/torch_functional.py:34** - (yejun) fix me
- [ ] **luffy/verl/verl/utils/torch_functional.py:35** - (yejun) fix me
- [ ] **luffy/verl/verl/utils/torch_functional.py:36** - (yejun) fix me
- [ ] **luffy/verl/verl/utils/torch_functional.py:39** - (yejun) fix me
- [ ] **luffy/verl/verl/utils/torch_functional.py:43** - (yejun) fix me
- [ ] **luffy/verl/verl/utils/torch_functional.py:48** - (yejun) fix me
- [ ] **luffy/verl/verl/utils/torch_functional.py:66** - (yejun) fix me
- [ ] **luffy/verl/verl/utils/torch_functional.py:78** - (yejun) fix me
- [ ] **luffy/verl/verl/workers/actor/base.py:34** - Implement the actor initialization
- [ ] **luffy/verl/verl/workers/actor/base.py:45** - Implement the forward pass
- [ ] **luffy/verl/verl/workers/actor/base.py:56** - Implement the backward pass
- [ ] **luffy/verl/verl/workers/actor/base.py:67** - Implement the optimizer step
- [ ] **luffy/verl/verl/workers/actor/base.py:76** - Implement the get/set parameters
- [ ] **luffy/verl/verl/workers/actor/base.py:83** - Implement the get/set gradients
- [ ] **luffy/verl/verl/workers/actor/base.py:91** - Implement the get/set optimizer states
- [ ] **luffy/verl/verl/workers/actor/base.py:99** - Implement the learning rate scheduler step
- [ ] **luffy/verl/verl/workers/actor/base.py:106** - Implement the saving/loading checkpoint
- [ ] **luffy/verl/verl/workers/actor/dp_actor.py:26** - Implement the actor initialization
- [ ] **luffy/verl/verl/workers/actor/dp_actor.py:36** - Implement the forward pass
- [ ] **luffy/verl/verl/workers/actor/dp_actor.py:47** - Implement the backward pass
- [ ] **luffy/verl/verl/workers/actor/dp_actor.py:58** - Implement the optimizer step
- [ ] **luffy/verl/verl/workers/actor/dp_actor.py:67** - Implement the get/set parameters
- [ ] **luffy/verl/verl/workers/actor/dp_actor.py:74** - Implement the get/set gradients
- [ ] **luffy/verl/verl/workers/actor/dp_actor.py:82** - Implement the get/set optimizer states
- [ ] **luffy/verl/verl/workers/actor/dp_actor.py:90** - Implement the learning rate scheduler step
- [ ] **luffy/verl/verl/workers/actor/dp_actor.py:97** - Implement the saving/loading checkpoint
- [ ] **luffy/verl/verl/workers/actor/megatron_actor.py:26** - Implement the actor initialization
- [ ] **luffy/verl/verl/workers/actor/megatron_actor.py:36** - Implement the forward pass
- [ ] **luffy/verl/verl/workers/actor/megatron_actor.py:47** - Implement the backward pass
- [ ] **luffy/verl/verl/workers/actor/megatron_actor.py:58** - Implement the optimizer step
- [ ] **luffy/verl/verl/workers/actor/megatron_actor.py:67** - Implement the get/set parameters
- [ ] **luffy/verl/verl/workers/actor/megatron_actor.py:74** - Implement the get/set gradients
- [ ] **luffy/verl/verl/workers/actor/megatron_actor.py:82** - Implement the get/set optimizer states
- [ ] **luffy/verl/verl/workers/actor/megatron_actor.py:90** - Implement the learning rate scheduler step
- [ ] **luffy/verl/verl/workers/actor/megatron_actor.py:97** - Implement the saving/loading checkpoint
- [ ] **luffy/verl/verl/workers/critic/base.py:34** - Implement the critic initialization
- [ ] **luffy/verl/verl/workers/critic/base.py:45** - Implement the forward pass
- [ ] **luffy/verl/verl/workers/critic/base.py:56** - Implement the backward pass
- [ ] **luffy/verl/verl/workers/critic/base.py:67** - Implement the optimizer step
- [ ] **luffy/verl/verl/workers/critic/base.py:76** - Implement the get/set parameters
- [ ] **luffy/verl/verl/workers/critic/base.py:83** - Implement the get/set gradients
- [ ] **luffy/verl/verl/workers/critic/base.py:91** - Implement the get/set optimizer states
- [ ] **luffy/verl/verl/workers/critic/base.py:99** - Implement the learning rate scheduler step
- [ ] **luffy/verl/verl/workers/critic/base.py:106** - Implement the saving/loading checkpoint
- [ ] **luffy/verl/verl/workers/critic/dp_critic.py:26** - Implement the critic initialization
- [ ] **luffy/verl/verl/workers/critic/dp_critic.py:36** - Implement the forward pass
- [ ] **luffy/verl/verl/workers/critic/dp_critic.py:47** - Implement the backward pass
- [ ] **luffy/verl/verl/workers/critic/dp_critic.py:58** - Implement the optimizer step
- [ ] **luffy/verl/verl/workers/critic/dp_critic.py:67** - Implement the get/set parameters
- [ ] **luffy/verl/verl/workers/critic/dp_critic.py:74** - Implement the get/set gradients
- [ ] **luffy/verl/verl/workers/critic/dp_critic.py:82** - Implement the get/set optimizer states
- [ ] **luffy/verl/verl/workers/critic/dp_critic.py:90** - Implement the learning rate scheduler step
- [ ] **luffy/verl/verl/workers/critic/dp_critic.py:97** - Implement the saving/loading checkpoint
- [ ] **luffy/verl/verl/workers/critic/megatron_critic.py:26** - Implement the critic initialization
- [ ] **luffy/verl/verl/workers/critic/megatron_critic.py:36** - Implement the forward pass
- [ ] **luffy/verl/verl/workers/critic/megatron_critic.py:47** - Implement the backward pass
- [ ] **luffy/verl/verl/workers/critic/megatron_critic.py:58** - Implement the optimizer step
- [ ] **luffy/verl/verl/workers/critic/megatron_critic.py:67** - Implement the get/set parameters
- [ ] **luffy/verl/verl/workers/critic/megatron_critic.py:74** - Implement the get/set gradients
- [ ] **luffy/verl/verl/workers/critic/megatron_critic.py:82** - Implement the get/set optimizer states
- [ ] **luffy/verl/verl/workers/critic/megatron_critic.py:90** - Implement the learning rate scheduler step
- [ ] **luffy/verl/verl/workers/critic/megatron_critic.py:97** - Implement the saving/loading checkpoint
- [ ] **luffy/verl/verl/workers/fsdp_workers.py:40** - implement the torch process group
- [ ] **luffy/verl/verl/workers/fsdp_workers.py:45** - wrap the model into FSDP
- [ ] **luffy/verl/verl/workers/fsdp_workers.py:50** - implement the offload
- [ ] **luffy/verl/verl/workers/fsdp_workers.py:55** - implement the forward function
- [ ] **luffy/verl/verl/workers/fsdp_workers.py:61** - implement the optimization step
- [ ] **luffy/verl/verl/workers/fsdp_workers.py:66** - implement the checkpoint saving and loading
- [ ] **luffy/verl/verl/workers/reward_model/base.py:33** - Implement the reward model initialization
- [ ] **luffy/verl/verl/workers/reward_model/base.py:43** - Implement the forward pass
- [ ] **luffy/verl/verl/workers/reward_model/base.py:50** - Implement the get/set parameters
- [ ] **luffy/verl/verl/workers/reward_model/base.py:57** - Implement the get/set gradients
- [ ] **luffy/verl/verl/workers/reward_model/megatron/reward_model.py:22** - Implement the reward model initialization
- [ ] **luffy/verl/verl/workers/reward_model/megatron/reward_model.py:31** - Implement the forward pass
- [ ] **luffy/verl/verl/workers/reward_model/megatron/reward_model.py:38** - Implement the get/set parameters
- [ ] **luffy/verl/verl/workers/reward_model/megatron/reward_model.py:45** - Implement the get/set gradients
- [ ] **luffy/verl/verl/workers/rollout/base.py:66** - (yejun): the response tensor should be passed in
- [ ] **luffy/verl/verl/workers/rollout/base.py:70** - (yejun): the response tensor should be passed in
- [ ] **luffy/verl/verl/workers/rollout/hf_rollout.py:91** - (yejun): add support for logprobs
- [ ] **luffy/verl/verl/workers/rollout/hf_rollout.py:98** - filter out the seq with no answers like ds-chat
- [ ] **luffy/verl/verl/workers/rollout/vllm_rollout/vllm_rollout.py:117** - (yejun): add support for cuda graph
- [ ] **luffy/verl/verl/workers/rollout/vllm_rollout/vllm_rollout.py:137** - (yejun): add support for async
- [ ] **luffy/verl/verl/workers/sharding_manager/fsdp_ulysses.py:49** - check how to set seed for each model
- [ ] **luffy/verl/verl/workers/sharding_manager/fsdp_ulysses.py:56** - check how to set seed for each model
- [ ] **luffy/verl/verl/workers/sharding_manager/fsdp_vllm.py:82** - offload FSDP model weights
- [ ] **luffy/verl/verl/workers/sharding_manager/fsdp_vllm.py:113** - Current impl doesn't consider FSDP with torch micro-dp
- [ ] **luffy/verl/verl/workers/sharding_manager/fsdp_vllm.py:122** - Current impl doesn't consider FSDP with torch micro-dp
- [ ] **luffy/verl/verl/workers/sharding_manager/fsdp_vllm.py:130** - shall we build a micro_dp group for vllm when integrating with vLLM?
- [ ] **luffy/verl/verl/workers/sharding_manager/megatron_vllm.py:76** - after binding to the memory buffer, we can load the checkpoint here
- [ ] **luffy/verl/verl/workers/sharding_manager/megatron_vllm.py:253** - (sgm): this may not be true for FSDP -> vLLM
- [ ] **luffy/verl/verl/workers/sharding_manager/megatron_vllm.py:323** - (zhangchi.usc1992) We can consider copy non-tp weight to another infer buffer.

---

## How to Update this TODO List

This TODO list is automatically generated from code comments throughout the repository. To update:

1. Search for `# TODO` in the codebase
2. Implement the functionality
3. Test your implementation
4. Update this README when TODOs are completed
