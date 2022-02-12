# **FINAL TASK**

## Pada final task ini, berikut adalah infrastruktur yang akan dibuat:
![final-task-infra](final-task-infra.png) <br>

Akan dibuat sebuah reverse proxy pada web server yang berfungsi untuk melakukan port forwarding suatu request, dari public request menuju ke dalam sistem. Kemudian dalam reverse proxy juga dibuatkan load balance menggunakan method least connections yang mana traffic akan diarahkan ke server yang paling sedikit koneksi atau requestnya.
Untuk app frontend dan backend menggunakan docker untuk deployment-nya. App frontend dan backend akan berjalan 2 container, traffic di 2 container tersebut nantinya akan diatur oleh load balance.
CI/CD menggunakan jenkins dan installasinya menggunakan docker, akan dibuatkan job untuk frontend dan backend app dan di integrasikan dengan masing-masing repository-nya, jika ada update dari repository nantinya akan di proses oleh jenkins untuk dilakukan build app secara otomatis.
Server monitoring menggunakan node-exporter di install di semua instance/server untuk mengambil metrics-nya, prometheus sebagai query metrics diberikan authentication ketika sistemnya diakses. Untuk grafik dan tampilan monitoring menggunakan Grafana.

## **Penyelesaian**
- [Repository](1.repository.md)
- [Server](2.server.md)
- [User](3.user.md)
- [SSH](4.ssh.md)
- [Database](5.database.md)
- [Webserver](6.webserver.md)
- [Deployment](7.deployment.md)
- [CICD](8.cicd.md)
- [Monitoring](9.monitoring.md)
- [Auth](10.auth.md)

