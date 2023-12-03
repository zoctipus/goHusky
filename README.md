Project goHusky

This a a project adapted from [Puppo, The Corgi - Unity Blog](https://blog.unity.com/engine-platform/puppo-the-corgi-cuteness-overload-with-the-unity-ml-agents-toolkit) With update of 
# Project Name: goHusky

## Contents

1. [Modern Ways of Using ML-Agents Library Function Calls](#modern-ml-agents)
2. [UW-Themed Scene with Husky](#uw-themed-scene)
3. [Project Setup](#project-setup)
4. [Training Script Provided](#training-script)

## Modern Ways of Using ML-Agents Library Function Calls <a name="modern-ml-agents"></a>

- Describe the modern ways of using ML-Agents library function calls in your project.
- Initialize()
- OnEpisodeBegin()
- CollectObservations(VectorSensor sensor)
- OnActionReceived(ActionBuffers actions)
- FixedUpdate()

## UW-Themed Scene with Husky <a name="uw-themed-scene"></a>

- Showcase the UW-themed scene with the Husky character.
![Alt Text](goHusky.png)
- [Demo](https://drive.google.com/file/d/16MwlWZDvgC36cPbYV7LD5hqD-6m4coSb/view?usp=drive_link)


## Project Setup <a name="project-setup"></a>

## Training Script(from Hugging Face)

```yaml
behaviors:
  CorgiFetch:
    trainer_type: ppo
    hyperparameters:
      batch_size: 2048
      buffer_size: 20480
      learning_rate: 0.0003
      beta: 0.005
      epsilon: 0.2
      lambd: 0.95
      num_epoch: 3
      learning_rate_schedule: linear
    network_settings:
      normalize: true
      hidden_units: 512
      num_layers: 3
      vis_encode_type: simple
    reward_signals:
      extrinsic:
        gamma: 0.995
        strength: 1.0
    checkpoint_interval: 200000
    keep_checkpoints: 15
    max_steps: 2e7
    time_horizon: 1000
    summary_freq: 50000



