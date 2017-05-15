# Como habilitar ou desabilitar protocolos SMB no servidor SMB

Windows 8 e Windows Server 2012
sd
Windows 8 e o Windows Server 2012 introduzem nova SMBServerConfiguration conjunto de Windows PowerShell cmdlet. O cmdlet permite habilitar ou desabilitar os protocolos SMBv1 SMBv2 e SMBv3 no componente de servidor.

Anotações Quando você habilitar ou desabilitar o SMBv2 no Windows 8 ou no Windows Server 2012, o SMBv3 também está ativado ou desativado. Esse comportamento ocorre porque esses protocolos compartilham a mesma pilha.

Você não precisa reiniciar o computador depois de executar o cmdlet Set-SMBServerConfiguration.

Para obter o estado atual da configuração de protocolo do servidor SMB, execute o seguinte cmdlet:
Get-SmbServerConfiguration | Select EnableSMB1Protocol, EnableSMB2Protocol

Para desabilitar o SMBv1 no servidor SMB, execute o seguinte cmdlet:
Set-SmbServerConfiguration -EnableSMB1Protocol $false

Para desabilitar o SMBv2 e SMBv3 no servidor SMB, execute o seguinte cmdlet:
Set-SmbServerConfiguration -EnableSMB2Protocol $false

Para ativar o servidor SMB SMBv1, execute o seguinte cmdlet:
Set-SmbServerConfiguration -EnableSMB1Protocol $true

Para habilitar o SMBv2 e SMBv3 no servidor SMB, execute o seguinte cmdlet:
Set-SmbServerConfiguration -EnableSMB2Protocol $true﻿
