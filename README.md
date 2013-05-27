DRMeshGeometry
==============

DRMeshGeometryBuilder is a builder of static mesh geometry that makes it really easy to do 3D graphs in SceneKit.

![An example rendering of a mesh](example.png)

The above geometry was generated with this code (available in the sampe project)

    DRMeshGeometryBuilder *builder = [[DRMeshGeometryBuilder alloc] init];
    builder.numberOfTextureRepeats = DRMeshCountMake(10, 10);
    builder.xRange = DRMeshRangeMake(-20.0, 20.0);
    builder.zRange = DRMeshRangeMake(-20.0, 20.0);
    
    SCNGeometry *sine = [builder geometryWithFunction:^CGFloat(CGFloat x, CGFloat z) {
        return 2.0 * (sinf(.4*x) - cosf(.4*z));
    }];

Once the geometry is generated it can be shaded using any light and material just like normal geometry in the scene.

![Another shading of a sample mesh](light.png)
  

# Known limitations 

 * Only supports continous geometry. 
 * Only cartesian coordinate systems (x,y,z).
 
If you need these additions or find a bug, please file an issue.
