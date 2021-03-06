
# Bootcamp Case 2 :

    1.  Manuel olarak 3 adet VM yaratılacak. (1 core işlemci, 2 GB memory yeterli olacaktır.)
    
    -   Makinelere 5 GB object storage disk eklenecek.
    
    3.  Bu makinelere Ansible üzerinden minio deployment yapılacak. (Open source object storage solution)
    
    -   Object storage diski üzerine, bir volume group tanımlanacak.
    -   Volume group üzerine, 8 adet logical volume tanımlanacak.
    -   Bu logical volume’lar üzerine, filesystem yaratılacak.
    -   Kurulu minio server, systemctl üzerinden yönetilebilecek şekilde bir custom service yazılacak. (Bkz: “systemctl start minio.d”)

Kurgulanan Ortam yapısı şu şekildedir.

 - core/centos : 192.168.233.134
 - centos 1 : 192.168.233.133/24
 - centos :2 : 192.168.233.132/24
 - centos 3:  192.168.233.129/24 

> VMWare Workstation üzerinde 4 adet 2Gb Ram 1 core CPU VM olarak yaratılmıştır.

Öncelikle sunucumuza 5 GB object storage disk ekleyerek başlayalım.  Hali hazırda ekli olanları görmek için bu komutu kullanabiliriz.

```bash
fdisk -l
```

Sonrasında aşağıdaki komutla ilgili partition'ı yaratıyoruz. 
```bash
fdisk /dev/sdb1
```

> Burada **n p w** komutlarıyla ilerlerken LVM dosyamız için **8e** hash'ini seçiyoruz.

Ardından ilgili yerden çıkıyoruz. Ve kurulum başarıyla tamamlandı.

Sonrasında ilk olarak tanıtacağımız diske format atacağız.  _Eğer diskiniz önceden unix tabanlı bir sistemde ise formata gerek yok yani elinideki bir yedek diski olabilir vs._

```bash
mkfs.ext3 /dev/sdb1
```

Yeni diskin mount edileceği klasör yolunu oluşturalım

```bash
mkdir /disk2
```

Şimdi diskimizi oluşturduğumuz klasör yoluna mount edelim.

```bash
mount /dev/sdb1 /disk2
```

Diskiniz kullanıma hazır. Disklerimizi görmek için  `df -h`  komutunu kullanabilirsiniz.

Ardıdan oluşturduğumuz ansible playbook ile 8 adet partition yaratıyoruz.

    ansible-playbook -k playbooks/volume.yml

Ardından Disklerimizi görmek için `df -h` komutunu kullanabilirsiniz.

![diskler başarıyla oluştu](https://cloudflare-ipfs.com/ipfs/QmXoFgMdYqogL1ysJcA9XBEXB9coxpL3adde23yr8zV4aD)









