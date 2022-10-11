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
  

  
  
  
 ## Yukarıdaki kodu girdikten sonra aşağıdaki gibi bir ekran sizi karşılayacak. Buraya twitter adresinizi başında "@" işareti olmadan giriyoruz. Sonrasında mail adresimizi girip enter basıyoruz.
  
  ![image](https://docs.manta.network/assets/images/ts_guide_register-a29ac5c407de7d05e590fefa7c93ae5e.png)
  
### Bu şekilde bir görünüm elde ettiyseniz. Başarılı şekilde kayıt işlemini tamamlamışsınız demektir. 

#NOT: Yukarıdaki adımlar ile çalıştıramazsanız bu kısmı kullanabilirsiniz. 

 # 2. Manuel Kurulum
  
  
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
sudo apt install pkg-config build-essential libssl-dev curl jq
 ```
 ```
curl https://sh.rustup.rs -sSf | sh -s -- -y
 ```
 ```
source $HOME/.cargo/env
 ```
 ```
git clone https://github.com/Manta-Network/manta-rs.git
 ```

 ```
cd manta-rs
 ``` 
 ```
cargo run --release --package manta-trusted-setup --all-features --bin groth16_phase2_client register
 ``` 
  
 ## İşlemler bu kadar kurulumu tamamladık. Şimdi kayıt işlemlerine devam edeceğiz.
   ```
manta-trusted-setup register
 ```
 ## Yukarıdaki kodu girdikten sonra aşağıdaki gibi bir ekran sizi karşılayacak. Buraya twitter adresinizi başında "@" işareti olmadan giriyoruz. Sonrasında mail adresimizi girip enter basıyoruz.
  
  ![image](https://docs.manta.network/assets/images/ts_guide_register-a29ac5c407de7d05e590fefa7c93ae5e.png)
  
### Bu şekilde bir görünüm elde ettiyseniz. Başarılı şekilde kayıt işlemini tamamlamışsınız demektir. 

# KAYIT FORMU;
  [Buradan](https://mantanetwork.typeform.com/TrustedSetup) formuna ulaşabilirsiniz. Sizden istenilen bilgileri oradan doldurup, kayı işlemini tamamlayabilirsiniz.
  
  Formda sizden KMA adresinizi vermenizi isteyecek, bunun için polkadotjs cüzdana sahip olmanız gerekiyor. Kurulumunu bilmiyorsanız. [Buradan](https://www.pusulafinans.com/polkadot-cuzdan-nasil-olusturulur/) makalemize göz atabilirsiniz.
  Kurulumu yaptıktan sonra; Aşağıdaki görselleri takip ederek, KMA adresinize ulaşabilirsiniz.
  ![image](https://user-images.githubusercontent.com/111747226/195038643-45d453c9-20ff-49f6-b7a5-0d0b7f69577d.png)   ![image](https://user-images.githubusercontent.com/111747226/195038903-d12d58b5-16d6-4516-ac11-07457b8bc42c.png)

  
## Kayıt işlemleri sonrasında "contribute" aktif hale geldiğinde güncellemelerini yayınlarız.
