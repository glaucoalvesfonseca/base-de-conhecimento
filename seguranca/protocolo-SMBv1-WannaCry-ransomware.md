# Como habilitar ou desabilitar protocolos SMB no servidor SMB

*Obs.: para alterar as configurações abaixo, será necessário usar o Windows Powershell como usuário administrador.*

## No Windows 8 e Windows Server 2012

Windows 8 e o Windows Server 2012 introduzem nova SMBServerConfiguration conjunto de Windows PowerShell cmdlet. O cmdlet permite habilitar ou desabilitar os protocolos SMBv1 SMBv2 e SMBv3 no componente de servidor.

*Você não precisa reiniciar o computador depois de executar o cmdlet Set-SMBServerConfiguration.*

Para obter o estado atual da configuração de protocolo do servidor SMB, execute o seguinte cmdlet:
`Get-SmbServerConfiguration | Select EnableSMB1Protocol, EnableSMB2Protocol`

**Para desabilitar o SMBv1 no servidor SMB, execute o seguinte cmdlet:**

`Set-SmbServerConfiguration -EnableSMB1Protocol $false`

**Para desabilitar o SMBv2 e SMBv3 no servidor SMB, execute o seguinte cmdlet:**
`Set-SmbServerConfiguration -EnableSMB2Protocol $false`

Para ativar o servidor SMB SMBv1, execute o seguinte cmdlet:
`Set-SmbServerConfiguration -EnableSMB1Protocol $true`

Para habilitar o SMBv2 e SMBv3 no servidor SMB, execute o seguinte cmdlet:
`Set-SmbServerConfiguration -EnableSMB2Protocol $true`
