---
date: 2021-09-23T17:20
---

# Bevy

Bevy is a game engine written in [[ccdd77e8|Rust]].

I have created a [gamebase](https://github.com/TheNeikos/bevy_spicy_gamebase) for the bevy game engine, which allows for quick game iterations with Aseprite and LDTK.


## Bevy Systems

Bevy is an engine based around the ECS paradigm. The way one interacts with the actual data of the game is through _systems_. These are plain Rust functions that all implement a particular trait called `IntoSystem`. And this trait is implemented for all functions (up to 10~ parameters) that represent "World Interacting" structs. The main ones are:

- `Res`/`ResMut` which allow access to global resources
- `Query` which represents an ECS Query, it has two type components, one is the data one wants to query and the other is a filter.
  - These two parameters are the whole 'magic' of systems, as they allow to say things like "Every Car that has moved in the last frame" and do something with those
- `Commands` which allows insertion/deletion of entities.
  - More about them can be read in [[38996304|commands]]
