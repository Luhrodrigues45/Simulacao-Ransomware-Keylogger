# Simulando Ameaças Digitais: Ransomware e Keylogger para Estudo
Este repositório documenta a conclusão do **Desafio Prático de Cibersegurança** da [Dio](https://web.dio.me/track/santander-ciberseguranca-2025), com o objetivo de **experimentar, compreender e documentar** o funcionamento de malwares em um ambiente 100% controlado e seguro.

---

### 1. 🚀 Introdução e Contexto do Desafio:
O projeto foi dividido em 2 simulações principais e 1 análise estratégica de defesa, conforme solicitado no desafio:

1. **Implementação de Ransomware Simulado.**
2. **Implementação de Keylogger Simulado.**
3. **Reflexão sobre Estratégias de Defesa e Mitigação.**

**Tecnologias Utilizadas:**
* Python;
* Módulos principais: `[cryptography, pynput, smtplib]`
* Ambiente: `[Ex: Windows, visual studio code]`

Obs: Você pode optar por testar em uma VM, o recomendado é este.

---

### 2. 🔐 Implementação 1: Ransomware Simulado

#### A. Visão Geral:
O script `ransomware.py` simula o ciclo de um ataque, focando na fase de infecção e criptografia. Para fins de testes e reversão segura, o script `decryptor.py` foi desenvolvido separadamente como mostra na imagem abaixo:

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/ae74936f-8ad6-41d3-b47a-85173dfc969d" />


#### B. Mecanismos Chave
* **Criptografia:** Utilizei o algoritmo **[Fernet]** da biblioteca `[Ex: cryptography]` para simular o sequestro de dados. A chave de criptografia é gerada e armazenada em `[Ex: Ransomware.py]`.
* **Captura de Alvos:** O script varre o diretório `[Teste_de_Ransomware]` buscando arquivo com a extensão `[Ex: .txt]` para criptografar.
* **Mensagem de Resgate:** Uma notificação simulada ou um arquivo `leia isso.txt` é gerado, instruindo sobre o processo de "resgate".

> **⚠️ Aviso:** Este código é estritamente educacional. Execute-o apenas em máquinas virtuais isoladas ou em ambientes de teste seguros.

---

### 3. ⌨️ Implementação 2: Keylogger Simulado

### A. Visão Geral do Módulo
O script `keylogger.py` demonstra a **captura furtiva de teclas** e o **registro local dos logs**, que é o primeiro passo para a exfiltração de dados sensíveis. O código atende ao requisito de registrar em arquivo `.txt` e implementar lógica de filtragem.

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/fac54287-9183-40ce-bd92-4ce57c047d03" />

### B. Mecanismos Chave (Análise do Código)

| Mecanismo | Detalhes da Implementação |
| :--- | :--- |
| **Captura de Teclas** | Utilização da biblioteca **`pynput.keyboard`** e do *handler* `on_press(key)`. |
| **Tratamento de Caracteres** | A lógica implementa um bloco `try-except AttributeError` para distinguir: **Caracteres normais** (`key.char`) de **Teclas Especiais** (como `Key.space`, `Key.enter`). |
| **Filtragem de Logs** | **Teclas de Controle (Shift, Ctrl, Alt, Caps Lock, etc.)** são definidas no dicionário `ignorar` e tratadas com `pass`, garantindo que o log se concentre apenas no conteúdo digitado pelo usuário. |
| **Registro de Logs** | As informações são salvas no arquivo **`log.txt`** usando o modo *append* (`"a"`). |
| **Exfiltração (E-mail)** | [Se a parte de envio por e-mail estiver em um script separado, mencione: *A funcionalidade de envio automático de logs (utilizando `smtplib`) é implementada em um módulo complementar e é executada periodicamente para exfiltração.*]

---

## 5. 🛡️ Reflexão sobre Defesa e Mitigação

A simulação prática de Ransomware e Keylogger revela a importância de uma **Estratégia de Defesa em Camadas**. A mitigação dessas ameaças exige medidas que vão desde o nível de infraestrutura até a conscientização do usuário.

### 1. Defesa Específica Contra Ransomware

O foco aqui é na **Resiliência de Dados** e na **Prevenção da Execução**.

| Estratégia | Detalhes Técnicos |
| :--- | :--- |
| **Backup 3-2-1** | É a defesa mais importante. Manter **três** cópias dos dados, em **duas** mídias diferentes, com **uma** cópia **off-site e offline** (desconectada da rede principal). Isso garante que o Ransomware não possa criptografar todas as cópias. |
| **Princípio do Menor Privilégio** | Aplicar permissões mínimas necessárias ao usuário. Um usuário sem privilégios de administrador **limita** o Ransomware de criptografar pastas críticas do sistema ou de se auto-executar com privilégios elevados. |
| **Segmentação de Rede** | Isolar dados críticos em segmentos de rede separados. Isso **contém o Ransomware**, impedindo que ele se propague horizontalmente por toda a rede após a infecção inicial. |

### 2. Defesa Específica Contra Keylogger

O foco aqui é na **Detecção Furtiva** e na **Proteção do Endpoint**.

| Estratégia | Detalhes Técnicos |
| :--- | :--- |
| **Soluções EDR/AV** | Implementar soluções de **Endpoint Detection and Response (EDR)**. Estas ferramentas monitoram *hooks* de teclado e processos de baixo nível, identificando o uso de bibliotecas suspeitas como `pynput` ou tentativas de comunicação externa para **exfiltração de logs**. |
| **Teclado Virtual** | Para inserção de credenciais sensíveis (senhas), o uso de teclados virtuais *on-screen* pode frustrar Keyloggers baseados em *hooking* de hardware ou software, pois a digitação é feita através de eventos do mouse. |
| **Monitoramento de Comunicação** | Configurar o **Firewall** para alertar ou bloquear tentativas de conexão **SMTP** ou tráfego incomum de saída. O Keylogger precisa de um canal para enviar o log (ex: e-mail), e o bloqueio desse canal impede o sucesso do ataque. |

### 3. Mitigação Comum (Fator Humano)

A maioria dos ataques de malware começa com o **Fator Humano**.

* **Conscientização do Usuário (Phishing):** O Ransomware e o Keylogger frequentemente entram através de e-mails de **phishing** ou *malvertising*. Treinamento contínuo ajuda os usuários a identificarem anexos e links maliciosos.
* **Patch Management:** Manter o **Sistema Operacional** e todos os aplicativos (navegadores, Java, Adobe) atualizados. Muitas vezes, o malware explora vulnerabilidades de softwares desatualizados para ser executado.
* **Software de Segurança Atualizado:** Garantir que o Antivírus e o EDR estejam sempre rodando com as **definições de vírus mais recentes**.
* 
---

## Política de Uso Ético
Este projeto foi criado apenas para fins educacionais, em ambiente controlado, como parte do estudo sobre Ransomware e Keylogger.  
O uso indevido deste código fora de laboratório é proibido.
Para detalhes completos sobre responsabilidades, limites e boas práticas, consulte: 👉 [Política de Uso Ético (Security.md)](./Security.md)
