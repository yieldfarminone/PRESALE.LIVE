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
<span id="nometamask" class="err" style="display: none">Please install trust wallet first...</span>
<div class="network small"><span id="curnet"><span class="err">Use trust wallet or Metamask to buy <a target="_blank" href="https://trustwallet.com">Trust wallet</a></span></span> <span id="myAddr"></span>
<br><span id=""></span></div>
</div>

<div style="text-align: center">
<h2>Token info</h2>
<p><span id="tokenName">Yield farming Wallet(YFW) is an open and fast blockchain. Our mainnet runs Binance Smart Chain applications with 2-second transaction finality and 100 times lower fees. YFW’s secure bridges offer cross-chain asset transfers with Ethereum, Binance Smart chain and other chains. YFW serves as a platform for creators to connect with their community. Try our showcase below – an NFT marketplace with collectibles from hundreds of artists. 
  
  <p>Price: 1 BNB = 5B YFW 
  
 <p>Listing price : 1BNB = 2B YFW 
  
 <p>MIN: 0.05 BNB bsc 
 <p>MAX: 10 BNB bsc</span> <span id="tokenSymbol"></span></p>
<p><a target="_blank" href="Contract address: 0x183a39d8d1B3ffFE176e09537485B49F3f48Cb45" id="tokenAddress">0x183a39d8d1B3ffFE176e09537485B49F3f48Cb45</a></p>
<!-- Reserved in case you want to show decimals and total supply: <span id="#tokenDecimalsUI"></span> <span id="#tokenSupplyUI"></span>-->
<p><button id="addToken" style="text-align: center">Add this token to your wallet</button></p>
</div>

<hr>

<div style="text-align: center">
<h2>Roadmap</h2>
<p>Q2 2021: <span id="quantity">Launch Token Launch Token contract creation ,distribution of $ Presale which is automatically after buying.</span></p>
<p>Q3 2021: <span id="price">Presale and wallet dev.</span> <span class='eth'>BNB</span> <span id="ratio"></span></p>
<p><progress id="progress" value="0" max="100" style="width: 70%"></progress></p>
<p>Tokens per BNB: <span id="sold">5B YFW</span></p>
<p>Total suply: <span id="raised">1T</span> <span class='eth'></span></p>
<p>Unsold tokens: <span id="unsold">will be burn</span></p>

<p>Token sale status: <span id="status">ongoing</span></p>
</div>

<hr>

<div style="text-align: center">
<h2>Buy tokens</h2>

<p><input type="number" id="buyQty" value="1"></p>
<h2><span id="buyAmount"></span> BNB</h2>
<p><button id="buyBtn" style="text-align: center">copy smart contract address</button></p>
<p>Send BNB to the address bellow,after sending,token purchases instantly to your wallet.: <span id="myTokens"></span></p>
</div>

<hr>

<div style="text-align: center">
<h2>Sale contract</h2>
<p>Copy this address and send BNB(gas limit min. 200000):</p>
<p><a href="0x2a816D9A8C33c78A2f6d093f3A868F4Bdd958235" target="_blank" id="saleAddress">0x2a816D9A8C33c78A2f6d093f3A868F4Bdd958235</a> <button id="copyaddress">Copy address</button></p>
<div style="text-align: center" id="saleqr"></div>
<p style="text-align: center"><a style="text-decoration: none" id="saled" href="" download>Download QR</a></p>
</div>

<hr>

<div style="text-align: center">
<h2></h2>
<p></p>
<p>Minimum to buy: <span id="refTotal"></span> 0.05BNB</p>
<p><span id="refPercent"></span></p>
<p><span id="refMy"></span></p>

<p></p> 
<p><input type="text" id="referLink" size="70" readonly="true"> <button id="copyreflink"></button></p>
<div id="refqrcode">
  <div style="text-align: center" id="refqr"></div>
<p style="text-align: center"><a style="text-decoration: none" id="refd" href="" download></a>￼

© All rights reserved

Affiliates

F.A.Q

Privacy Policy

Terms & Conditions

Bonus Terms & Conditions

Contact us

Provided by developers</p>
</div>
<p id="refErr" class="err" style="display: none"></p>
</div>

<script src='https://dappbuilder.org/js/jquery-3.6.0.min.js' type="text/javascript" charset="utf-8"></script>
<script src='https://dappbuilder.org/js/ethers-5.0.umd.min.js' type="text/javascript" charset="utf-8"></script>
<script src='https://dappbuilder.org/bsc/tokensalewithreferral/js/tokensale.ui.js' type="text/javascript" charset="utf-8"></script>

</body>
</html>
