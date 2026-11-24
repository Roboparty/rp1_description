# RP1 URDF models

| File | Robot configuration |
| --- | --- |
| `rp1.urdf` | 28-DoF body |
| `rp1_24dof.urdf` | 24-DoF body |
| `rp1_hand.urdf` | 28-DoF body with articulated hands |
| `rp1_hand_fixed.urdf` | 28-DoF body with fixed fingers |
| `rp1_hand_bilateral_optimized.urdf` | Articulated hands with detailed collision geometry on both hands |
| `rp1_hand_fixed_bilateral_optimized.urdf` | Fixed fingers with detailed collision geometry on both hands |
| `rp1_hand_left_optimized.urdf` | Articulated hands with detailed collision geometry on the left hand |
| `rp1_hand_fixed_left_optimized.urdf` | Fixed fingers with detailed collision geometry on the left hand |

## Using the detailed hand models

For bimanual manipulation, set your URDF loader's model path to `urdf/rp1_hand_bilateral_optimized.urdf`. Select `urdf/rp1_hand_fixed_bilateral_optimized.urdf` for the same collision geometry with fixed fingers. The joint definitions, inertial properties and visual meshes match the corresponding original URDF.

| Hand | Convex palm meshes | Convex meshes across 16 finger links |
| --- | ---: | ---: |
| [Left](../meshes/collision/left_hand/) | 70 | 173 |
| [Right](../meshes/collision/right_hand/) | 81 | 175 |

The bilateral variants use collision meshes fitted to the CAD for each hand in its own link frames. The `left_optimized` variants pair the detailed left hand with the original right-hand collision geometry. Keep the `urdf/` and `meshes/` directories together when copying a model. MuJoCo scenes loading models from `mjcf/` use the collision geometry defined in those XML files.
