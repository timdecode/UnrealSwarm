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
* [Unreal Engine 4 Beginner Tutorial Series - Virtus on Youtube](https://www.youtube.com/watch?v=1M3S3eiJK5I): I haven't watched it personally, but it looks like a comprehensive video introduction to Unreal. However, there are tons of other tutorial out there.
