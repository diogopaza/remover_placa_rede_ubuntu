<h1>Remover placa de rede Ubuntu</h1>
<p>Este artigo é parte de uma série voltada a iniciantes no mundo Ubuntu</p>
<p>No meu caso o Ubuntu reconheceu a placa de rede do notebook. Porém essa placa de rede apresenta defeitos e 
por várias vezes se desconecta da rede wifi a qual está logada.</p>
<p>Para resolver o problema coloquei uma placa de rede usb, porém era preciso remover a placa de rede que vem integrada ao notebook.</p>
<h2>IFCONFIG</h2>
<p>O comando ifconfig lista todas as placas de rede instaladas</p>
<p>No meu caso o Ubunutu não trouxe o comando instalado por padrão</p>
<h3>Instalar ifconfig</h3>
<p>apt-get install net-tools( lembre de estar logado como root no terminal == comando == sudo -s)</p>
<p>Após efetuar o comando acima o ifconfig estara funcionando.</p>
<p>ifconfig</p>
<p>Com o comando acima serão listadas as placa de rede que estão rodando no seu sistema.</p>
<p>O ifconfig tem o atributo down que derruba uma placa de rede</p>
<p>ifconfig nome_placa down.</p>
<p>Esse comando mata(deruba) a placa de rede selecionada, claro que após reiniciar ela voltara a funcionar. No caso o comando não conseguiu matar o processo da placa de rede, e a placa de rede continuou funcionando, apesar de nenhuma mensagem de erro ser dada após o comando.</p>
<h3>Comandos úteis</h3>
<p>lsmod == lista os módulos do Kernel carregados pelo sistema</p>
<p>lshw -C network == mostra as informações sobre as placas de rede</p>
<p>lspci -k == mostra todos os dispositivos pci que são reconhecidos na máquina como módulos, drivers usados e etc.</p>
<h3>Remover módulo</h3>
<p>modprobe -r nome_módulo</p>
<p>O comando acima com o auxilio do comando lspci -k que mostrou exatamente o nome do módulo pertencente a placa de rede, aparentemente resolveu o problema. Mas ao reinicar o sistema a placa voltava a funcionar normalmente.</p>
<h2>Solução do problema</h2>
<p>Acessar a pasta /etc/modprobe.d</p>
<p>Abrir o arquivo blacklist.conf</p>
<p>No meu caso foi só incluir a linha <em>blacklist ath9k</em>. A parte final ath9k é o nome do módulo que localizei através do comando lspci -k.</p>

