# Data

Since the amount of data in a single dataset may be very large, it is not possible to directly export the data file, but only the data information, which contains the download address of the data.

```json
{
    // Format version
    "version": "1.0",
    // Data ID (Not required when importing)
    "dataId": 1,
    // Data type
    // LIDAR_BASIC, LIDAR_FUSION, IMAGE
    "type": "LIDAR_FUSION",
    // Name
    "name": "08",
    
    
    // The following are specific to LIDAR_BASIC
    // Point cloud file download address
    "pointCloudUrl": "https://basicai-prod-app-dataset.s3.us-west-2.amazonaws.com/1657877637263-90050/point_cloud/08.pcd"
    // The path inside the point cloud file compression package
    // This field is only available when uploading through a compressed package.
    // Not required when importing
    "pointCloudZipPath": "2022-11-11/point_cloud/08.pcd",
    
    
    // The following are specific to LIDAR_FUSION
    // Camera parameter file download address
    "cameraConfigUrl": "https://basicai-prod-app-dataset.s3.us-west-2.amazonaws.com/1657877637263-90050/camera_config/08.json",
    // The path in the compressed package of the camera parameter file.
    // This field is only available when uploading through a compressed package.
    // Not required when importing.
    "cameraConfigZipPath": "2022-11-11/camera_config/08.json",
    // Camera image information, sorted by camera number
    "cameraImages": [
        {
            // Camera image download address
            "url": "https://basicai-prod-app-dataset.s3.us-west-2.amazonaws.com/1657877637263-90050/image0/08.jpg",
            // The path in the compressed package of the camera parameter file.
            // This field is only available when uploading through a compressed package.
            // Not required when importing.

            "zipPath": "2022-11-11/image0/08.jpg",
            "width": 1920,
            "height": 1080
        }
    ],
    // Point cloud file download address
    "pointCloudUrl": "https://basicai-prod-app-dataset.s3.us-west-2.amazonaws.com/1657877637263-90050/point_cloud/08.pcd"
    // The path in the compressed package of the camera parameter file.
    // This field is only available when uploading through a compressed package.
    // Not required when importing.

    "pointCloudZipPath": "2022-11-11/point_cloud/08.pcd",
    
    
    // The following are specific to IMAGE  
    // Image file download address
    "imageUrl": "https://basicai-prod-app-dataset.s3.us-west-2.amazonaws.com/1657877637263-90050/point_cloud/08.pcd"
    // The path in the compressed package of the camera parameter file.
    // This field is only available when uploading through a compressed package.
    // Not required when importing. 

    "imageZipPath": "2022-11-11/point_cloud/08.pcd",
    "imageWidth": 1920,
    "imageHeight": 1080
}
```

