# Como conectar na interface gráfico do Linux

## Iniciando o serviço

1. Logue na máquina `10.0.28.26`
2. Acesse o usuário root utilizando o comando `sudo su -`
3. Execute o comando `vncserver`

## Desativando o serviço

1. Logue na máquina 10.0.28.26
2. Acesse o usuário root utilizando o comando `sudo su -`
3. Execute o comando `vncserver -kill :1`

## Acessando a interface

1. Abra o UltraVNC em seu desktop
2. Conecte-se no IP `10.0.28.26:5901` (não esqueça de informar a porta). A senha é `unimed,290`
3. Após o uso, encerre a conexão do UltraVNC fechando no X vermelho
