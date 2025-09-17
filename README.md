# Pluralis Research Node

![mmDxyPqC_400x400](https://github.com/user-attachments/assets/92d1b63c-cb2f-4240-916e-043d943888b0)


| X        | Minimum              |
|------------------|----------------------------|
| **CPU**          | 8++ |
| **RAM**          | 32++ GB                    |
| **Disk**      | 100 GB+ NVME GB SDD                   |
| **GPU**      | 16GB Vram++                   |
| **Internet Speed**      | 100 Mbps (1 Gbps+ recommended) |


#### Vast Kayıt : 

| Server Sağlayıcısı        | Kayıt Link              | Neden |
|------------------|----------------------------|----------------------------|
| **VAST GPU**          | [Link](https://cloud.vast.ai/?ref_id=228932) | İstediğimiz Sunucular / Kripto Ödeme |

- https://cloud.vast.ai/billing/ 'den Kripto yada Kart ile bakiye ekleyebilirsiniz.

## Bağlanmak için SSH Key Ayarlama : 

- Wsl Kullanıyorsanız CMD / Powershell - Mac'de Terminal Açın
```bash
ssh-keygen
```

![image](https://github.com/user-attachments/assets/ec8c9bac-3397-40da-ac0d-70bcb985a360)

- 3 Soru Yöneltiyor ; 
```bash
Enter file in which to save the key (/home/codespace/.ssh/id_rsa):
Enter passphrase (empty for no passphrase):
Enter same passphrase again: 
```
- İsim değiştirmek isterseniz (/home/codespace/.ssh/id_rsa): 'den sonra isim yazıp enter'e basın.
- Şifre'ye enter sonrakinede enter diyip geçebilirsiniz.

![image](https://github.com/user-attachments/assets/6e944f73-120c-44e1-9d29-d220352d9594)

- \home\kullanici\.ssh\id_rsa.pub 'ı açın. İçindekini kopyalayın.

-  https://cloud.vast.ai/manage-keys/ - + New'den kayıt edin keyinizi.

![image](https://github.com/user-attachments/assets/3a15ce26-341b-4ca9-8a7a-47d1cd3b927c)

## Sunucu Kiralama : 

![image](https://github.com/user-attachments/assets/5fbb7dcd-ab59-4d63-9bc4-a3b1ec89b2a5)

- Port Ekleme : 

<img width="348" height="320" alt="image" src="https://github.com/user-attachments/assets/cf51163f-d83b-4ce5-8b9d-8ca9b434095d" />

<img width="970" height="730" alt="image" src="https://github.com/user-attachments/assets/2b8db503-38ed-40a3-952a-fbef1242aba4" />


- Save'e basıp onaylayın.

- Template : Ubuntu 22.04 VM
- 8 CPU Üstü Ryzen Serverlara Bakabilirsiniz
- 100 Mbps üstü indirme hızı olan serverlar +
- Minimum Container alanını 100+ ayarla

- Sunucunu seçip Rent'e basıp kiralayabilirsiniz.

## Sunucuya Giriş ; 

![image](https://github.com/user-attachments/assets/38947105-2719-420d-9d6e-8a87b718d10b)

- Connect'e basın.

![image](https://github.com/user-attachments/assets/cbba0796-733e-4b2b-9c7f-219cc1c69d55)

- Bağlantı için verdiği komutu CMD / Termius Terminale yapıştırıp enterleyin.
- Size bağlantı sorusu sorar ise yes yazıp enterleyin.

![image](https://github.com/user-attachments/assets/e3a37172-f583-4bfe-b5b0-fba98c42b0de)

## Project Social Media : 
- Twitter : https://x.com/PluralisHQ


## Server Update : 

```bash
sudo apt update -y && sudo apt upgrade -y
```
## Download Packages :

```bash
sudo apt install htop ca-certificates zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev tmux iptables curl nvme-cli git wget make jq libleveldb-dev build-essential pkg-config ncdu tar clang bsdmainutils lsb-release libssl-dev libreadline-dev libffi-dev jq gcc screen file unzip lz4 -y
```

## Docker İle Kurulum ; 

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io -y
docker version
```

## Docker Compose : 

```bash
VER=$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep tag_name | cut -d '"' -f 4)
curl -L "https://github.com/docker/compose/releases/download/$VER/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
chmod +x /usr/local/bin/docker-compose
docker-compose --version
```

## Docker User

```bash
sudo groupadd docker
sudo usermod -aG docker $USER
```

## Dosyaları İndirelim 

```bash
git clone https://github.com/PluralisResearch/node0
cd node0
```

## Buildliyelim

```bash
docker build . -t pluralis_node0
```

## Başlangıç Scriptini Oluşturalım

```bash
python3 generate_script.py --use_docker --host_port 49200 --announce_port <A_Port> --token <HF_token> --email <email_address>
```

- HF token : Huggingface'den aldığınız token / key.
- Email : Mail Adresiniz.

## HugginFace Token Almak İçin  ; 

#### Hesap Oluştur : https://huggingface.co/

![image](https://github.com/user-attachments/assets/62af4936-bcd6-4f3b-8f92-4c34cfb0e388)


#### Key / Token Alıyoruz ; 

- Link : https://huggingface.co/settings/tokens/new?tokenType=write

<img width="917" height="384" alt="image" src="https://github.com/user-attachments/assets/9a416825-da62-4c43-b66e-7df36d786af7" />

## Ann Port Nasıl Alınır ? 

- https://cloud.vast.ai/instances/ - girdik sunucumuzun ip adresinin üstüne tıkladık.

<img width="1180" height="279" alt="image" src="https://github.com/user-attachments/assets/5ff8b92a-6303-4881-8b40-59e6a6a44e08" />

-  sunucuip:misal25ilebaslayanport -> 49200/tcp 'e yönlendiriyor. Peer bağlatımızı böyle yapmalıyız.

<img width="327" height="480" alt="image" src="https://github.com/user-attachments/assets/c9e4aa26-f8f2-4662-91a3-06519de3dd0e" />




## Örnek : 

<img width="1251" height="343" alt="image" src="https://github.com/user-attachments/assets/d8bd8286-3fb0-4d04-ae76-924ec8064ea9" />

- Sorduğu soruya "n" yazıp enterliyoruz.
- File start_server.sh is generated. Run ./start_server.sh to join the experiment. yazısı çıkacak.


## Başlatalım : 
```bash
./start_server.sh
```
<img width="398" height="105" alt="image" src="https://github.com/user-attachments/assets/ab6e2f6d-74d9-41a0-a780-9105d9ad860b" />

## Loglar ; 
```bash
tail -f run.out
```

<img width="1305" height="231" alt="image" src="https://github.com/user-attachments/assets/d6b6da06-2a0e-4817-ba22-9a353142a4ea" />

## Çalıştığını Doğrulama ; 

- "Eğitimi Doğrula

Sunucunun diğer eşleri (peers) bulup eğitime katılması birkaç dakika sürebilir. Süreci takip etmek için eğitim loglarını (logs/server.log) veya stdout çıktısını kontrol edin. Kodunuzu Docker içinde çalıştırıyorsanız, stdout çıktısı run.out dosyasında kaydedilir.

Başlangıçta, yetkilendirmenin tamamlandığını ve yeni parametrelerin bir eşten (peer) indirildiğini göreceksiniz:"

- Başlangıç Logları ; 

```bash
INFO:node0.security.authorization: Access for user username has been granted until 2025-04-15 12:59:12.613600+00:00 UTC
INFO:node0.security.authorization: Authorization completed
 
 ...

INFO:hivemind.averaging.averager: Downloading parameters from peer <...>
INFO:hivemind.averaging.averager: Finished downloading state in 0.309s from <...>
```

- Sonraki Loglar ; 

```bash
INFO:hivemind.moe.server.runtime: Processed 51 batches in last 60 seconds:
INFO:hivemind.moe.server.runtime: body2.0.919_backward: 27 batches (100.62 batches/s), 108 examples (402.50 examples/s), avg batch size 4.00
INFO:hivemind.moe.server.runtime: body2.0.919_forward: 24 batches (382.51 batches/s), 96 examples (1530.02 examples/s), avg batch size 4.00
```
## Manuel Erişiminiz Yok İse Docker VM'den Dosya Çekme 

- Node0 Dizininde olduğunuzdan emin olun. Değilseniz girin.

```bash
cd node0
```

- Http server başlatalım.

```bash
python3 -m http.server 8080
```

- Kendi tarayıcınız üzerinden http://localhost:8080/'e girin.

<img width="581" height="526" alt="image" src="https://github.com/user-attachments/assets/457e9408-4a0e-43f4-81b2-306059a75b58" />

- private.key'in üstüne tıklayın indirin. 
- Sunucuya geri girip CTRL C ile http serveri durdurun. 
