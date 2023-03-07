First of all you should backup your validator priv_key:
```
cp $HOME/.nolus/data/priv_validator_state.json $HOME/.nolus/priv_validator_state.json.backup
```
After that cleand your data base:
```
nolusd tendermint unsafe-reset-all --home $HOME/.nolus --keep-addr-book 
```
Download data folder & wasm folder:
```
wget http://135.181.88.141:8000/nolus.tar.gz
wget http://135.181.88.141:8011/wasm.tar.gz
```
Unzip them:
```
tar -C $HOME/ -zxvf nolus.tar.gz
tar -C $HOME/ -zxvf wasm.tar.gz
```
Move them to the correct folder:
```
mv /root/nolus/.nolus/data /root/.nolus/
mv /root/nolus/.nolus/wasm /root/.nolus/
```
Delete archives:
```
rm -rf wasm.tar.gz
rm -rf nolus.tar.gz
```
Restore your validator key:
```
mv $HOME/.nolus/priv_validator_state.json.backup $HOME/.nolus/data/priv_validator_state.json
```

You are ready to go now! Start your node ;-)
