# RP1 URDF models

| File | Robot configuration |
| --- | --- |
| `rp1.urdf` | 28-DoF body |
| `rp1_24dof.urdf` | 24-DoF body |
| `rp1_hand.urdf` | 28-DoF body with articulated hands |
| `rp1_hand_fixed.urdf` | 28-DoF body with fixed fingers |
| `rp1_hand_left_optimized.urdf` | Articulated hands with detailed left-hand collision geometry |
| `rp1_hand_fixed_left_optimized.urdf` | Fixed fingers with detailed left-hand collision geometry |

## Using the detailed left hand

Set your URDF loader's model path to one of the two `left_optimized` files. Both models use 70 convex collision meshes for the left palm and 173 distributed across its 16 finger links. The right hand uses the same collision geometry as in the corresponding original model. The joint definitions, inertial properties and visual meshes match the respective original URDF.

The collision meshes are in [`meshes/collision/left_hand/`](../meshes/collision/left_hand/). Keep the `urdf/` and `meshes/` directories together when copying a model. These variants are selected by URDF path. MuJoCo scenes loading an XML file from `mjcf/` use the collision geometry defined in that XML.
