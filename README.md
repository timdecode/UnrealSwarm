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


