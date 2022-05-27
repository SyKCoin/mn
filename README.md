# MasternodeSetup

### Required:

1. sykcoin for Collateral <br>
(You can buy syk from exchange for collateral) <br>
***https://www.exbitron.com/trading/sykbtc <br>***
***https://www.exbitron.com/trading/sykusdt <br>***

2. Download your Local Wallet: https://github.com/SyKCoin/syk/releases



3. You will need also VPS with Ubuntu 16.04 or 18.04 or 20.04

**VPS WALLET:**

1. After you longin on your VPS , with this command you will download masternode-installer.   
`wget https://raw.githubusercontent.com/SykCoin/mn-setup/master/mnsetup.sh`  


2. With this command you will make masternode-install-ubuntu-16.04.sh executable.  
`sudo chmod +x mnsetup.sh` <br>


3. Now install your masternode.  
`./mnsetup.sh`



**LOCAL WALLET:**

Send the collateral
Open your wallet and wait until your wallet has downloaded the blockchain.

Go to “Tools”.
Click “Debug console”.
This is the console where you will execute all commands.

Create a new masternode private key.

```
createmasternodekey
```

Example output

7R76KexRJ9iqStPC5V3VkLc4GtGhEoLqdmabeuX6zVnCujhFqec

Show your collateral address.
```
getaccountaddress "MN1"
```

Example output

ShRoHD68QQJLE8JFyB4Vt9gkghWowwQYfV
```
Transfer the required amount of coins to the “collateral address” that you created using the command “getaccountaddress "MN1"”.
```
Wait until the transaction has the required masternode confirmations.

Go to “Tools”.
Click “Debug console”.
Enter the following command.
```
getmasternodeoutputs
```
```
Example output


[
  {
    "txhash": "506a242ccbfd2555bcd9cff5f4041752c911f39cb2905acc83ccfe0cf8808df9",
    "outputidx": 1
  }
]
```

Modify the following line in your masternode.conf file and paste it into:
```
MN1 VPSIP:4468 7R76KexRJ9iqStPC5V3VkLc4GtGhEoLqdmabeuX6zVnCujhFqec 506a242ccbfd2555bcd9cff5f4041752c911f39cb2905acc83ccfe0cf8808df9 1
```
MN1 - Alias for your masternode.

VPSIP- External IP address of your VPS.

4468 - The port for syk

7R76KexRJ9iqStPC5V3VkLc4GtGhEoLqdmabeuX6zVnCujhFqec - Masternode private key from the command “createmasternodekey”.

506a242ccbfd2555bcd9cff5f4041752c911f39cb2905acc83ccfe0cf8808df9 - Value “txhash” from the command “getmasternodeoutputs”.

1 - Value “outputidx” from the command “getmasternodeoutputs”.


Save the file and close.

Close your wallet.

Restart your wallet! 
On Masternode tab in your wallet - Start the masternode! 

