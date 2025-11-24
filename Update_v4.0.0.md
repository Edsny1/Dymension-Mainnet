# Mevcut Go'yu kaldır
```
sudo rm -rf /usr/local/go
```

# Go 1.24.6'yı indir ve kur
```
cd $HOME
```
```
wget https://golang.org/dl/go1.24.6.linux-amd64.tar.gz
```
```
sudo tar -C /usr/local -xzf go1.24.6.linux-amd64.tar.gz
```
```
rm go1.24.6.linux-amd64.tar.gz
```

# PATH'i güncelle
```
source $HOME/.bash_profile
```
# Versiyonu kontrol et
```
go version
```

# Yeni Binary Yükle
```
cd dymension
```
```
git pull
```
```
git checkout v4.0.0
```
```
make install
```
# Version Kontrol

Önce doğru binary'nin kurulup kurulmadığını kontrol edin
```
$HOME/go/bin/dymd version
$HOME/go/bin/dymd version --long | grep commit
```
# Should be commit 5bbee2a0c74474bc159bd28bd2f70782e2352dcd

# Cosmovisor Dizinini Oluşturun ve İkili Dosyayı Kopyalayın
```
mkdir -p $HOME/.dymension/cosmovisor/upgrades/v5/bin
cp $HOME/go/bin/dymd $HOME/.dymension/cosmovisor/upgrades/v5/bin
```

### Fast Block Time

- Hızlı blok süresini etkinleştirmek için `config.toml` dosyasında `timeout_propose=“1.8s”`  ve `timeout_commit=“500ms”` değerlerini güncellememiz gerekir.
Dymension ana dizininiz `$HOME/.dymension` ise, aşağıdaki snippet'i kullanabilirsiniz:

```
sed -i -e 's/^timeout_propose *=.*/timeout_propose = "1.8s"/' \
       -e 's/^timeout_commit *=.*/timeout_commit = "500ms"/' \
       $HOME/.dymension/config/config.toml
```

