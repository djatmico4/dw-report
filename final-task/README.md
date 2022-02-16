# **FINAL TASK**

## Pada final task ini, berikut adalah infrastruktur yang akan dibuat:
![final-task-infra](final-task-infra.png) <br>

Akan dibuat sebuah reverse proxy pada web server yang berfungsi untuk melakukan port forwarding suatu request, dari public request menuju ke dalam sistem. Kemudian dalam reverse proxy juga dibuatkan load balance menggunakan method least connections yang mana traffic akan diarahkan ke server yang paling sedikit koneksi atau requestnya.
Untuk app frontend dan backend menggunakan docker untuk deployment-nya. App frontend dan backend akan berjalan 2 container, traffic di 2 container tersebut nantinya akan diatur oleh load balance.
CI/CD menggunakan jenkins dan installasinya menggunakan docker, akan dibuatkan job untuk frontend dan backend app dan di integrasikan dengan masing-masing repository-nya, jika ada update dari repository nantinya akan di proses oleh jenkins untuk dilakukan build app secara otomatis.
Server monitoring menggunakan node-exporter di install di semua instance/server untuk mengambil metrics-nya, prometheus sebagai query metrics diberikan authentication ketika sistemnya diakses. Untuk grafik dan tampilan monitoring menggunakan Grafana.

## **Penyelesaian**
- [Add Repository](1.repository.md)
- [Setup Server](2.server.md)
- [Add new user for new server](3.user.md)
- [Add ssh-key to github](4.ssh.md)
- [Setup database for app](5.database.md)
- [Setup webserver for reverse proxy](6.webserver.md)
- [Deployment frontend and backend application](7.deployment.md)
- [Install and manage CICD](8.cicd.md)
- [Setup monitoring server with prometheus & grafana](9.monitoring.md)
- [Setup auth for Prometheus](10.auth.md)

