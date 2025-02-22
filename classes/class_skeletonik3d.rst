:github_url: hide

.. DO NOT EDIT THIS FILE!!!
.. Generated automatically from Godot engine sources.
.. Generator: https://github.com/godotengine/godot/tree/master/doc/tools/make_rst.py.
.. XML source: https://github.com/godotengine/godot/tree/master/doc/classes/SkeletonIK3D.xml.

.. _class_SkeletonIK3D:

SkeletonIK3D
============

**Inherits:** :ref:`Node<class_Node>` **<** :ref:`Object<class_Object>`

SkeletonIK3D is used to place the end bone of a :ref:`Skeleton3D<class_Skeleton3D>` bone chain at a certain point in 3D by rotating all bones in the chain accordingly.

.. rst-class:: classref-introduction-group

Description
-----------

SkeletonIK3D is used to place the end bone of a :ref:`Skeleton3D<class_Skeleton3D>` bone chain at a certain point in 3D by rotating all bones in the chain accordingly. A typical scenario for IK in games is to place a characters feet on the ground or a characters hands on a currently hold object. SkeletonIK uses FabrikInverseKinematic internally to solve the bone chain and applies the results to the :ref:`Skeleton3D<class_Skeleton3D>` ``bones_global_pose_override`` property for all affected bones in the chain. If fully applied this overwrites any bone transform from :ref:`Animation<class_Animation>`\ s or bone custom poses set by users. The applied amount can be controlled with the ``interpolation`` property.

::

    # Apply IK effect automatically on every new frame (not the current)
    skeleton_ik_node.start()
    
    # Apply IK effect only on the current frame
    skeleton_ik_node.start(true)
    
    # Stop IK effect and reset bones_global_pose_override on Skeleton
    skeleton_ik_node.stop()
    
    # Apply full IK effect
    skeleton_ik_node.set_interpolation(1.0)
    
    # Apply half IK effect
    skeleton_ik_node.set_interpolation(0.5)
    
    # Apply zero IK effect (a value at or below 0.01 also removes bones_global_pose_override on Skeleton)
    skeleton_ik_node.set_interpolation(0.0)

.. rst-class:: classref-introduction-group

Tutorials
---------

- `3D Inverse Kinematics Demo <https://godotengine.org/asset-library/asset/523>`__

.. rst-class:: classref-reftable-group

Properties
----------

.. table::
   :widths: auto

   +---------------------------------------+---------------------------------------------------------------------------+-----------------------------------------------------+
   | :ref:`float<class_float>`             | :ref:`interpolation<class_SkeletonIK3D_property_interpolation>`           | ``1.0``                                             |
   +---------------------------------------+---------------------------------------------------------------------------+-----------------------------------------------------+
   | :ref:`Vector3<class_Vector3>`         | :ref:`magnet<class_SkeletonIK3D_property_magnet>`                         | ``Vector3(0, 0, 0)``                                |
   +---------------------------------------+---------------------------------------------------------------------------+-----------------------------------------------------+
   | :ref:`int<class_int>`                 | :ref:`max_iterations<class_SkeletonIK3D_property_max_iterations>`         | ``10``                                              |
   +---------------------------------------+---------------------------------------------------------------------------+-----------------------------------------------------+
   | :ref:`float<class_float>`             | :ref:`min_distance<class_SkeletonIK3D_property_min_distance>`             | ``0.01``                                            |
   +---------------------------------------+---------------------------------------------------------------------------+-----------------------------------------------------+
   | :ref:`bool<class_bool>`               | :ref:`override_tip_basis<class_SkeletonIK3D_property_override_tip_basis>` | ``true``                                            |
   +---------------------------------------+---------------------------------------------------------------------------+-----------------------------------------------------+
   | :ref:`StringName<class_StringName>`   | :ref:`root_bone<class_SkeletonIK3D_property_root_bone>`                   | ``&""``                                             |
   +---------------------------------------+---------------------------------------------------------------------------+-----------------------------------------------------+
   | :ref:`Transform3D<class_Transform3D>` | :ref:`target<class_SkeletonIK3D_property_target>`                         | ``Transform3D(1, 0, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0)`` |
   +---------------------------------------+---------------------------------------------------------------------------+-----------------------------------------------------+
   | :ref:`NodePath<class_NodePath>`       | :ref:`target_node<class_SkeletonIK3D_property_target_node>`               | ``NodePath("")``                                    |
   +---------------------------------------+---------------------------------------------------------------------------+-----------------------------------------------------+
   | :ref:`StringName<class_StringName>`   | :ref:`tip_bone<class_SkeletonIK3D_property_tip_bone>`                     | ``&""``                                             |
   +---------------------------------------+---------------------------------------------------------------------------+-----------------------------------------------------+
   | :ref:`bool<class_bool>`               | :ref:`use_magnet<class_SkeletonIK3D_property_use_magnet>`                 | ``false``                                           |
   +---------------------------------------+---------------------------------------------------------------------------+-----------------------------------------------------+

.. rst-class:: classref-reftable-group

Methods
-------

.. table::
   :widths: auto

   +-------------------------------------+--------------------------------------------------------------------------------------------------+
   | :ref:`Skeleton3D<class_Skeleton3D>` | :ref:`get_parent_skeleton<class_SkeletonIK3D_method_get_parent_skeleton>` **(** **)** |const|    |
   +-------------------------------------+--------------------------------------------------------------------------------------------------+
   | :ref:`bool<class_bool>`             | :ref:`is_running<class_SkeletonIK3D_method_is_running>` **(** **)**                              |
   +-------------------------------------+--------------------------------------------------------------------------------------------------+
   | void                                | :ref:`start<class_SkeletonIK3D_method_start>` **(** :ref:`bool<class_bool>` one_time=false **)** |
   +-------------------------------------+--------------------------------------------------------------------------------------------------+
   | void                                | :ref:`stop<class_SkeletonIK3D_method_stop>` **(** **)**                                          |
   +-------------------------------------+--------------------------------------------------------------------------------------------------+

.. rst-class:: classref-section-separator

----

.. rst-class:: classref-descriptions-group

Property Descriptions
---------------------

.. _class_SkeletonIK3D_property_interpolation:

.. rst-class:: classref-property

:ref:`float<class_float>` **interpolation** = ``1.0``

.. rst-class:: classref-property-setget

- void **set_interpolation** **(** :ref:`float<class_float>` value **)**
- :ref:`float<class_float>` **get_interpolation** **(** **)**

Interpolation value for how much the IK results are applied to the current skeleton bone chain. A value of ``1.0`` will overwrite all skeleton bone transforms completely while a value of ``0.0`` will visually disable the SkeletonIK. A value at or below ``0.01`` also calls :ref:`Skeleton3D.clear_bones_global_pose_override<class_Skeleton3D_method_clear_bones_global_pose_override>`.

.. rst-class:: classref-item-separator

----

.. _class_SkeletonIK3D_property_magnet:

.. rst-class:: classref-property

:ref:`Vector3<class_Vector3>` **magnet** = ``Vector3(0, 0, 0)``

.. rst-class:: classref-property-setget

- void **set_magnet_position** **(** :ref:`Vector3<class_Vector3>` value **)**
- :ref:`Vector3<class_Vector3>` **get_magnet_position** **(** **)**

Secondary target position (first is :ref:`target<class_SkeletonIK3D_property_target>` property or :ref:`target_node<class_SkeletonIK3D_property_target_node>`) for the IK chain. Use magnet position (pole target) to control the bending of the IK chain. Only works if the bone chain has more than 2 bones. The middle chain bone position will be linearly interpolated with the magnet position.

.. rst-class:: classref-item-separator

----

.. _class_SkeletonIK3D_property_max_iterations:

.. rst-class:: classref-property

:ref:`int<class_int>` **max_iterations** = ``10``

.. rst-class:: classref-property-setget

- void **set_max_iterations** **(** :ref:`int<class_int>` value **)**
- :ref:`int<class_int>` **get_max_iterations** **(** **)**

Number of iteration loops used by the IK solver to produce more accurate (and elegant) bone chain results.

.. rst-class:: classref-item-separator

----

.. _class_SkeletonIK3D_property_min_distance:

.. rst-class:: classref-property

:ref:`float<class_float>` **min_distance** = ``0.01``

.. rst-class:: classref-property-setget

- void **set_min_distance** **(** :ref:`float<class_float>` value **)**
- :ref:`float<class_float>` **get_min_distance** **(** **)**

The minimum distance between bone and goal target. If the distance is below this value, the IK solver stops further iterations.

.. rst-class:: classref-item-separator

----

.. _class_SkeletonIK3D_property_override_tip_basis:

.. rst-class:: classref-property

:ref:`bool<class_bool>` **override_tip_basis** = ``true``

.. rst-class:: classref-property-setget

- void **set_override_tip_basis** **(** :ref:`bool<class_bool>` value **)**
- :ref:`bool<class_bool>` **is_override_tip_basis** **(** **)**

If ``true`` overwrites the rotation of the tip bone with the rotation of the :ref:`target<class_SkeletonIK3D_property_target>` (or :ref:`target_node<class_SkeletonIK3D_property_target_node>` if defined).

.. rst-class:: classref-item-separator

----

.. _class_SkeletonIK3D_property_root_bone:

.. rst-class:: classref-property

:ref:`StringName<class_StringName>` **root_bone** = ``&""``

.. rst-class:: classref-property-setget

- void **set_root_bone** **(** :ref:`StringName<class_StringName>` value **)**
- :ref:`StringName<class_StringName>` **get_root_bone** **(** **)**

The name of the current root bone, the first bone in the IK chain.

.. rst-class:: classref-item-separator

----

.. _class_SkeletonIK3D_property_target:

.. rst-class:: classref-property

:ref:`Transform3D<class_Transform3D>` **target** = ``Transform3D(1, 0, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0)``

.. rst-class:: classref-property-setget

- void **set_target_transform** **(** :ref:`Transform3D<class_Transform3D>` value **)**
- :ref:`Transform3D<class_Transform3D>` **get_target_transform** **(** **)**

First target of the IK chain where the tip bone is placed and, if :ref:`override_tip_basis<class_SkeletonIK3D_property_override_tip_basis>` is ``true``, how the tip bone is rotated. If a :ref:`target_node<class_SkeletonIK3D_property_target_node>` path is available the nodes transform is used instead and this property is ignored.

.. rst-class:: classref-item-separator

----

.. _class_SkeletonIK3D_property_target_node:

.. rst-class:: classref-property

:ref:`NodePath<class_NodePath>` **target_node** = ``NodePath("")``

.. rst-class:: classref-property-setget

- void **set_target_node** **(** :ref:`NodePath<class_NodePath>` value **)**
- :ref:`NodePath<class_NodePath>` **get_target_node** **(** **)**

Target node :ref:`NodePath<class_NodePath>` for the IK chain. If available, the node's current :ref:`Transform3D<class_Transform3D>` is used instead of the :ref:`target<class_SkeletonIK3D_property_target>` property.

.. rst-class:: classref-item-separator

----

.. _class_SkeletonIK3D_property_tip_bone:

.. rst-class:: classref-property

:ref:`StringName<class_StringName>` **tip_bone** = ``&""``

.. rst-class:: classref-property-setget

- void **set_tip_bone** **(** :ref:`StringName<class_StringName>` value **)**
- :ref:`StringName<class_StringName>` **get_tip_bone** **(** **)**

The name of the current tip bone, the last bone in the IK chain placed at the :ref:`target<class_SkeletonIK3D_property_target>` transform (or :ref:`target_node<class_SkeletonIK3D_property_target_node>` if defined).

.. rst-class:: classref-item-separator

----

.. _class_SkeletonIK3D_property_use_magnet:

.. rst-class:: classref-property

:ref:`bool<class_bool>` **use_magnet** = ``false``

.. rst-class:: classref-property-setget

- void **set_use_magnet** **(** :ref:`bool<class_bool>` value **)**
- :ref:`bool<class_bool>` **is_using_magnet** **(** **)**

If ``true``, instructs the IK solver to consider the secondary magnet target (pole target) when calculating the bone chain. Use the magnet position (pole target) to control the bending of the IK chain.

.. rst-class:: classref-section-separator

----

.. rst-class:: classref-descriptions-group

Method Descriptions
-------------------

.. _class_SkeletonIK3D_method_get_parent_skeleton:

.. rst-class:: classref-method

:ref:`Skeleton3D<class_Skeleton3D>` **get_parent_skeleton** **(** **)** |const|

Returns the parent :ref:`Skeleton3D<class_Skeleton3D>` Node that was present when SkeletonIK entered the :ref:`SceneTree<class_SceneTree>`. Returns null if the parent node was not a :ref:`Skeleton3D<class_Skeleton3D>` Node when SkeletonIK3D entered the :ref:`SceneTree<class_SceneTree>`.

.. rst-class:: classref-item-separator

----

.. _class_SkeletonIK3D_method_is_running:

.. rst-class:: classref-method

:ref:`bool<class_bool>` **is_running** **(** **)**

Returns ``true`` if SkeletonIK is applying IK effects on continues frames to the :ref:`Skeleton3D<class_Skeleton3D>` bones. Returns ``false`` if SkeletonIK is stopped or :ref:`start<class_SkeletonIK3D_method_start>` was used with the ``one_time`` parameter set to ``true``.

.. rst-class:: classref-item-separator

----

.. _class_SkeletonIK3D_method_start:

.. rst-class:: classref-method

void **start** **(** :ref:`bool<class_bool>` one_time=false **)**

Starts applying IK effects on each frame to the :ref:`Skeleton3D<class_Skeleton3D>` bones but will only take effect starting on the next frame. If ``one_time`` is ``true``, this will take effect immediately but also reset on the next frame.

.. rst-class:: classref-item-separator

----

.. _class_SkeletonIK3D_method_stop:

.. rst-class:: classref-method

void **stop** **(** **)**

Stops applying IK effects on each frame to the :ref:`Skeleton3D<class_Skeleton3D>` bones and also calls :ref:`Skeleton3D.clear_bones_global_pose_override<class_Skeleton3D_method_clear_bones_global_pose_override>` to remove existing overrides on all bones.

.. |virtual| replace:: :abbr:`virtual (This method should typically be overridden by the user to have any effect.)`
.. |const| replace:: :abbr:`const (This method has no side effects. It doesn't modify any of the instance's member variables.)`
.. |vararg| replace:: :abbr:`vararg (This method accepts any number of arguments after the ones described here.)`
.. |constructor| replace:: :abbr:`constructor (This method is used to construct a type.)`
.. |static| replace:: :abbr:`static (This method doesn't need an instance to be called, so it can be called directly using the class name.)`
.. |operator| replace:: :abbr:`operator (This method describes a valid operator to use with this type as left-hand operand.)`
