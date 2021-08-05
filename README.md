# วิธีติดทำ Oracle เวอร์ชั่นต่างๆ ด้วย oracle-image

ทำการ Download file ติดตั้ง
- [11.2.0.2](https://mega.nz/file/fkYCxLCb#uUfozWIKKf75FXJmv0hIFh8S7Oc0QgugV44PFsVBioc)
- 12.1.0.2
- 12.2.0.1
- 18.3.0
- 18.4.0
- 19.3.0
เราสามารถ clone docker file จาก git ของ Oracle Official ได้โดย
```bash
git clone https://github.com/oracle/docker-images.git
```

จากนั้นทำการ
```bash
cd docker-images/OracleDatabase/SingleInstance/dockerfiles
```

เรียกดูไฟล์
```bash
ls
....
# Output
11.2.0.2/  12.1.0.2/  12.2.0.1/  18.3.0/  18.4.0/  19.3.0/  buildDockerImage.sh*
```

