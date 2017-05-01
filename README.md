# UnrealSwarm

This is a blueprint implementation of a [Boid](https://en.wikipedia.org/wiki/Boids) simulation in Unreal. 

The following urges are implemented in function inside of the BoidActor blueprint:
* separation
* alignment
* cohesion

The neighbours of each boid are found using Unreal's collision system. Each boid has a SphereCollisionComponent and this is queired in `Event Tick` to efficiently find all the nearby boids that overlap with that sphere. This should scale to a large number of actors. To achieve even more boids one could use UInstanceStaticMeshComponent.

The BoidActor has a few other components:
* `collisionSphere` simulates the physics and collision response with other boids
* the `visibleMesh` (a cone by default) is for show, it does not collide with other agents
* `overlapSphere` is used to find neighbouring boids to interact with, it is not a mesh because mesh overlap detection is slow
* `visibleOverlapSphere` is a pretty representation of the `overlapSphere`

# Learn Unreal

2017 Summer Students of the Lindsay Virutal Human Project here are some links to get you started with Unreal:
* [Unreal Engine](https://www.unrealengine.com/)
* [Unreal Engine Documentation Hub](https://docs.unrealengine.com/latest/INT/index.html)
* [Get Started with UE4](https://docs.unrealengine.com/latest/INT/GettingStarted/index.html)
* [Blueprints Visual Scripting](https://docs.unrealengine.com/latest/INT/Engine/Blueprints/GettingStarted/index.html)
* [Unreal's Video Tutorials](https://docs.unrealengine.com/latest/INT/Videos/) Videos are a good way to learn workflows outside of the written documentation.
* [Unreal Wiki](https://wiki.unrealengine.com/Main_Page) The Unreal wiki also has important documentation that is not covered directly by Epic's engineers.
