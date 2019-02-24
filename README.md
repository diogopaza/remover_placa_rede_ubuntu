<h1>Remover placa de rede Ubuntu</h1>
<p>Este artigo é parte de uma série voltada a iniciantes no mundo Ubuntu</p>
<p>No meu caso o Ubuntu reconheceu a placa de rede do notebook.Porém essa placa de rede apresenta defeitos e 
por várias vezes se desconecta da rede wifi a qual está logada.</p>
<h2>IFCONFIG</h2>
<p>O comando ifconfig lista todas as placas de rede instaladas</p>
<p>No meu caso o Ubunutu não trouxe o comando instalado por padrão</p>
<h3>Instalar ifconfig</h3>
<p>apt-get install net-tools( lembre de estar logado como root no terminal == comando == sudo -s)</p>
<p>Após efetuar o comando acima o ifconfig estara funcionando.</p>
<p>ifconfig</p>
<p>Com o comando acima serão listadas as placa de rede que estão rodando no seu sistema.</p>
<p>O ifconfig tem o atributo down que derruba uma placa de rede</p>
<p>ifconfig nome_placa down</p>
<p>Esse comando mata(deruba) a placa de rede selecionada, claro que após reiniciar ela voltara a funcionar.Porém em meu caso o comando não conseguiu matar o processo da placa de rede, e a placa de rede continuou funcionando, apesar de nenhuma mensagem de erro ser dada após o comando.</p>
