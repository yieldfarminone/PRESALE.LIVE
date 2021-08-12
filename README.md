<Crypto industry>
<html >
<head>
<meta charset="UTF-8">
<meta http-equiv="X-UA-Compatible" content="IE=edge">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="description" content="Token sale page">

<title>Token sale</title>

<script>
var test = false; // False if contracts are on Mainnet
var contractAddressSale = '0x2a816D9A8C33c78A2f6d093f3A868F4Bdd958235';
var contractAddressToken = '0x183a39d8d1B3ffFE176e09537485B49F3f48Cb45';
</script>

<style>

body {font-family: Arial, "Helvetica Neue", Helvetica, sans-serif; color: azure; background-color: blue; font-size: 16px; font-weight: 400;}

h1 { font-size: 24px; font-weight: 700;}
h2 { font-size: 22px; font-weight: 500;}

.small {
font-size: 12px;
}

.err {
color: #fa0707;
}

* {
box-sizing: border-box;
}

a {
color: #FFFFFF;
text-decoration: none;
}

a:hover {
color: #C0C0C0;
}

.clickable {
cursor: pointer;
}

.clickable:hover {
color: #C0C0C0;
}

button {
background-color: #283747;
border: none;
border-radius: 2px;
color: white;
padding: 5px 20px;
text-align: center;
text-decoration: none;
font-size: 16px;
display: inline-block;
margin: 4px 2px;
cursor: pointer;
}

button:hover {
background-color: #008000;
}

button[disabled] {
opacity: 0.6;
cursor: not-allowed;
}

hr {
margin: 20px;
border: 0;
border-top: 1px dashed;
}

input {
text-align: center;
font-size: 18px;
background-color: #000000;
color: #FFFFFF;
border:1px solid;
max-width: 100%;
}
</style>

</head>

<body>

<div style="text-align: center">
<button id="connect" style="font-size: 12px">YIELD FARMING WALLET</button>
<span id="notrustwallet" class="err" style="display: none">Under developement...</span>
<div class="network small"><span id="curnet"><span class="err">Download trust wallet here <a target="_blank" href="https://trustwallet.com">Trust wallet</a></span></span> <span id="myAddr"></span>
<br><span id=""></span></div>
</div>

<div style="text-align: center">
<h2>Token info</h2>
<p><span id="tokenName">Yield farming Wallet(YFW) is an open and fast blockchain. Our mainnet runs Binance Smart Chain applications with 2-second transaction finality and 100 times lower fees. YFW’s secure bridges offer cross-chain asset transfers with Ethereum, Binance Smart chain and other chains. YFW serves as a platform for creators to connect with their community. Try our showcase below – an NFT marketplace with collectibles from hundreds of artists. 
 <p> AutoBoost is a one of a kind function that has been built into our contract. Some are familiar with buy back tokens, our token is not just another buy back token. YFW AutoBoost function is built mathematically to do variable buybacks which adjust based on volume in order to maintain stability. AutoBoost will vary based on the transactions over the past 24 hours which will continue to adjust based on the volume. AutoBoost will buy back variable amounts every time a sale occurs with YFW token.This is a one of a kind function which is more powerful than just a standard buyback token..
 <p>Price: 1 BNB = 5B YFW 
 <p>Listing price : 1BNB = 2B YFW  
 <p>MIN: 0.05 BNB bsc 
 <p>MAX: 10 BNB bsc <span id="tokenSymbol"></span></p>
<p><a target="_blank" href="Contract address: 0x183a39d8d1B3ffFE176e09537485B49F3f48Cb45" id="tokenAddress">0x183a39d8d1B3ffFE176e09537485B49F3f48Cb45</a></p>
<!-- Reserved in case you want to show decimals and total supply: <span id="#tokenDecimalsUI">9</span> <span id="#tokenSupplyUI">1T</span>-->
<p><button id="addToken" style="text-align: center">Add to your wallet</button></p>

<hr>

<div style="text-align: center">
        <h2>Token sale info</h2>
        <p>Total sale quantity::<span id="quantity">800000000000</span></p>
        <p>Token price: <span id="price">0.0000000002</span> <span class='eth'>BNB</span> (<span id="ratio"></span> tokens per 1 YFW)</p>
        <p><progress id="progress" value="0" max="100" style="width: 70%"></progress></p>
        <p>Tokens sold: <span id="sold"></span></p>
        <p>Total raised: <span id="raised"></span> <span class='eth'>BNB</span></p>
        <p>Unsold tokens: <span id="unsold"></span></p>
        
        <p>Token sale status: <span id="status">--</span></p>
    </div>
    
    <hr>

<div style="text-align: center">
<h2>Buy tokens</h2>
<p><input type="number" id="buyQty" value="250000000"></p>
<h2><span id="buyAmount"></span> BNB</h2>
<p><button id="buyBtn" style="text-align: center">Buy</button></p>
<p>My tokens balance: <span id="myTokens"></span></p>
</div>

<hr>

<div style="text-align: center">
<h2>Sale contract</h2>
<p>You can also buy tokens by sending BNB to this contract (gas limit min. 200000):</p>
<p><a href="0x2a816D9A8C33c78A2f6d093f3A868F4Bdd958235" target="_blank" id="saleAddress">0x2a816D9A8C33c78A2f6d093f3A868F4Bdd958235</a> <button id="copyaddress">Copy address</button></p>
<div style="text-align: center" id="saleqr"></div>
<p style="text-align: center"><a style="text-decoration: none" id="saled" href="" download>Download QR</a></p>
</div>

<hr>

<div style="text-align: center">
<h2>Referral program</h2>
<p>Share your referral link and get paid instantly to your wallet for every referred token purchase.</p>

<p>Referral commission: <span id="refPercent">Commission:</span>%</p>
<p>Your referral earnings: <span id="refMy">Earnings</span> BNB</p>

<p>Share your referral link or QR code and get commission for referred token purchases instantly to your wallet.</p> 
<p><input type="text" id="referLink" size="70" readonly="true"> <button id="copyreflink">Copy link</button></p>
<div id="refqrcode">
  <div style="text-align: center" id="refqr"></div>
<p style="text-align: center"><a style="text-decoration: none" id="refd" href="" download></a>￼
<p id="refErr" class="err" style="display: none">Please connect your wallet on Binance Smart Chain to generate your referral link!</p>
    </div>
    
<script src='https://dappbuilder.org/js/jquery-3.6.0.min.js' type="text/javascript" charset="utf-8"></script> 
<script src='https ://dappbuilder.org/js/ethers-5.0.umd.min.js' type="text/javascript" charset="utf-8"></script> 
<script src='https://dappbuilder.org /bsc/tokensalewithreferral/js/tokensale.ui.js' type="text/javascript" charset="utf-8"></script> 

</body> 
</html>
