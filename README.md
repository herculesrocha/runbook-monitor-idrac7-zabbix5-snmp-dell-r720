# Monitoramento SNMP – Dell PowerEdge R720 (iDRAC 7) com Zabbix 5

Este repositório documenta o procedimento real e validado para
monitoramento SNMP de um servidor Dell PowerEdge R720 utilizando
a iDRAC 7 integrada ao Zabbix 5.

No ambiente de trabalho que foi executados esse procedimento, todas as VMs
e seus serviços, são monitoradas idividualmente. O foco do runbook
é para estudo e a meta é a coleta de métricas de hardware diretamente
da iDRAC, sem dependência do sistema operacional instalado no servidor.

---

## Ambiente validado

- Servidor: Dell PowerEdge R720
- Controladora: iDRAC 7
- Protocolo: SNMP
- Sistema de monitoramento: Zabbix 5
- IP da iDRAC: `192.168.127.10` (somente documental)
- Zabbix Server: `zabbix.dominio.com.br` (somente documental)

---

## Observações importantes sobre SNMP na iDRAC 7

⚠️ A iDRAC 7 **não permite habilitar apenas SNMP v2c**.  
Ao selecionar a opção:
All (SNMP v1/v2/v3) `(pocurei inserir imagens)`

Os protocolos **SNMP v1 e v2c são habilitados conjuntamente**, por
limitação do firmware.

Apesar disso:
- O Zabbix será configurado explicitamente para **SNMP v2c**
- O Zabbix **não realizará requisições via SNMP v1**
- A exposição do v1 será mitigada por controles do ambinete de rede

---

## Escopo

✅ Configuração real da iDRAC 7  
✅ Configuração do SNMP Agent  
✅ Uso de community SNMP  
✅ Integração com Zabbix 5  
✅ Validação via snmpwalk  
✅ Boas práticas de segurança interna  

❌ SNMP v3 (fora do escopo inicial)  
❌ Alertas avançados  
❌ Customização de triggers  

📘 Procedimento detalhado:

➡️ [runbook/idrac7_snmp_zabbix5.md](../runbook/idrac7_snmp_zabbix5.md)
