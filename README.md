<h1 align="center">Manta Network Trusted Setup

  ## Güvenilir kurulumların açıklaması ve Manta Network'te oynadıkları rol için [buraya](https://docs.manta.network/docs/concepts/TrustedSetup) bakın . Katılım talimatları için okumaya devam edin.
  
 ![image](https://docs.manta.network/img/guides/trusted-setup-stages.svg)

## Manta Network için minimum kurulum gereksinimleri belirtilmemiştir. Aşağıdaki rehberden digital ocean veya google cloud ile en düşük sunucuları kiralayıp kurabilirsiniz.

 
  
  # 1. adımda Manta kurulumu otomatik script ile kurulumunu paylaşalım sorun yaşarsanız manuel kurulum kısmına geçebilirsiniz.
  
  
  ## Root yetkisi alalım.
  ```
  sudo su
  cd
  ```
  
 ## Sunucumuzu güncelleyelim
  
  ```
 sudo apt update && sudo apt upgrade -y
  ```
  
 ## Ardından bu komu ile çalıştırıyoruz.
  
 ```
curl --proto '=https' --tlsv1.2 -sSf https://raw.githubusercontent.com/Manta-Network/manta-rs/main/tools/install.sh | sh
 ```
 
  ## Kurulum tamamlandıktan sonra
   ```
source ~/.profile
 ```
 ## İşlemler bu kadar kurulumu tamamladık. Şimdi kayıt işlemlerine devam edeceğiz.
   ```
manta-trusted-setup register
 ```
  

  
  
  
 ## Node'u kontrol etmek için [bu siteye](https://ait.aptos-node.net/) gidelim. Görselde gördüğünüz gibi Validator Node'umuzun sunucu IP'sini yazalım ve API port'unu 80 olarak girelim.
  
  ![image](https://user-images.githubusercontent.com/101462877/185793794-020738f2-cd22-4419-9e5b-83fa5269974d.png)
  
Bu şekilde bir görüntü varsa başarılı bir şekilde kurmuşuz demektir.
  
 ## Node'umuzu başarıyla kurduk, şimdi Node'umuzu sisteme kayıt edeceğiz. Bunun için tekrar [AIT-3 için Kayıt Sayfası](https://aptoslabs.com/it3)'na gidiyoruz.
  
  ![image](https://user-images.githubusercontent.com/101462877/185748205-5209eadb-1c50-44de-889f-558406bf13e4.png)

  Şuan için henüz anketi doldurmadığım için bu kısımda buton bulunmuyor, fakat siz anketi doldurduktan sonra buradaki buton aktif olacaktır.
  
  ## Bu kısımda doldurmanız gereken yerler için verileri nereden alacağınızı anlatacağım. Boşlukları tek tek emin olarak doldurun, hatalı kayıt yapmak istemezsiniz.
  
  Kurduğumuz validator node'unda aşağıdaki komutu girelim:
  ```
cat ~/$WORKSPACE/keys/public-keys.yaml
  ```
  Ardından karşımıza çıkan dosyadaki veriler ile kayıt formunu dolduralım. Hangi boşluk için hangi veriyi girmeniz gerektiğini aşağıya bırakıyorum. Ayrıca, API PORT'u `8080` olarak geliyor, onu `80` olarak değiştirin.
  
  ![image](https://user-images.githubusercontent.com/101462877/185748364-40ef482b-a3e5-4825-a7c2-19b3fbe7478f.png)
  
  - `OWNER KEY`: Petra cüzdanınızın `Public Key`'i. Nasıl erişebileceğinizi aşağıdaki ss'lerde gösterdim.
  ![image](https://user-images.githubusercontent.com/101462877/185748436-3837fcba-b981-4f31-b0c5-18875d782163.png) ![image](https://user-images.githubusercontent.com/101462877/185748440-b9ac017c-ff45-4817-82d6-883a21b527b0.png)
- `CONSENSUS KEY`: Yukarıdaki komutla terminalde gördüğümüz consensus_public_key
- `CONSENSUS POP`: Yukarıdaki komutla terminalde gördüğümüz consensus_proof_of_possession 
- `ACCOUNT KEY`: Yukarıdaki komutla terminalde gördüğümüz account_public_key 
- `VALIDATOR NETWORK KEY`: Yukarıdaki komutla terminalde gördüğümüz validator_network_public_key
  
  
## Bu verileri doğru bir şekilde girdiğimize emin olduktan sonra `Validate Node` butonuna tıklayalım. Ardından eğer node'unuz Aptos takımı tarafından seçilirse mail alacaksınız. Bu yüzden süreç boyunca mail'lerinizi sık sık kontrol etmelisiniz.
  
  
  # Son adımda kimlik doğrulaması yapmamız gerekiyor, bunun için aşağıdaki görselde gördüğünüz butona tıklıyoruz ve bizi yönlendirdiği sayfada kimliğimizi doğruluyoruz.
  ![image](https://user-images.githubusercontent.com/101462877/185860116-f76ff713-1082-4636-90d2-da430381a0e9.png)


# Kurulum bu kadardı, validatör olarak kullanabileceğiniz bazı komutları aşağıya bırakıyorum. Ayrıca optional olarak Fullnode yüklemek isterseniz [Aptos Fullnode Kurulumu](https://github.com/thisislexar/Aptos-AIT-3/blob/main/fullnode.md)'na göz atabilirsiniz. 


# Logları kontrol etmek için kod:

```
docker logs -f testnet-validator-1 --tail 50
```

# Senkronize durumunu kontrol etmek için kod:

```
curl 127.0.0.1:9101/metrics 2> /dev/null | grep aptos_state_sync_version | grep type
```
  
# Node'u tekrar başlatmak için kod:
```
docker restart testnet-validator-1
```  
  

