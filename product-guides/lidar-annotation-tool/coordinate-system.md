---
description: >-
  Introduction 2D & 3D Fusion dataset coordinate system including camera
  parameter configuration
---

# 📸 Coordinate System

The point cloud annotation tool mainly involves two coordinate systems:&#x20;

* [3D point cloud coordinate system](coordinate-system.md#3d-point-cloud-coordinate-system)
* [2D image coordinate system](coordinate-system.md#2d-image-coordinate-system)

### 3D Point Cloud Coordinate System

The 3D point cloud tool uses a right-handed coordinate system. The coordinate system of the point cloud data is the world coordinate system, and the coordinate system of the point cloud is up with the Z axis (as shown in the figure below).

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption><p>The position information position of the 3D annotation result is the coordinate value of the relative point cloud coordinate system</p></figcaption></figure>

### 2D Image Coordinate System

The origin of the image in the 2D & 3D fusion tool mapping of the point cloud tool is in the upper left corner of the image. The horizontal represents the X axis. The vertical represents the Y axis.

The X value becomes larger to the right, and the Y value becomes larger downward (as shown in the figure below).

<figure><img src="../../.gitbook/assets/image (5).png" alt=""><figcaption><p>The coordinate position information in the 2D annotation result is the value relative to the image coordinate system.</p></figcaption></figure>

### Camera parameters (for 2D & 3D fusion datasets)

The 2D & 3D mapping conversion process in the tool is basically the same as that of the general dataset, and the conversion parameters include camera extrinsic parameters and camera intrinsic parameters.

Example of camera parameters

```
{
        // or camera_internal
        "cameraInternal": {
            "fx": 933.4667,
            "fy": 934.6754,
            "cx": 896.4692,
            "cy": 507.3557
        },
        "width": 1920,
        "height": 1080,
        // or camera_external
        "cameraExternal": [
            -0.7209479393140598,
            -0.04004438206239668,
            -0.6918312773097581,
            0,
            0.6911177056736608,
            0.0317737123271339,
            -0.7220434530617444,
            0,
            0.05089583188421044,
            -0.9986925846676711,
            0.004768189029478265,
            0,
            0.009297776700688867,
            1.6581292167169648,
            -1.0197515012137728,
            1
        ],
        "rowMajor": false
    }
```

* width: Image width.
* height: Image height
* cameraExternal: Intrinsic parameters of camera
* cameraInternal: Camera matrix with `4x4`
* rowMajor: Whether cameraExternal is the row-major order or not, default is `true`

Refer to [Camera Calibration and 3D Reconstruction](https://docs.opencv.org/2.4/modules/calib3d/doc/camera\_calibration\_and\_3d\_reconstruction.html).

### **Universal Dataset Transformation**

The general data conversion process is as follows:

point coordinates \* camera external parameters \* camera internal parameters = image coordinates

* X/Y/Z: point cloud coordinate system coordinates
* r11...t3: Camera extrinsic parameter matrix information
* Fx/Fy/Cx/Cy: Camera internal parameter information
* S(u,v): Image coordinates

### **Tool data conversion**

The data conversion process of the tool is as follows:

S(u,v) = M(internal) x M(external) x P

* P : point cloud coordinate system coordinates.
* M(internal) : 4x4 internal parameter matrix (row order)
* M(external) : 4x4 external parameter matrix (row order)

When building the camera parameters into the tool, the 4x3 or 3x3 matrix needs to be filled into a 4x4 matrix, as follows:

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption><p>Internal parameter conversion</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (2) (1).png" alt=""><figcaption><p>External parameter conversion</p></figcaption></figure>

**Conversion example (**[**KITTI**](https://www.cvlibs.net/datasets/kitti/)[ **Dataset**](https://www.cvlibs.net/datasets/kitti/)**)**

A 3D point x in Velodyne LiDAR coordinates gets projected to a point y in the i’th camera image as:

`y = P(i) @ R(0) @ Tvelo_cam @ x`

Refer to [kitti-coordinate-transformation](https://towardsdatascience.com/kitti-coordinate-transformations-125094cd42fb).

Code with Three.js

```
// Example: Calculate external matrix of camera 1

// camera 0 projection matrix as internal matrix
// 7.215377e+02 0.000000e+00 6.095593e+02 0.000000e+00
// 0.000000e+00 7.215377e+02 1.728540e+02 0.000000e+00
// 0.000000e+00 0.000000e+00 1.000000e+00 0.000000e+00
let P_rect_matrix_0 = createMatrixFrom4x3(config.cameras[0].P_rect);

// camera 1 projection matrix
// 7.215377e+02 0.000000e+00 6.095593e+02 -3.875744e+02
// 0.000000e+00 7.215377e+02 1.728540e+02 0.000000e+00
// 0.000000e+00 0.000000e+00 1.000000e+00 0.000000e+00
let P_rect_matrix_1 = createMatrixFrom4x3(config.cameras[1].P_rect);
// camera 0 rotate matrix
let R_rect_matrix_0 = createMatrixFrom3x3(config.R_rect);
// velodyne-camera transform
let RT_velo_to_cam_matrix = createMatrixFrom4x3(config.RT_velo_to_cam);

// external parameters
let external_matrix = new THREE.Matrix4().copy(P_rect_matrix_0).invert()
                    .multiply(P_rect_matrix_1)
                    .multiply(R_rect_matrix_0)
                    .multiply(RT_velo_to_cam_matrix);

// elements of THREE.Matrix4 is column-major, need to convert to row-major
external_matrix.transpose()
console.log(external_matrix.elements)
// [0.0002347736981472108,-0.9999441545437641,-0.010563477811052198,-0.5399474051919163,
// 0.010449407416592824,0.010565353641379319,-0.9998895741176488,-0.07510879138296463,
// 0.9999453885620024,0.00012436537838650657,0.010451302995668946,-0.2721327964058732,
// 0,0,0,1]

// internal parameters from camera 0 projection matrix
// fx: 7.215377e+02  fy: 7.215377e+02
// cx: 6.095593e+02  cy: 1.728540e+02


// tool function
// 3x3 convert to 4x4
function createMatrixFrom3x3(a: Array<number>): THREE.Matrix4 {
    return new THREE.Matrix4().set(a[0], a[1], a[2], 0, a[3], a[4], a[5], 0, a[6], a[7], a[8], 0, 0, 0, 0, 1);
}

// 4x3 convert to 4x4
function createMatrixFrom4x3(a: Array<number>): THREE.Matrix4 {
    return new THREE.Matrix4().set(a[0], a[1], a[2], a[3], a[4], a[5], a[6], a[7], a[8], a[9], a[10], a[11], 0, 0, 0, 1);
}
```

### **Conversion example (**[**The PandaSet Dataset**](https://pandaset.org/)**)**

Code with Three.js

```
// poses parameter from poses.json
function createExternalMatrix(poses) {
    let quaternion = new THREE.Quaternion(pos.heading.x, pos.heading.y, pos.heading.z, pos.heading.w);
    let position = new THREE.Vector3(pos.position.x, pos.position.y, pos.position.z);
    let external_matrix = new THREE.Matrix4();
    external_matrix.compose(position, quaternion, new THREE.Vector3(1, 1, 1));

    // elements of THREE.Matrix4 is column-major, need to convert to row-major
    external_matrix.transpose()

    return external_matrix;
}

// internal parameters from intrinsics.json
// { fx: 933.4667, fy: 934.6754, cx: 896.4692, cy: 507.3557 }
```
