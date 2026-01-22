IMPORTANT SECURITY PATCH: Dymension v4.0.2


## GÜNCELLEME ADIMLARI (Cosmovisor)

### 1. Servisi Durdurun
```bash
sudo systemctl stop dymension
```

### 2. v4.0.2 Binary'sini İndirin
```bash
cd $HOME
wget https://github.com/dymensionxyz/dymension/releases/download/v4.0.2/dymension_linux_amd64.tar.gz
```

### 3. Binary'yi Çıkartın
```bash
tar -xzf dymension_linux_amd64.tar.gz
```

### 4. Mevcut Binary'nin Yedeğini Alın (İsteğe Bağlı)
```bash
cp $HOME/.dymension/cosmovisor/upgrades/v5/bin/dymd $HOME/.dymension/cosmovisor/upgrades/v5/bin/dymd.backup
```

### 5. Yeni Binary'yi Güncelleyin
```bash
cp dymd $HOME/.dymension/cosmovisor/upgrades/v5/bin/dymd
chmod +x $HOME/.dymension/cosmovisor/upgrades/v5/bin/dymd


cp dymd $HOME/.dymension/cosmovisor/current/bin/dymd
chmod +x $HOME/.dymension/cosmovisor/current/bin/dymd
```

### 6. Versiyonu Kontrol Edin
```bash
$HOME/.dymension/cosmovisor/current/bin/dymd version
# Çıktı: v4.0.2 olmalı
```

### 7. Servisi Başlatın
```bash
sudo systemctl start dymension
```

### 8. Logları Kontrol Edin
```bash
sudo journalctl -u dymension -f
```

Node'un düzgün başladığını ve blokları işlemeye devam ettiğini görmelisiniz.
