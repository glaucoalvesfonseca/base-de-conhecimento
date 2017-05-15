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

**Para ativar o servidor SMB SMBv1, execute o seguinte cmdlet:**

`Set-SmbServerConfiguration -EnableSMB1Protocol $true`

**Para habilitar o SMBv2 e SMBv3 no servidor SMB, execute o seguinte cmdlet:**

`Set-SmbServerConfiguration -EnableSMB2Protocol $true`

## O Windows 7, Windows Server 2008 R2, Windows Vista e Windows Server 2008

Para habilitar ou desabilitar os protocolos SMB em um servidor SMB que esteja executando usar o Windows 7, Windows Server 2008 R2, Windows Vista ou Windows Server 2008, Windows PowerShell ou do Editor do registro.

### Windows PowerShell 2.0 ou uma versão posterior do PowerShell

Para desabilitar o SMBv1 no servidor SMB, execute o seguinte cmdlet:

`ItemProperty Set-SMB1 do caminho "HKLM:\SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters"-type DWORD-value 0 - Force`

**Para desabilitar o SMBv2 e SMBv3 no servidor SMB, execute o seguinte cmdlet:**

`ItemProperty Set-SMB2 do caminho "HKLM:\SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters"-digite DWORD-valor 0 - Force`

**Para ativar o servidor SMB SMBv1, execute o seguinte cmdlet:**

`Conjunto ItemProperty-caminho "HKLM:\SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters" SMB1 -Digite DWORD -valor 1 - Force`

**Para habilitar o SMBv2 e SMBv3 no servidor SMB, execute o seguinte cmdlet:**

`Conjunto ItemProperty-caminho "HKLM:\SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters" SMB2 -Digite DWORD -valor 1 - Force`

*Observação: Você deve reiniciar o computador após fazer essas alterações.*

## No Editor do registro (caso as opções acima não funcionem)

**Importante**: Esta parte contém informações sobre como modificar o registro. Certifique-se de fazer backup do registro antes de modificá-lo. Certifique-se de que você saiba como restaurar o registro caso ocorra um problema. 

Para ativar ou desativar SMBv1 no servidor SMB, configure a seguinte chave do registro:
```
Subchave do registro: entrada de registro HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters: SMB1
REG_DWORD: 0 = desativado
REG_DWORD: 1 = ativado
Padrão: 1 = ativado
```
Para habilitar ou desabilitar o SMBv2 no servidor SMB, configure a seguinte chave do registro:

Subchave do registro: entrada de registroHKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters: SMB2
REG_DWORD: 0 = desativado
REG_DWORD: 1 = ativado
Padrão: 1 = ativado
