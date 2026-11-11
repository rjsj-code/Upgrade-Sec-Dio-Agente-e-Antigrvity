# Upgrade-Sec-Dio-Agente-e-Antigrvity
Melhoria ao agente da DIO, utilizando Antigravity, incrivel o retorno recebido e o mundo a ser melhorado e inserido nesse formato.

## 📸 Evidências dos Testes

### 1. Análise de Código Inseguro (`app.py`)
- **Comportamento do Agente:** O agente atuou como mentor de AppSec, identificando a falha crítica de **SQL Injection** (`CWE-89`) e a violação de **armazenamento de senhas em texto puro** (`OWASP A02:2021`).
- **Mapeamento & Risco:** Relacionou a vulnerabilidade ao **OWASP Top 10 (A03:2021 - Injection)** e às técnicas do **MITRE ATT&CK** (`T1190`, `T1078`, `T1552` e `T1110`), classificando a severidade como alta/crítica.
- **Orientação:** Explicou conceitualmente o motivo do erro (concatenação direta de strings) e propôs a reescrita utilizando consultas parametrizadas (`prepared statements`) e técnicas de hashing.

### 2. Validação da Mitigação (`app_upd.py`)
- **Comportamento do Agente:** Após a atualização do código com marcadores de posição (`?`), o agente realizou uma nova varredura e confirmou a mitigação completa do SQL Injection.
- **Análise Adicional:** Além de validar a correção, o agente identificou um detalhe de lógica e indentação no fluxo do `return`, sugerindo o ajuste fino para garantir a correta execução do código.

### 3. Pergunta de Contexto e Postura Defensiva (Servidor Exposto)
- **Comportamento do Agente:** Ao receber o cenário de um servidor Ubuntu exposto na internet, o agente **não disparou comandos de imediato**.
- **Postura Investigativa:** Questionou primeiro a finalidade do ambiente, os serviços necessários e a forma de acesso antes de recomendar alterações.
- **Orientações Defensivas:** Mapeou o risco de lockout no SSH, aplicou o *Princípio do Menor Privilégio* (*Default Deny*) e orientou a configuração segura do firewall (`UFW`) por etapas.
