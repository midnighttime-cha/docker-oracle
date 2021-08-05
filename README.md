# วิธีติดตั้ง Oracle เวอร์ชั่นต่างๆ ด้วย Docker image โดย Oracle official

ทำการ Download file ติดตั้ง
- [11.2.0.2](https://mega.nz/file/fkYCxLCb#uUfozWIKKf75FXJmv0hIFh8S7Oc0QgugV44PFsVBioc)
- 12.1.0.2
- 12.2.0.1
- 18.3.0
- 18.4.0
- 19.3.0

จากนั้น ทำการ clone docker file จาก git ของ Oracle Official ได้โดย
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
11.2.0.2/  12.1.0.2/  12.2.0.1/  18.3.0/  18.4.0/  19.3.0/  buildContainerImage.sh*
```

ทำการคัดลอกไฟล์ติดตั้ง
```bash
cp ./oracle-xe-11.2.0-1.0.x86_64.rpm.zip ./docker-images/OracleDatabase/SingleInstance/dockerfiles/11.2.0.2/oracle-xe-11.2.0-1.0.x86_64.rpm.zip
```

ทำการ ทำการ Build container ด้วยคำสั่ง
```bash
./buildContainerImage.sh -v 11.2.0.2 -x
```
หมายเหตุ
- -v is Oracle database version to build
- -x to create an image based on 'Express Edition'

เมื่อทำการ Build เรียบร้อยสามารถ ทำการ Run docker ได้ด้วยคำสั่ง
```bash
docker run --name OracleXE \
--shm-size=1g \
-p 1521:1521 \
-p 8081:8080 \
-e ORACLE_PWD=12345 \
-v oracle-data:/u01/app/oracle/oradata \
--restart=always \
oracle/database:11.2.0.2-xe
```

ทดสอบการเชื่อมต่อ
- Host: localhost
- Port: 1521
- Database: XE
- Use SID
- User name: SYS
- Role: SYSDBA
- Password: 12345


### อ้างอิง
- (https://github.com/oracle/docker-images)
