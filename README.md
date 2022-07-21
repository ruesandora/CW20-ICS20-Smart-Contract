<h1 align="center"> CW20-ICS20-Smart-Contract </h1> 

### Selamlar Bugün kendimize ait CW20 token oluşturacağız ek olarak CW20-ICS20 Akıllı Sözleşmeleri kullanarak IBC üzerinden transfer yapacağız.

# CW20 nedir?

### CW20, Kısaca ERC-20 gibi düşünebilirsiniz, CW20 Token oluşturmak için Juno mint kullanıyoruz. Juno mint, Juno üzerinde akıllı sözleşmeler ile kodlama gerektirmeden kendi tokenimizi oluşturduğumuz platformdur.

# Nerede işimize yarıyacak?

### Şu an Sei Network Atlantic-1 testnetinde ihtiyacımız olacak, size anlatacağım.

# İhtiyacımız olan şeyler.

* Sei Networkte oluşturduğumuz cüzdan (normal şartlarda herhangi bir keplrda olur, sei görevi yapmak için diyorum)

* Juno test tokeni.

* Juno test ağı

* Sei ağı

* En önemlisi tüm floodu okuma becerisi <3

# BEN TOKEN OLUŞTURMAYACAĞIM, EN KISA YOLU GÖSTER HOCAM DERSEN FLOODUN SONUNDA.

# İlk önce yeni bir keplr cüzandan sei'de ki 12 kelimemizi kullanarak cüzdan oluşturuyoruz.

### Daha sonra https://testnets.cosmosrun.info/sei-testnet üzerine gidip sağ üsten cüzdanı bağlamalıyız.

* Yukaıda DISCLAIMER: uyarısını önemsemeyin, alta gelip Enable keplr diyerek sei ağını ekleyin.
* Keplrda çıkan sei cüzdanınız mainnet. adresler farklı olabilir aynı olursada umursamayın.

![image](https://user-images.githubusercontent.com/101149671/180020630-ee51e1c8-f977-40d3-b1b1-eb97289246ba.png)

# Daha sonra https://junomint.com/ üzerinden juno test ağını ekleyelim.

![image](https://user-images.githubusercontent.com/101149671/180021110-3e7db7f2-89de-4eee-8ee2-0576a7952b4c.png)

### Şimdi discorda girip juno test tokeni alalım: https://discord.gg/4HxYGtaQ

```
$request + cüzdan adresi
```

# Şimdi tokenimizi oluşturalım:

* Token Name giriyoruz
* Token Symbol giriyoruz
* Initial Supply'ın sonuna 1-2 tane sıfır (0) ekliyoruz
* Sağ altın biraz üstünden Agreement kısmında tiki onaylıyoruz
* Confirm diyoruz.
* 2 kez cüzdan onayı veriyoruz.

![image](https://user-images.githubusercontent.com/101149671/180021850-ba831712-5d00-4a0b-b413-d6c927aba349.png)

# Şimdi Transaction details ekranı çıkacak karşınıza ve Contract Address'e tıklıyoruz ve Juno Blueprints sayfası açılacak.

* Bu arada keplr juno ağında alt kısma bakın tokeniniz gözükecek.

![image](https://user-images.githubusercontent.com/101149671/180022385-8940cfea-7af0-4bc7-8fbe-dce41c59c863.png)

# Daha sonra bu sayfaya giriyoruz: [Link](https://blueprints.juno.giansalex.dev/#/contracts/juno16gckhheyql9f85r9ydmazdccc0pnwxx5xxxrwltygtx3kxjg57ksamkpym) ve gerekli görevleri sıralıyorum alta.

* Yukarıda verdiğim linkten sağ üstten cüzdan bağlıyoruz.
* Alt kısımda Write kontrat kısmına tıklıyoruz
* Altta verdiğim kodu write kontrat kısmını silip benim kodu giriyoruz.

```
{
  "allow": {
    "contract": "juno1d3pnlc086evh7d277vak6tpz6gmvw6gr6plwxzf5n2tl9zdtwf7qrdsn44"
  }
}
```

### Daha sonra altta göstedğim görselde ki gibi, kendi kontrat adresimizi kopyalıyoruz.

![image](https://user-images.githubusercontent.com/101149671/180023931-6394e6b4-e813-4f25-9e8b-b0c821820fcc.png)

### Daha sonra kendi oluşturduğumuz tokenin kontrat adresi ile değiştiriyoruz.

* Değiştirdikten sonra Execute contrat (mavi buton, altında olur) butonuna tıklıyoruz.

![image](https://user-images.githubusercontent.com/101149671/180024177-6cab7dcb-fffa-440d-a2ea-96da7ac554de.png)

# Şimdi yapacaklarımızı çok basit bir dille anlatacağım 1-2 kez okuyalım lütfen.

* Altta ki kodu kopyalayın.

```
eyJjaGFubmVsIjoiY2hhbm5lbC03OSIsInJlbW90ZV9hZGRyZXNzIjoic2VpMXAwdDZha3M3dGpzdTB5OXNqaHNwNXQ1Z2t1bmtjODlheHg0Mnk3In0=
```

* https://www.utilities-online.info/base64 üzerine gidin.

* Altta ki görselde ki gibi sol tarafa yapıştırın
* Ortada Decode butonuna tıklayın.
* Sağda görselde ki gibi {"channel diye başlayan bir kod çıkacak, o kodun sonunda remote_address ve sei adresi yazar.
* O sei adresini kendi keplr cüzdanınızda ki sei adresi ile değiştirin. (çünkü benim adresim o)
* Değiştirdikten sonra kopyalayıp sol tarafa yapıştırın.
* İlk başta decode demiştik şimdi encode yapıyoruz.
* Şimdi size ait bir MSG oluştu, yukarıda paylaştığım komutun benzeri.

![image](https://user-images.githubusercontent.com/101149671/180026953-69d462fb-60fa-4b53-bea3-5247667a6e58.png)

![image](https://user-images.githubusercontent.com/101149671/180027683-e777f7c3-d731-4bf0-8f55-7fd0f3618b67.png)

# Şimdi başta token oluşturmuş ve kendi kontrat adresimize tıkladığımızda Juno Blueprints üzerinde bir site açılmıştı. (görselde ki gibi)

Sırasıyla:

* Sağ üstten cüzdanı bağlıyoruz aynı şekilde.
* Aşağıya gelip write kontrat diyoruz

![image](https://user-images.githubusercontent.com/101149671/180028129-dd7a2e81-c0af-49a4-a335-dc258971545d.png)

### Görselde ki gibi bir mesaj çıkacak, orayı siliyoruz ve görselin altında verdiğim kodu giriyoruz

![image](https://user-images.githubusercontent.com/101149671/180028662-fc6cbe64-3649-4bd1-977c-76b92fa5ea79.png)

```
{
  "send": {
    "contract": "juno16gckhheyql9f85r9ydmazdccc0pnwxx5xxxrwltygtx3kxjg57ksamkpym",
    "amount": "100000000",
    "msg": "eyJjaGFubmVsIjoiY2hhbm5lbC03OSIsInJlbW90ZV9hZGRyZXNzIjoic2VpMXAwdDZha3M3dGpzdTB5OXNqaHNwNXQ1Z2t1bmtjODlheHg0Mnk3In0="
  }
}
```

### Daha sonra MSG kısmında resimde gösterdiğim gibi tırnak işaretleri içersinde olan (") kodu siliyoruz.

* Yukarıda kodu çevirmiştik kendi sei adresimizi girmiştik hatırlarsınız onu kopyalıyoruz.
* MSG kısmında sildiğimiz tırnak işaretleri arasına yapıştırıp execute kontrat diyoruz.
* Bunu yaptıktan sonra cüzdanınızdan 1 tane kendı oluşturduğunuz token gidecek.

![image](https://user-images.githubusercontent.com/101149671/180028984-96c97bdc-9fe8-4dbb-bdcf-cc3b3156df13.png)

# Daha sonra bu işlemi tamamladıktan sonra sayfayı yenileyin.

* En altta bir TX oluşacak ona tıklıyoruz.
* Tıkladıktan sonra açılan sayfada Success yazısını gör

![image](https://user-images.githubusercontent.com/101149671/180030336-0363a981-02a3-42da-8f98-d86c735e9a7e.png)

# İşlem sonunda https://sei.explorers.guru/validators giriyoruz ve sırasıyla:

* Validatorumuze tıklıyoruz
* En altta kendi cüzdanımızı buluyoruz ve tıklıyoruz
* Daha sonra böyle bir görselle karşılaşacaksınız, işlem tamam buraya kadar.

![image](https://user-images.githubusercontent.com/101149671/180138007-7ce5d9ab-f9b4-428a-98c2-8426335da36b.png)

### Daha sonra bunu altta ki paylaşacağım görevler kısmında bu cw20 tokeni kullanarakta ek işlem yapabilirsiniz.

https://github.com/ruesandora/sei-atlantic-1/blob/main/seinami-testnet-mission.md


# TOKEN OLUŞTURMAK İSTEMEUYENLERE KOLAY YOL:

### Keplr ayarlardan IBC Transferi açıyoruz.

![image](https://user-images.githubusercontent.com/101149671/180145089-86f0ddd2-e146-4ef7-a895-a079c98d7f69.png)

### Juno test ağına gelip en alttan IBC transfer diyoruz:

Sırasıyla:

* Select chain
* New IBC Transfer Channel
* Select channel'dan en altta sei seçiyoruz.
* channel ID channel-35 yazıyoruz.
* save diyoruz
* daha sonra sei testnet cüzdan adresimizi veya keplrdaki adresımızı kopyalıyoruz (explorerden alın)
* adres kısmına (Recipient) giriyoruz.
* Memo boş kalacak
* daha sonra token oluşturduysanız tokeninizi veya juno seçiyoruz.
* Sırasıyla submit ve approve diyerek 3-5dk geçmesini bekliyoruz.

### Görselde ki gibi explorerde gözükecek işlem tamamlanınca: biraz uzun sürebilir

![image](https://user-images.githubusercontent.com/101149671/180145951-7bc4755a-ee5f-44eb-a253-e4ebc7ac25a5.png)


# Hesaplar:

[<img src="https://cdn-icons-png.flaticon.com/512/733/733579.png" width="16px"> Twitter   ](https://twitter.com/Ruesandora0) 

[<img src="https://cdn-icons-png.flaticon.com/512/1336/1336494.png" width="16px"> Forum   ](https://forum.rues.info/index.php)

[<img src="https://cdn-icons-png.flaticon.com/512/2111/2111646.png" width="16px"> Telegram Announcement   ](https://t.me/RuesAnnouncement)

[<img src="https://cdn-icons-png.flaticon.com/512/2111/2111646.png" width="16px"> Telegram Chat   ](https://t.me/+-l6GpqiNOxFiMTVk)

[Discord](https://discord.gg/ruescommunity)


