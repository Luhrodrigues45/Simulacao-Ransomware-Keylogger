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
## Política de Uso Ético

Este projeto foi criado apenas para fins educacionais, em ambiente controlado, como parte do estudo sobre Ransomware e Keylogger.  
O uso indevido deste código fora de laboratório é proibido.

Para detalhes completos sobre responsabilidades, limites e boas práticas, consulte: 👉 [Política de Uso Ético (Security.md)](./Security.md)
