# Using External Libraries in MoJaro

----------------------

MoJaro would use the C ABI and would be 1:1 about it in memory. 

as such it would be as simple as: 

``` json
{
    "mojaro.external.library.header": "api.h",
    "mojaro.compiler.version": "1.0.0",
    "mojaro.compiler.path": "C:/Program Files/MoJaroRuntime/bin",
    "mojaro.compiler.binary": "mjc.exe",
    "mojaro.code.env_file": "vsc.env",
    "mojaro.internal.package": [
        "physics.mj"
    ]


}
```

and lets say that `.h` has something to do with physics:

``` C
import "Physics" from 'config';
import "serial" from 'std';
import "io" from 'std';
import "enum" from 'std';

class physics : public {
  struct ColliderShape : public {
    enum ShapeType : public {
        BOX_SHAPE = Physics->ShapeType->SHAPE_BOX;
        SPHERE_SHAPE = Physics->ShapeType->SHAPE_SPHERE;
    }>.return;
    ColliderShape* ShapeType;
  };

  struct PhysicsVars : public {
  int world : [32] = Physics->World;
   struct PhysVec3 : public {} = Physics->Vec3;
   double mass = Physics->mass;
   bool is_static = Physics->is_static;
   double restitution = Physics->restitution;
   double friction = Physics->friction; 
   int body : [32] = Physics->Body;
  }

  fn create_world(Physics->World) {
    alloc(sizeof(PhysicsVars->world));
    if (!world) {return null};
    world->body_count = 0;
    world->gravity = struct Grav* Property((prop_grav)+(Physics)=>{

        (void)->GRAVITY_Y = 0.0;

    });

    return world
  };

  fn destroy_world(world) {
    if (!world) {return};
    for(int i : [64] = 0; i < world->body_count; i++) {
        falloc(sizeof(world->bodies[i]));
    }
    falloc(sizeof(world));
  };

  fn create_phys_body(body = PhysicsVars->body, world = PhysicsVars->world, mass = PhysicsVars->mass, is_static =PhysicsVars->is_static, restitution = PhysicsVars->restitution, friction = PhysicsVars->friction) {
    if (!world || world->body_count >= Physics->MAX_BODIES) {io->err(msg,"world is false, body_count exceeds MAX_BODIES"),return null};
    alloc(sizeof(PhysicsVars->body));
    if (!body) {io->err(msg,"body is false"), return null};
       Physics->create_bodies;
  };
  fn phys_set_box_collider() {
     Physics->set_box_collider;
  };
  fn phys_set_sphere_collider() {
    Physics->set_sphere_collider;
  };

  fn set_phys_gravity(PhysicsVars->PhysVec3->x, PhysicsVars->PhysVec3->y, PhysicsVars->PhysVec3->z) {
    Physics->set_gravity;
  };

  fn phys_apply_force() {
    Physics->apply_force;
  };
};
```

MoJaro uses Implicit Execution Forwarding, the outer wrapper function has it's own space in that threads arena, but the function call is external so it is forwarded and executed by a C Compiler (if you have one installed)
