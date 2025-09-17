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

## Sunucu Kiralama : 

<img width="1192" height="725" alt="image" src="https://github.com/user-attachments/assets/ed335e12-e934-473e-a127-65465ec74140" />


- Port Ekleme : 
<img width="347" height="472" alt="image" src="https://github.com/user-attachments/assets/db312479-cb3b-4784-a36c-d113bb479537" />

<img width="964" height="844" alt="image" src="https://github.com/user-attachments/assets/ce331059-714b-444b-8151-5fc4e62afc49" />


- Save'e basıp onaylayın.

- Template : Ubuntu 22.04 VM
- 8 CPU Üstü Ryzen Serverlara Bakabilirsiniz
- 100 Mbps üstü indirme hızı olan serverlar +
- Minimum Container alanını 100+ ayarla

- Sunucunu seçip Rent'e basıp kiralayabilirsiniz.

![image](https://github.com/user-attachments/assets/38947105-2719-420d-9d6e-8a87b718d10b)

- Connect'e basın.

<img width="1365" height="499" alt="image" src="https://github.com/user-attachments/assets/80f35785-47bb-4980-a28b-9de0d1a9c0f2" />

- Jupyter Terminal altındaki butona basıp panele erişin. 


## Project Social Media : 
- Twitter : https://x.com/PluralisHQ


## Server Update : 

```bash
cd
```

```bash
sudo apt update -y && sudo apt upgrade -y
```
## Download Packages :

```bash
sudo apt install htop ca-certificates zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev tmux iptables curl nvme-cli git wget make jq libleveldb-dev build-essential pkg-config ncdu tar clang bsdmainutils lsb-release libssl-dev libreadline-dev libffi-dev jq gcc screen file unzip lz4 -y
```

## Screen ; 

```bash
screen -S pluralis
```

```bash
cd
```

## Dosyaları İndirelim 

```bash
git clone https://github.com/PluralisResearch/node0
cd node0
```

## Conda

```bash
conda create -n node0 python=3.11
conda activate node0
```

<img width="633" height="899" alt="image" src="https://github.com/user-attachments/assets/6749ea02-4352-4b18-b714-89a1f905a208" />

- y yazıp enterleyin.

## Node0
```bash
pip install .
```

<img width="741" height="482" alt="image" src="https://github.com/user-attachments/assets/e2ab2880-8fcb-413a-964e-1ef94de43b53" />


## Başlangıç Scriptini Oluşturalım

```bash
python3 generate_script.py --host_port 49200 --announce_port <A_Port> --token <HF_token> --email <email_address>
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

<img width="668" height="413" alt="image" src="https://github.com/user-attachments/assets/f6badb16-9f7c-4da2-b1d5-a4ed1bf542a7" />


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
- Sunucuya geri girip CTRL C ile durdurun. 

