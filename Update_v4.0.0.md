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

# Install New Binary
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
# Check Version

Önce doğru binary'nin kurulup kurulmadığını kontrol edin
```
$HOME/go/bin/dymd version
$HOME/go/bin/dymd version --long | grep commit
```

# Make Cosmovisor Directory and Copy Binary
```
mkdir -p $HOME/.dymension/cosmovisor/upgrades/v5/bin
cp $HOME/go/bin/dymd $HOME/.dymension/cosmovisor/upgrades/v5/bin
```

### Fast Block Time

- to enable fast block time we need to update `timeout_propose="1.8s"`  and `timeout_commit="500ms"` in `config.toml` . 
In case your dymension home directory is `$HOME/.dymension` you can use the following snippest:

```
sed -i -e 's/^timeout_propose *=.*/timeout_propose = "1.8s"/' \
       -e 's/^timeout_commit *=.*/timeout_commit = "500ms"/' \
       $HOME/.dymension/config/config.toml
```
