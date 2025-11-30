# Simulando Ameaças Digitais: Ransomware e Keylogger para Estudo
Este repositório documenta a conclusão do **Desafio Prático de Cibersegurança** da [Nome da Plataforma/Curso], com o objetivo de **experimentar, compreender e documentar** o funcionamento de malwares em um ambiente 100% controlado e seguro.

---

### 1. 🚀 Introdução e Contexto do Desafio

O projeto foi dividido em duas simulações principais e uma análise estratégica de defesa, conforme solicitado no desafio:

1. **Implementação de Ransomware Simulado.**
2. **Implementação de Keylogger Simulado.**
3. **Reflexão sobre Estratégias de Defesa e Mitigação.**

**Tecnologias Utilizadas:**
* Python;
* Módulos principais: `[cryptography, pynput, smtplib]`
* Ambiente: `[Ex: Linux VM e Windows Sandbox]`

---

### 2. 🔐 Implementação 1: Ransomware Simulado

#### A. Visão Geral
O script `ransomware.py` simula o ciclo de um ataque, focando na fase de infecção e criptografia. Para fins de testes e reversão segura, o script `decryptor.py` foi desenvolvido separadamente.

#### B. Mecanismos Chave
* **Criptografia:** Utilizei o algoritmo **[Nome do Algoritmo, ex: Fernet]** do módulo `[Ex: cryptography]` para simular o sequestro de dados. A chave de criptografia é gerada e armazenada em `[Ex: key.txt]`.
* **Captura de Alvos:** O script varre o diretório `[Nome do Diretório de Teste]` buscando arquivos com as extensões `[Ex: .txt, .doc, .jpg]` para criptografar.
* **Mensagem de Resgate:** Uma notificação simulada ou um arquivo `README_DECRYPT.txt` é gerado, instruindo sobre o processo de "resgate".

> **⚠️ Aviso:** Este código é estritamente educacional. Execute-o apenas em máquinas virtuais isoladas ou em ambientes de teste seguros.

---

### 3. ⌨️ Implementação 2: Keylogger Simulado

#### A. Visão Geral
O script `keylogger.py` demonstra a exfiltração de dados sensíveis, registrando todas as teclas pressionadas e enviando o arquivo de log para um e

## Política de Uso Ético

Este projeto foi criado apenas para fins educacionais, em ambiente controlado, como parte do estudo sobre Ransomware e Keylogger.  
O uso indevido deste código fora de laboratório é proibido.

Para detalhes completos sobre responsabilidades, limites e boas práticas, consulte: 👉 [Política de Uso Ético (Security.md)](./Security.md)
