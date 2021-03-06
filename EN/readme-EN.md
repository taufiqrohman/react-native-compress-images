# react native compress images
![Platform - Android](https://img.shields.io/badge/platform-Android-yellow.svg)  ![MIT](https://img.shields.io/dub/l/vibe-d.svg)
----------
A React Native module that allows you to compress you images.( currently just support android).

## install

yarn add react-native-compress-images
## Automatic Installation
react-native link
## Usage
1, import CompressImages from 'react-native-compress-images';

2, 
```
CompressImages({
			urlList: ['storage/emulated/0/Pictures/image-b1ae0ff3-c014-4e37-b510-f00d6ec88b08.jpg']
              }).then((res) => {
                  console.log(res);
                  // base64
                  console.log("data:image/jpeg;base64,"+data.base64List[0]);
              })
```              
## Type
now Support two types.
##### set type = 'compressSzie'
Compress picture quality and size. this way will change picture size. Picture size is small
#####set type = 'quality'
this way just compress picture quality.
(support library: [Luban](https://github.com/Curzibn/Luban))
## Options

| option     |   Info   |
| :-------- |:------: |
| type| compressSize or quality. default compressSize|
| urlList    | image path array。just like this: ['storage/emulated/0/Pictures/image-b1ae0ff3-c014-4e37-b510-f00d6ec88b08.jpg', 'image2.png']  |
|maxWidth| definition compressed picture maxWidth. default : 380(Only when the type is equal to the 'compressSzie' is valid)|
|maxHeight| definition compressed picture maxHeight. default : 600(Only when the type is equal to the 'compressSzie' is valid)|
|quality| 0~100  default: 60|
|saveImages | Save the picture to the local. if set false, module will return base64 image list. default true(Only when the type is equal to the 'compressSzie' is valid)|
|resultBase64 |  if set true, module will return base64 picture list. default: false(Only when the type is equal to the 'compressSzie' is valid)|
## The Response Object
| option     |   Info   |
| :-------- |:------: |
| status | success or error|
| msg | when status equals 'error' will return|
| urlList | local picture path list.(only saveImages === true)|
| base64List | compressed picture base64 list.(saveImages === false or resultBase64 === true)|
#### Note
Repeatedly call the module, the compressed picture will overwrite the last compressed picture. So make sure the last compressed image is invalid.