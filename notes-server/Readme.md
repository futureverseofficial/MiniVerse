# Notes Server

Bu uygulama sadece index.html sayfasını host eden basit bir web sunucu uygulamasıdır. Sayfa her yenilendiğinde kaynak olarak kullanılan JSON dosyasında yer alan bilgilerden rastgele bir tanesi ekrana getirilir. Bu içerikte kitaplardan, bültenlerden, dergilerden, internet sitelerinden derlenmiş bazı ilgi çekici notlar yer almaktadır. Uygulama rust ile yazılmıştır ve projede warp, tokio, serde, handlebars isimli yardımcı küfeler(crates) kullanılmaktadır. warp web sunucusunu, tokio asenkron operasyonları, serde json serileştirme operasyonlarını ve handlebars' da HTML şablonundaki dinamik içerikleri yönetmektedir.

## Dockerize

Uygulama istenirse Dockerize edilerek de çalıştırılabilir. Bunun için sistemde aşağıdaki işlemleri yapmak yeterlidir.

```bash
# Docker Image oluşturma
sudo docker build -t notes-server .

# Image başarılı bir şekilde oluştuysa çalıştırabiliriz.
sudo docker run -d -p 5556:5555 notes-server

# Eğer makine her başlatıldığında bu servis aktif olarak çalışsın istiyorsak aşağıdaki komutu da kullanabiliriz
sudo docker run -d --restart always -p 5556:5555 notes-server
```