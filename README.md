# Boids in Unity

A 3D flocking prototype that combines cohesion, separation, and alignment to produce group motion from local steering rules. Each agent also steers back toward the flock’s center near the bounds.

## Try it

1. Open the repository root in **Unity 2022.3.10f1**.
2. Load [SampleScene](Assets/Scenes/SampleScene.unity) and enter Play Mode.
3. Select the flock object and tune population size, speed range, neighbor distances, and behavior weights in the Inspector. Increase separation to spread agents out or increase alignment to make their headings converge.

## Code tour

- [Flock.cs](Assets/Scripts/Flock.cs) spawns the units, stores shared settings, and updates each agent.
- [FlockUnit.cs](Assets/Scripts/FlockUnit.cs) scans neighbors, filters steering contributions by field of view, and smooths the resulting direction.

The prototype scans the flock per agent. The number of neighbor comparisons grows quadratically with population size.
